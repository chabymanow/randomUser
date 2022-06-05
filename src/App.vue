<template>
  <h1>Random user</h1>
  <GetUser @getData="getData($event)"/>
  <CardDiv :cards="RandomUsers" :idKey="idKey" />
    <!-- <RandomUser :title=title :firstName= firstName :lastName=lastName :email=email :picture=picture :phone=phone :mobile=mobile /> -->
</template>

<script>
import GetUser from './components/GetUser.vue'
import CardDiv from './components/CardDiv.vue';

export default {
  name: 'App',
  data(){
    return{
      RandomUsers: [],
    };
  },
  components: {
    GetUser,
    CardDiv
},
  methods: {
    getData(e){
      this.RandomUsers = [...this.RandomUsers, e];
      console.log(this.RandomUsers);
    },
  },
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: content-box;
}

body{
  background: #3d4d6e;
  margin-bottom: 5vh;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

h1{
  color: #e5e2e2;
  position: relative;
  font-size: 4rem;
  z-index: -100;
}

h1::before{
  content: 'Random';
  position: absolute;
  font-size: 15em;
  width: 110vw;
  height: 100vh;
  opacity: .03;
  left: -10vw;
  top: -350%;
  overflow: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
}

.cards{
  width: 80vw;
  margin: 0 auto;
  margin-top: 3rem;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
