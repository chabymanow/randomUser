<template>
    <div>
        <button @click="getData()">Get user</button>
    </div>
</template>

<script>
    export default{
        name: 'getUser',
    data(){
        return{
            firstName: "Chaby"
        };
    },
    components: {},
    methods: {
        async getData(){
            const res = await fetch('https://randomuser.me/api')
            const {results} = await res.json()
            console.log(results)
            this.$emit('getData', results[0])
        }
    }
    // {
    //     return{
    //         firstName: 'Chaby',
    //         lastName: 'Manow',
    //         email: 'chabymanow@gmail.com'
    //     }
    // }
    }
</script>

<style scoped>
    button{
        font-size: 1.3rem;
        width: 10em;
        height: 1.5em;
        border-radius: 20px;
        padding: 1em 1em;
    }
</style>