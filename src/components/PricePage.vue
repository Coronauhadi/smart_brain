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

        <div class="border text-center br position-relative" v-if="winnerArr.length>0" :style="'background-image:url(' +winnerArr[ind].img+ ');' ">
          <div class="h-100 rgba-stylish-light text-white px-4 pt-2">

            <p class="" style="font-size:40px!important; margin-top:5vh;"><b>{{winnerArr[ind].title}}</b> </p>
            <div @click="next(1)" class="position-absolute  " style="right:20px; top:40%;">
              <i class="fas fa-chevron-right" style="font-size:50px; color:white;"></i>
            </div>
            <div @click="next(0)" class="position-absolute  " style="left:20px; top:40%;">
              <i class="fas fa-chevron-left" style="font-size:50px; color:white;"></i>
            </div>
            <p class="position-absolute text-center w-100" style="font-size:28px!important; bottom:40px; left:0; ">{{winnerArr[ind].text}}</p>
          </div>
        </div>
        <div class="h-100" v-else >
          <h3 class="text-center position-absolute w-100 " style="top:50vh; left:0">ого здесь пусто... <br>скорее выполните задание</h3>
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
  created(){
    if (localStorage.coins) {
      this.coins = Number(localStorage.coins)
    }
    if (localStorage.taskList) {
      try {
        this.winnerArr = JSON.parse(localStorage.getItem('winnerArr'));
        if (this.winnerArr == null) {
          this.winnerArr = []
        }
      } catch(e) {
        localStorage.removeItem('winnerArr');
      }
    }
  },
  data(){
    return{
      coins: 0,
      winnerArr: [],
      ind: 0,
    }
  },
  methods: {
    next(napr){
      if (napr == 1) {
        if (this.winnerArr.length-1 == this.ind) {
          this.ind = 0
        }else {
          this.ind ++
        }
      }else {
        if (this.ind == 0) {
          this.ind = this.winnerArr.length-1
        }else {
          this.ind --
        }
      }
    },
  },
}
</script>

<style scoped>
  .br{
    background-position:center;
    background-size: cover;
    height: 70vh;
    background-position:center;
    background-size: cover;
  }

  .poln{
    min-height: 100vh;
  }
</style>
