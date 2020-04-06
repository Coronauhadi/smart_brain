<template>
  <div id="app">
    <HelloPage :nextPage="nextPage"  v-if="namePage == 'HelloPage'" />
    <StatPage :nextPage="nextPage"  v-if="namePage == 'StatPage'" />
    <AgePage :nextPage="nextPage"  v-if="namePage == 'AgePage'" />
    <MainPage :nextPage="nextPage"  v-if="namePage == 'MainPage'" />
    <Loser :nextPage="nextPage" v-if="namePage == 'Loser'" />
    <SaveData :nextPage="nextPage"  v-if="namePage == 'SaveData'" />
    <Winner :nextPage="nextPage"  v-if="namePage == 'Winner'" />
    <!-- <Nav :nextPage="nextPage"  v-if="namePage == 'Nav'" /> -->

    <Nav :nextPage="nextPage"   />

  </div>
</template>

<script>
import HelloPage from './components/HelloPage.vue'
import StatPage from './components/StatPage.vue'
import AgePage from './components/AgePage.vue'
import MainPage from './components/MainPage.vue'
import Loser from './components/Loser.vue'
import Winner from './components/Winner.vue'
import SaveData from './components/SaveData.vue'
import Nav from './components/Nav.vue'
// import SaveData from './components/SaveData.vue'

export default {
  name: 'App',
  components: {
    HelloPage,
    StatPage,
    AgePage,
    MainPage,
    Loser,
    Winner,
    SaveData,
    Nav,
    // SaveData,


  },
  mounted() {
    // localStorage.name
    this.aud = new Audio();
    this.aud.src = 'mus/Sound.wav';
    if (localStorage.namePage) {
      //Эта переменная влияет на сохранение страницы при перезагрузке
      this.namePage = localStorage.namePage
    }
  },
  data(){
    return{
      namePage: "HelloPage",
      aud:'',
    }
  },
  methods:{
    nextPage: function(newPage) {
      this.aud.play();
      this.namePage = newPage
      localStorage.namePage = newPage
    },

  },
}
</script>

<style>
  h1{
    font-family: Amatic SC;

  }

  #app {
    /* font-family: Roboto; */
    /* font-family: 'Roboto', sans-serif; */
    font-family: 'Oswald', sans-serif;
    /* font-weight: 100; */
    /* -webkit-font-smoothing: antialiased; */
    /* -moz-osx-font-smoothing: grayscale; */
    /* color: #2c3e50; */
  }
</style>
