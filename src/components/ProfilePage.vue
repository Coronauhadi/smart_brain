<template>
  <div class="poln white container-fluid">
    <div class="row">
      <div class="col pb-4">

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

        <h1 class="text-center mt-4">О приложении</h1>
        <div class=" rounded border mx-auto p-2 lead mb-5">
          Добро пожаловать в это шуточное приложение! <br><br>
          Оно вряд ли поможет стать Вам самостоятельным. Мы думаем приложение вообще вряд ли способно сделать кого-то самостоятельным.
          Но несмотря на это наше приложение может чему- научить, загляните в раздел магазин.
          <br><br>
          Приложение несет лишь развлекательный характер. Не относитесь слишком серьезно к заданиям. Надеимся нам удалось поднять Вам настроение
          и направить на путь саморазвития.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProfilePage',
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

</style>
