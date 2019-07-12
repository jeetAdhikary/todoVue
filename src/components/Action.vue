<template>
    <button class="big-button" @click="onHandlePick">What Should I Do ? </button>
</template>

<script>
export default {
    name : 'Action',
    props : {
        onHandlePick : Function
    }
}
</script>

<style>
.big-button {
    background: #8357c5;
    border: none;
    border-bottom: .6rem solid #3c275a;
    color: white;
    font-weight: bold;
    font-size: 1.6rem;
    width: 100%;
    margin-bottom: 1.6rem;
    padding: 2.4rem;
}

.big-button:disabled{
    opacity: .5;
}
</style>
