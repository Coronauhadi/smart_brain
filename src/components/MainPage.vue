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
      <div class="col elegant-color-dark poln text-warning text-center">
        <div class="quote">
          <p> '<strong>Самостоятельность</strong> - это способность купить сосиски не по акции.' (с) Адам Смит </p>
        </div>
        <div class="todoBanner">
          <p> Выполняй задания и становись самостоятельным! </p>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col text-center">
          <div class="tasklist">
            <p> Бла-бла-бла </p>
            <p> Бла-бла-бла </p>
            <p> Бла-бла-бла </p>
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
  .container-fluid{
    background-color: #212121;
  }
  .tasklist{
    border-top-right-radius: 30px;
    border: 5vh solid white;
    background-color: white;
    color: #212121;
  }
</style>
