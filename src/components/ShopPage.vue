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

        <h1 class="text-center mt-4">Магазин</h1>

        <div class="border p-1 mt-3 elegant-color-dark rounded text-center z-depth-1 bg" style="height:100px;">
          <!-- <i class="fas white-text fa-cat" style="font-size:40px"></i> -->
          <div class="h-100 rgba-stylish-light py-2">
            <!-- <img src="https://image.flaticon.com/icons/svg/308/308028.svg" class="" width="40px" alt=""> -->
            <p class="h4  white-text ">Секретный навык</p>
            <p class="h4  white-text ">-10<img src="/res/coin.png" width="25" height="25" alt="Монетки:"></p>

          </div>
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
  .bg{
    background-image: url('https://cdn.pixabay.com/photo/2015/03/26/09/41/tie-690084_960_720.jpg');
    background-size: cover;
  }
  .poln{
    min-height: 100vh;
  }
</style>
