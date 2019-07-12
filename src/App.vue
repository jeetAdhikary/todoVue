<template>
  <div>
    <Header  :title="title" :subTitle="subTitle"/>
    <div class="container">
      <Action  :onHandlePick="handlePick"/>
      <div class="widget">
        <Options :options="options" 
        :handleDeleteOptions="handleDeleteOptions"
        :handleDeleteOption="handleDeleteOption"
         />
         <AddOption :handleAddOption="handleAddOption"  />
      </div>
    </div>
    <OptionModal v-if="selectedOption!==undefined" @close="selectedOption=undefined" :selectedOption="selectedOption"/>
  </div>
</template>

<script>
import Header from './components/Header';
import Options from './components/options';
import AddOption from './components/AddOption';
import Action from './components/Action';
import OptionModal from './components/OptionModal';

export default {
  name: 'app',
  components: {
    Header,
    Options,
    AddOption,
    Action,
    OptionModal
  },
  data : function(){
    return {
      title : 'Todo Try Using Vue',
      subTitle : 'Put your life in the hands of a computer',
      options : [],
      selectedOption : undefined
    }
  },
  methods : {
    handleDeleteOptions : function(){
      this.options = [];
    },

    handleDeleteOption : function(optionToRemove){
     this.options = this.options.filter((option)=>{
        return option !==optionToRemove;
      });
    },

    handlePick : function(){
      const randomNumber = Math.floor(Math.random()*this.options.length);
      const option = this.options[randomNumber];
      this.selectedOption = option;
    },

    handleAddOption : function(option){
      if(!option){
            return 'Please provide valid option';
        }else if(this.options.indexOf(option)> -1){
            return 'This option already exists';
        }
        this.options = this.options.concat(option);
    }
  }
}
</script>

<style>

html {
    font-size: 62.5%;
}

body {
    font-family: Helvetica ,Arial , sans-serif;
    font-size: 1.6rem;
    background: #333745;
}
.container{
    max-width: 60rem;
    margin: 0 auto;
    padding: 0 1.6rem ;
}

.widget{
    background: #464b5e;
    margin-bottom: 4.8rem;
}


.button {
    background: #8357c5;
    border: none;
    border-bottom: .3rem solid #52357c;
    color: white;
    font-weight: 500;
    padding: 1.2rem;
}
</style>
