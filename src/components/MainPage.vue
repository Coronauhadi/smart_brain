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
      <p class="col-sm-4 text-left">{{task.text}}</p>
      <p class="col-sm-4 cost"> <img src="/res/coin.png" width="25" height="25" alt="Монетки:"> {{task.cost}} </p>
      <p class="col-sm-4 text-right"> <img :src="task.imglink" width="100" height="100"> </p>
    </div>
    </div>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    nextPage: Function,
  },
  created(){
    console.log(this.taskList)
  },
  data(){
    return{
      coins: 0,
      tasksDone: 0,
      taskList:[
      {
        text: 'Начать мыслить как самостоятельный человек',
        cost: 'Бесплатно',
        imglink: 'https://sun9-65.userapi.com/c858232/v858232718/1c2ac2/ifHMdhcUqMk.jpg',
      },
      {
        text: 'Начать',
        cost: 'платно',
        imglink: 'https://sun9-65.userapi.com/c858232/v858232718/1c2ac2/ifHMdhcUqMk.jpg',
      },
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
  .container-fluid{
    /* background-color: #212121; */
  }
  .tasklist-head{
    border-top-right-radius: 65px;
    border: 5vh solid white;
    background-color: white;
    color: #212121;
  }
  .task{
    margin: 1px -15px;
    background-color: white;
    color: #212121;
  }

  .cost{
    position:relative;
    bottom: -90px;
  }
</style>
