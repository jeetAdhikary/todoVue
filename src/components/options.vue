<template>
    <div>
    <div class="widget-header">
        <h3 v-if="options.length===0" class="widget-header__title">Please add your options</h3>
        <h3 v-else class="widget-header__title">Options are : </h3>
        <button class=" button__link" @click="handleDeleteOptions">Remove all</button>
    </div>
    <p v-if="options.length===0" class="widget__message"></p>
    <Option v-for="(option, index) in options" 
            :key="index"
            :count="index+1" 
            :option="option" 
            :handleDelete="handleDeleteOption"/>
    </div>
</template>

<script>

import Option from './Option';

export default {
    name : 'Options',
    components  : {
        Option
    },
    props : {
        options : Array,
        handleDeleteOptions : Function,
        handleDeleteOption : Function,
    }
}
</script>

<style>
.widget__message{
    border-bottom: 1px solid #464b5e;
    color: #a5afd7;
    margin: 0;
    padding: 3.2rem;
    text-align: center;
}

.widget-header{
    background: #3c4251;
    color: #a5afd7;
    display: flex;
    justify-content: space-between;
    padding: 1.6rem;
}

.widget-header__title{
    margin: 0;
}

.button__link{
    background: none;
    border : none;
    color: #a5afd7;
    padding: 0;
    font-weight: 500
}

</style>
