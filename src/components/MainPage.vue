<template>
  <div class="container-fluid elegant-color-dark poln">

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

    <div class="row">
      <div class="col ">
        <div class="text-white my-2">
          <p style="font-size: 19px; font-width:200;"> 'Самостоятельность - это способность купить сосиски не по акции.' (с) Адам Смит </p>
        </div>
        <div class=" text-center my-4 text-warning">
          <b style="font-size: 23px; line-height: 22px; "> Выполняй задания, <br> становись самостоятельнее </b>
        </div>
      </div>
    </div>

    <div class="row tasklist-head  pt-4" style="margin-right:-5px; " >

      <div class="col-12 p-0">
        <div class="container-fluid p-0">

          <div class="row px-3">
            <div class="col-12 d-flex justify-content-between pl-3 pr-4" style="height:30px;">
              <p class=" text-left font-weight-light h4" style=""> ЗАДАНИЯ </p>
              <p class=" text-right" style="font-size: 18px;"> Выполнено всего: <b>{{tasksDone}}</b> </p>
            </div>
          </div>

            <div class="row mt-3 z-depth-1 mr-3" style="height:122px;">
              <div class="col-7">
                sad
              </div>
              <div class="col-5">
                sad
              </div>
            </div>
        </div>
      </div>


    </div>


    <!-- <div class="row task shadow p-3 mb-5 bg-white" v-for="task in taskList" :key="task.text">
      <p class="col-sm-4 text-left">{{task.text}}</p>
      <p class="col-sm-4 cost"> <img src="/res/coin.png" width="25" height="25" alt="Монетки:"> {{task.cost}} </p>
      <p class="col-sm-4 text-right"> <img :src="task.imglink" width="100" height="100"> </p>
    </div> -->


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
    min-height: 80vh;
    border-top-right-radius: 65px;
    background-color: white;
  }
  .task{
    background-color: white;
    /* color: #212121; */
    font-size: 20px;
    line-height: 0.8;
  }
  .cost{
    position:relative;
    bottom: -90px;
  }
</style>
