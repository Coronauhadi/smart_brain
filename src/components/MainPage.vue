<template>
  <div class="container-fluid">
    <header class="row">
      <nav class="col  elegant-color-dark text-white">
        <div class="container-fluid">
          <div class="row">
            <div class="col">
              <span class="navbar-brand"> <img src="/res/coin.png" width="25" height="25" alt="Монетки:"> {{coins}} </span>
            </div>
          </div>
        </div>
      </nav>
    </header>
    <div class="row">
      <div class="col">
        <div class="">
<<<<<<< HEAD
=======
          <!-- <span class=""> 'Самостоятельность - это способность купить сосиски не по акции.' (с) Адам Смит </span> -->
>>>>>>> 4931828fd990c2205eeae20e3f21acdbfc96ab22
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    nextPage: Function,
  },
  data(){
    return{
      coins: 0,
    }
  },
  methods: {

  },
}
</script>

<style scoped>
.navbar-brand{
  /* TODO: check on the phones */
  /* margin: 0 -20vw; */
}
</style>
