<template>
    <div class="option">
        <p class="option__text">{{count}} . {{option}}</p>
        <button  @click="onHandleDelete" class="button__link">Remove</button>
    </div>
</template>

<script>
export default {
    name : 'Option',
    props : {
        count : Number,
        option : String,
        handleDelete : Function,
    },
    methods : {
        onHandleDelete : function(){
            this.handleDelete(this.option);
        }
    }
    
}
</script>

<style>
.option{
    border-bottom: 1px solid #464b5e;
    display: flex;
    justify-content: space-between;
    padding: 3.2rem 1.6rem ;
}

.option__text{ 
     color: white;
     font-weight: 500;
     font-size: 2rem;
     word-break: break-all;
}

.button--link{
    cursor: pointer;
    background: none;
    border : none;
    color: #a5afd7;
    padding: 0;
    font-weight: 500
}
</style>
