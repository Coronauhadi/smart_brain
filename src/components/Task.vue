<template>
  <div class="container-fluid elegant-color-dark poln">
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
      <div class="col elegant-color-dark  text-warning ">
        <div class="quote">
          <p> '<strong>Самостоятельность</strong> - это способность купить сосиски не по акции.' (с) Адам Смит </p>
        </div>
        <div class="todoBanner text-center">
          <p> Выполняй задания и становись самостоятельным! </p>
        </div>
      </div>
    </div>
    <div class="row tasklist-head">
        <p class="col-sm-6 text-left font-weight-bold"> Задания </p>
        <p class="col-sm-6 text-right"> Выполнено сегодня: {{tasksDone}} </p>
    </div>
    <div class="row task shadow p-3 mb-5 bg-white" v-for="task in taskList" :key="task.text">
    </div>
    </div>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    nextPage: Function,
    taskCount: Number,
    coins: Number,
  },
  created(){
    console.log(this.taskList)
  },
  data(){
    return{
      checkList: [

      ],
    }
  },
  methods: {

  },
}
</script>

<style scoped>
  .poln{
    min-height: 100vh;
  }
</style>
