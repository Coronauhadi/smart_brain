<template>
  <div id="app">
    <HelloPage :nextPage="nextPage"  v-if="namePage == 'HelloPage'" />
  </div>
</template>

<script>
import HelloPage from './components/HelloPage.vue'

export default {
  name: 'App',
  components: {
    HelloPage
  },
  mounted() {
    // localStorage.name

  },
  data(){
    return{
      namePage: "HelloPage",
    }
  },
  methods:{
    nextPage: function(newPage) {
      this.namePage = newPage
    },

  },
}
</script>

<style>
#app {
  font-family: Amatic SC;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* color: #2c3e50; */
}
</style>
