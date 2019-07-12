<template>
    <div class="header">
        <div class="container">
            <h1 class="header__title">{{title}}</h1>
            <h3 class="header__subtitle">{{subTitle}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name : 'Header',
    props:{
        title : String,
        subTitle : String
    }
}
</script>


<style scoped>
    .header{
    background: #20222b;
    color: white;
    margin-bottom: 1.6rem;
    padding: 1.6rem 0;
}

.header__title{
    font-size: 3.2rem;
    margin : 0;

}

.header__subtitle{
    color: #a5afd7;
    font-size: 1.6rem;
    font-weight: 500;
}

@media (min-width : 45rem){
    .header{
        margin-bottom: 4.8rem;
    }

}
</style>
