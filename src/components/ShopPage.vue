<template>
  <div class="poln white container-fluid">
    <div class="row pb-3">
      <div class="col pb-5">

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

        <h1 class="text-center mt-4">Магазин</h1>

        <div class="" v-for="task in shopList" :key="task.name">

          <div v-if="task.open==false" @click="buy(task)"  class="border p-1 mt-3 elegant-color-dark rounded text-center z-depth-1 " style="height:100px;">
            <!-- <i class="fas white-text fa-cat" style="font-size:40px"></i> -->
            <div class="h-100 rgba-stylish-light py-2">
              <!-- <img src="https://image.flaticon.com/icons/svg/308/308028.svg" class="" width="40px" alt=""> -->
              <h4 class="  white-text " style="">Секретный навык</h4>
              <p class="h4  white-text ">-{{task.price}}<img src="/res/coin.png" width="25" height="25" alt="Монетки:"></p>
            </div>
          </div>

          <a :href="task.url" target="_blank">
            <div v-if="task.open==true" class="border p-1 mt-3 rounded text-center z-depth-1 bg" :style="'background-image: url('+task.img+');height:100px;'">
              <!-- <i class="fas white-text fa-cat" style="font-size:40px"></i> -->
              <div class="h-100 rgba-stylish-light py-2">
                <!-- <img src="https://image.flaticon.com/icons/svg/308/308028.svg" class="" width="40px" alt=""> -->
                <h4 class="  white-text " style="">{{task.title}}</h4>
                <p class="lead white-text">Открыть <i class="fas fa-sign-in-alt"></i></p>
                <!-- <p class="h4  white-text ">-10<img src="/res/coin.png" width="25" height="25" alt="Монетки:"></p> -->
              </div>
            </div>
          </a>

        </div>


      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ShopPage',
  props: {
    nextPage: Function,
  },
  mounted() {
    if (localStorage.taskList) {
      try {
        this.shopList = JSON.parse(localStorage.getItem('shopList'));
      } catch(e) {
        localStorage.removeItem('shopList');
      }
    }
    if (localStorage.coins) {
      this.coins = Number(localStorage.coins)
    }
  },
  data(){
    return{
      coins: 0,
      shopList: [],
    }
  },
  methods: {
    buy(task){
      if (this.coins < task.price) {
        return "nomoney"
      }
      this.coins -= task.price
      localStorage.coins = this.coins

      task.open = true
      const parsed2 = JSON.stringify(this.shopList)
      localStorage.setItem('shopList', parsed2)
    }
  },
}
</script>

<style scoped>
  .bg{
    /* background-image: url('https://cdn.pixabay.com/photo/2015/03/26/09/41/tie-690084_960_720.jpg'); */
    background-size: cover;
  }
  .poln{
    min-height: 100vh;
  }
</style>
