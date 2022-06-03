<template>
    <div class="card">
        
        <img v-bind:src="picture" alt="">
        <p class="name">{{title}} {{firstName}} {{lastName}}</p>
        <p class="email">{{email}}</p>
        <p class="phone">{{phone}}</p>
        <p class="mobile">{{mobile}}</p>
    </div>
</template>

<script>
    export default{
        name: 'RandomUser',
    props:{
        firstName: String,
        lastName: String,
        title: String,
        email: String,
        picture: String,
        phone: String,
        mobile: String
    },
    }
</script>

<style scoped>
    h1{
        font-size: 3rem;
    }

    p{
        margin-top: 2em;
        font-size: .8em;
    }

    img{
        border: 2px solid #657bb9;
        border-radius: 50%;
        width: 200px;
        height: 200px;
    }

    .card{
        background: #899AC0;
        filter: brightness(90%);
        width: 35ch;
        height: 50ch;
        border: 1px solid rgba(0, 0, 0, .5);
        border-radius: 20px;
        padding: 1em 1em;
        box-shadow: 0 0 5px rgba(0, 0, 0, .5), 0 0 20px rgba(0, 0, 0, .3);
    }

    .name{
        margin-top: .5em;
        font-size: 1.7em;
        font-weight: 700;
    }

    .email{
        margin-top: .5em;
        font-size: 1em;
        font-weight: 900;
    }

    .phone, .mobile{
        margin-top: .5em;
        font-size: 1.7em;
        font-weight: 700;
    }
</style>