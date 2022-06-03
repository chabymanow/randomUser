<template>
  <h1>Random user</h1>
  <GetUser @click="show = !show" @getData="getData($event)"/>
  <div class="cards">
      <RandomUser :title=title :firstName= firstName :lastName=lastName :email=email :picture=picture :phone=phone :mobile=mobile />
  </div>
</template>

<script>
import RandomUser from './components/RandomUser.vue'
import GetUser from './components/GetUser.vue'

export default {
  name: 'App',
  data(){
    return{
      show: true,
      title: '',
      firstName: 'Chaby',
      lastName: 'Manow',
      email: 'themainemail@email.com',
      picture: 'https://images.unsplash.com/photo-1608889175123-8ee362201f81?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTh8fHN1cGVybWFufGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
      phone: '0202164866',
      mobile: '0705454666',
      RandomUser: []
    };
  },
  components: {
    RandomUser,
    GetUser
  },
  methods: {
    getData(e){
      this.title = e.name.title;
      this.firstName = e.name.first;
      this.lastName = e.name.last;
      this.email = e.email;
      this.picture = e.picture.large;
      this.phone = e.phone;
      this.mobile = e.cell
    },
    addCard(){
      this.RandomUser.push()
    }
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
