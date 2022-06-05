<template>
    <div class="card">
        
        <img v-bind:src="picture" alt="">
        <p class="name">{{title}} {{firstName}} {{lastName}}</p>
        <p class="email">{{email}}</p>
        <p class="phone"><i class="fa-solid fa-phone"></i> {{phone}}</p>
        <p class="mobile"><i class="fa-solid fa-mobile-screen-button"></i> {{mobile}}</p>
        <p class="location"><i class="fa-solid fa-location-dot"></i> Country: {{ city }}, {{country}}</p>
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
        mobile: String,
        country: String,
        city: String
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
        width: 150px;
        height: 150px;
    }

    .card{
        background: rgba(15, 12, 21, 0.7);
        color: #ede6fb;
        filter: brightness(90%);
        width: 25ch;
        height: 40ch;
        border: 1px solid rgba(0, 0, 0, .5);
        border-radius: 20px;
        padding: 1em 1em;
        box-shadow: 0 0 5px rgba(0, 0, 0, .5), 0 0 20px rgba(0, 0, 0, .3);
        position: relative;
        overflow: hidden;
    }

    .card::after{
        content: "";
        position: absolute;
        top: 0;
        bottom: 33ch;
        left: 0;
        right: 0;
        background: rgb(25, 18, 36);
        z-index: -100;
    }

    .name{
        margin-top: .5em;
        font-size: 1.2em;
        font-weight: 700;
    }

    .email{
        margin-top: .5em;
        font-size: .7m;
        font-weight: 500;
    }

    .phone, .mobile{
        margin-top: .5em;
        font-size: .8em;
        font-weight: 300;
    }
</style>