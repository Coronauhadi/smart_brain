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
      <div class="col elegant-color-dark  text-warning text-center">
        <div class="quote">
          <p> '<strong>Самостоятельность</strong> - это способность купить сосиски не по акции.' (с) Адам Смит </p>
        </div>
        <div class="todoBanner">
          <p> Выполняй задания и становись самостоятельным! </p>
        </div>
      </div>
    </div>
    <div class="row tasklist-head">
        <strong class="col-md-1 text-left font-weight-bold"> Задания </strong>
        <p class="col-md-11 text-right"> Выполнено сегодня: {{tasksDone}} </p>
    </div>
      <div class="row task shadow p-3 mb-5 bg-white">
        <div class="col">
          <ul class="list-group-flush">
         <li class="list-group-item" :v-for="task in taskList">
           {{task.text}}
         </li>
       </ul>
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
  created(){
    console.log('hooked')
    this.taskList.push(this.task1)
    this.taskList.push(this.task2)
    for(let i=0;i<this.taskList.length;i++){
      console.log(this.taskList)
    }
  },
  data(){
    return{
      coins: 0,
      tasksDone: 0,
      taskList:[],
      task1: {
        text: "Начать мыслить как самостоятельный человек",
        cost: "Бесплатно",
        imglink: "https://sun9-65.userapi.com/c858232/v858232718/1c2ac2/ifHMdhcUqMk.jpg",
      },
      task2: {
        text: "Начать мыслить как самостоятельный человек",
        cost: "Бесплатно",
        imglink: "https://sun9-65.userapi.com/c858232/v858232718/1c2ac2/ifHMdhcUqMk.jpg",
      },
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
    background-color: white;
    color: #212121;
  }
</style>
