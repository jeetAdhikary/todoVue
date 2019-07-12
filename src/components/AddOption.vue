<template>
    <div>
        <form class="add-option" @submit.prevent="handleFormSubmit">
            <input type="text" class="add-option__input" name="option">
            <button class="button">Add Option</button>
        </form>
    </div>
</template>

<script>
export default {
    name : 'AddOption',
    props : {
        handleAddOption : Function
    },
    methods : {
        handleFormSubmit : function(event){
            const option = event.target.elements.option.value.trim();
            this.handleAddOption(option);
            event.target.elements.option.value = '';
        }
    }
}
</script>

<style>
.add-option{
    display: flex;
    flex-direction: column;
    padding: 1.6rem;
}

.add-option__input{
    flex-grow: 1;
    color: #a5afd7;
    padding: 1.2rem;
    background: #333745;
    border : none;
    border-bottom: .3rem solid #333745;
    margin :  0 0 1.2rem 0;
    /* margin-right: 1.2rem; */
}

@media (min-width : 45rem){
    .add-option{
        flex-direction: row;
    }
    .add-option__input{
        margin: 0 1.2rem 0 0;
    }
}
</style>
