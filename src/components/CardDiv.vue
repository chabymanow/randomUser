<template>
    <div class="cards">
        <div :key="user.id.value" v-for="user in cards">
            <RandomUser
                :title=user.name.title
                :firstName=user.name.first
                :lastName= user.name.last
                :email=user.email
                :mobile=user.phone
                :phone=user.cell
                :picture=user.picture.large
                :country= user.location.country
                :city=user.location.city
            />
        </div>
    </div>
</template>

<script>
import RandomUser from './RandomUser.vue';
    export default{
    name: "CardDiv",
    props: {
        cards: Array
    },
    components: { RandomUser }
}
</script>

<style scoped>
    .cards{
        width: 95vw;
        margin: 0 auto;
        margin-top: 5em;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 2em;
    }
</style>