<template>
  <div class="poln white container-fluid">
    <div class="row">
      <div class="col ">

        <header class="row elegant-color-dark">
          <nav class="col text-white">
            <div class="container-fluid">
              <div class="row">
                <div class="col">
                  <span class="navbar-brand"> <img src="/res/coin.png" width="25" height="25" alt="Монетки:"> {{coins}} </span>
                </div>
              </div>
            </div>
          </nav>
        </header>

        <h1 class="text-center mt-4">Ваши достижения</h1>

        <div class="border text-center br position-relative" style="background:url('https://cdn.pixabay.com/photo/2017/11/11/15/52/young-man-2939344_960_720.jpg');background-position:center; background-size: cover;">
          <div class="h-100 rgba-stylish-light text-white px-4 pt-2">

            <p class="" style="font-size:40px!important; margin-top:5vh;"><b>Просветленный</b> </p>
            <div class="position-absolute  " style="right:20px; top:40%;">
              <i class="fas fa-chevron-right" style="font-size:50px; color:white;"></i>
            </div>
            <div class="position-absolute  " style="left:20px; top:40%;">
              <i class="fas fa-chevron-left" style="font-size:50px; color:white;"></i>
            </div>
            <p class="position-absolute text-center w-100" style="font-size:28px!important; bottom:40px; left:0; ">Теперь вы знаете все секреты этого непонятного мира</p>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PricePage',
  props: {
    nextPage: Function,
  },
  mounted(){
    if (localStorage.coins) {
      this.coins = Number(localStorage.coins)
    }
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
  .br{
    height: 70vh;
    background-position:center;
    background-size: cover;
  }

  .poln{
    min-height: 100vh;
  }
</style>
