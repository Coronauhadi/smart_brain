<template>
  <div id="app">
    <HelloPage :nextPage="nextPage"  v-if="namePage == 'HelloPage'" />
    <StatPage :nextPage="nextPage"  v-if="namePage == 'StatPage'" />
    <AgePage :nextPage="nextPage"  v-if="namePage == 'AgePage'" />
    <MainPage :nextPage="nextPage"  v-if="namePage == 'MainPage'" />
    <Loser :nextPage="nextPage" v-if="namePage == 'Loser'" />
    <!-- <MainPage :nextPage="nextPage"  v-if="namePage == 'MainPage'" /> -->
  </div>
</template>

<script>
import HelloPage from './components/HelloPage.vue'
import StatPage from './components/StatPage.vue'
import AgePage from './components/AgePage.vue'
import MainPage from './components/MainPage.vue'
import Loser from './components/Loser.vue'
// import MainPage from './components/MainPage.vue'

export default {
  name: 'App',
  components: {
    HelloPage,
    StatPage,
    AgePage,
    MainPage,
    Loser,
    // MainPage,


  },
  mounted() {
    // localStorage.name
    if (localStorage.namePage) {
      //Эта переменная влияет на сохранение страницы при перезагрузке
      this.namePage = localStorage.namePage
    }
  },
  data(){
    return{
      namePage: "HelloPage",
    }
  },
  methods:{
    nextPage: function(newPage) {
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
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* color: #2c3e50; */
  }
</style>
