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
<!-- animated -->
    <div class="row tasklist-head  fadeInUp pt-4" style="margin-right:-5px; " >


      <div class="col-12 p-0 position-static">
        <div class="container-fluid pb-5">

          <div class="alert alert-danger text-center z-depth-2 animated fadeInUp faster " v-if="nocaoins" style="position:fixed!important; bottom:20px; left:15%; width:70%; z-index: 1000;" role="alert">
            У вас не хватает монет
          </div>

          <div class="row px-3">
            <div class="col-12 d-flex justify-content-between pl-0 pr-3" style="height:30px;">
              <h1 class=" text-left  h3" style=""> ЗАДАНИЯ </h1>
              <p class=" text-right" style="font-size: 18px;"> Выполнено всего: <b>{{tasksDone}}</b> </p>
            </div>
          </div>

            <div v-for="task in taskList" :key="task.name"   class="row mt-3 depth  mr-0  an position-relative" :style="task.styles">
              <div v-if="task.checkList.done==true" class="position-absolute h-100 w-100 rgba-stylish-light " style="z-index:60;"></div>

              <div class="ms" v-if="task.show"  style="position:fixed; height:100%; width:100%; top:0; left:0; overflow-y: scroll; z-index:99;">
                <Task class=" " :task="task" :save="save" :close="close" :addCoins="addCoins" :coins="coins" />
              </div>

              <div class="col pr-3 pt-3 pl-3 pb-0 position-relative" @click="openTask(task)">
                <p class="lead m-0">{{task.text}}</p>
                <p class="text-right m-0 mt-1" style="position:absolute; bottom:0px; right:10px;"> <b>{{task.cost==0?'Бесплатно':task.cost}}</b>
                  <img src="/res/coin.png" style="width:27px;" alt="">

                </p>
              </div>
              <div class="" @click="openTask(task)"  :style="'background: url('+task.imglink+'); background-size:cover; width:100px;background-position: center;'">  </div>

            </div>

        </div>
      </div>

    </div>




    </div>
</template>

<script>

import Task from './Task.vue'

export default {
  name: 'MainPage',
  components:{
    Task,
  },
  props: {
    nextPage: Function,
  },
  created(){

    if (localStorage.taskList) {
      try {
        this.taskList = JSON.parse(localStorage.getItem('taskList'));
      } catch(e) {
        localStorage.removeItem('taskList');
      }
    }

    if (localStorage.coins) {
      this.coins = Number(localStorage.coins)
    }
    if (localStorage.tasksDone) {
      this.tasksDone = Number(localStorage.tasksDone)
    }
  },
  methods: {
    save: function() {
      const parsed = JSON.stringify(this.taskList);
      localStorage.setItem('taskList', parsed);
      localStorage.coins = this.coins
      localStorage.tasksDone = this.tasksDone
    },
    openTask(task){
      if (task.open) {
        task.show = true
        this.scroll = false
      }else {
        if (task.cost<= this.coins) {
          this.coins -= task.cost
          task.open = true
          task.show = true
          this.scroll = false
          this.save()
        }else{
          this.nocaoinsAnim()
        }
      }
    },
    close(task){
      task.show = false
      this.scroll = true
      this.tasksDoneSet()
      this.save()
    },
    addCoins(coin){
      this.coins += coin
      localStorage.coins = this.coins
    },
    tasksDoneSet(){
      let a = 0
      for (var i = 0; i < this.taskList.length; i++) {
        if (this.taskList[i].checkList.done == true) {
          a++
        }
      }
      this.tasksDone = a
      localStorage.tasksDone = a
    },
    nocaoinsAnim(){
      this.nocaoins = true
      setTimeout(()=>{this.nocaoins = false}, 4000)
    },


  },
  data(){
    return{
      coins: 10,
      tasksDone: 0,
      nocaoins: false,
      scroll: true,
      taskList:[],
    }
  },
  watch:{
    scroll: function(bol){
      let body = document.getElementsByTagName('body')
      if (!bol) {
        body[0].style.overflow = 'hidden'
      }else {
        body[0].style.overflow = 'auto'
      }
    },
  },


}
</script>

<style scoped>
  .depth{
    box-shadow: 1px 1px 10px #0000001c;
  }
  .task-preloud{
    position: absolute;
    background: white;
    height: 110px;
    width: 100%;
    z-index: 100;
    opacity: 0;
  }
  .an{
    min-height:110px;
  }
  .animated{
    position: static!important;
    animation-fill-mode: backwards;
  }
  .poln{
    min-height: 100vh;
  }

  .tasklist-head{
    min-height: 75vh;
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
