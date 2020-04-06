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
    <div class="row tasklist-head   slow fadeInUp pt-4" style="margin-right:-5px; " >


      <div class="col-12 p-0 position-static">
        <div class="container-fluid pb-5">


          <div class="row px-3">
            <div class="col-12 d-flex justify-content-between pl-0 pr-3" style="height:30px;">
              <p class=" text-left font-weight-light h4" style=""> ЗАДАНИЯ </p>
              <p class=" text-right" style="font-size: 18px;"> Выполнено всего: <b>{{tasksDone}}</b> </p>
            </div>
          </div>
<!-- animated -->
            <div v-for="task in taskList" :key="task.name"  class="row mt-3 z-depth-1 mr-0  an" :style="task.styles">

              <div class="ms" v-if="task.show"  style="position:fixed; height:100%; width:100%; top:0; left:0; overflow-y: scroll; z-index:99;">
                <Task class=" " :task="task" :coins="coins" />
              </div>

              <!-- <div class=" task-preloud an" v-if="task.show " :style="task.styles" ></div> -->
              <!-- <div class=" task-preloud "  :style="task.styles" ></div> -->



              <div class="col pr-3 pt-3 pl-3 pb-0 position-relative" @click="task.show = true ">
                <p class="lead m-0">{{task.text}}</p>
                <p class="text-right m-0 mt-1" style="position:absolute; bottom:0px; right:10px;"> <b>{{task.cost==0?'Бесплатно':task.cost}}</b>
                  <img src="/res/coin.png" style="width:27px;" alt="">
                  <!-- <img src="/res/lock.png" style="width:27px;" alt=""> -->

                </p>
              </div>
              <div class="" @click="task.show = true "  :style="'background: url('+task.imglink+'); background-size:cover; width:100px;background-position: center;'">  </div>

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
    // console.log(this.taskList)
    if (localStorage.taskList) {
      this.taskList = localStorage.taskList
    }
    if (localStorage.coins) {
      this.coins = localStorage.coins
    }
  },
  methods: {

  },
  data(){
    return{
      coins: 0,
      tasksDone: 0,
      taskList:[
      {
        text: 'Начать мыслить как самостоятельный человек',
        cost: '0',
        open: false,
        show: false,
        styles: {top: 0,},
        imglink: 'https://sun9-65.userapi.com/c858232/v858232718/1c2ac2/ifHMdhcUqMk.jpg',
        checkList: {
          stages:[
            {text: 'Спросите себя: “Мыслю ли я как самостоятельный человек?” и ответьте “да”, так как по-настоящему самостоятельный человек должен быть уверен в своей самостоятельности.',
            cleared: false,
            emojilink:'https://developers.redhat.com/blog/wp-content/uploads/2019/04/Thinking-Emoji.png'},
            {text: 'Перестаньте просить о помощи у знакомых, сядьте в укромный угол, где вас никто не достанет. Самостоятельным людям не нужны друзья.',
            cleared: false,
            emojilink:'https://im0-tub-ru.yandex.net/i?id=d2e3c74eb436aed4cb89579970994f74&n=13',},
            {text: 'Если вы не уверены, что мыслите как самостоятельный человек, начните мыслить, как самостоятельный человек, так как настоящий самостоятельный человек должен мыслить как самостоятельный человек.',
            cleared: false,
            emojilink:'https://im0-tub-ru.yandex.net/i?id=41324c8cd773db02f9a0fd3a1ee54b36&n=13',},
          ],
          done: false,
          reward: 10,
        },

      },
      {
        text: 'Начать управлять своими финансами',
        cost: '10',
        open: false,
        imglink: 'https://i.kym-cdn.com/photos/images/newsfeed/001/562/655/8fa.jpg',
      },
      {
        text: 'Начать заниматься спортом',
        cost: '20',
        open: false,
        imglink: 'https://pbs.twimg.com/media/ECcJDmkX4AAfA7M.jpg',
      },
      {
        text: 'Стать самодостаточным',
        cost: '20',
        open: false,
        imglink: 'https://i.kym-cdn.com/photos/images/original/001/562/654/1fd.jpg',
      },
      {
        text: 'Начать готовить самому себе ',
        cost: '20',
        open: false,
        imglink: 'https://ak0.picdn.net/shutterstock/videos/1013024960/thumb/1.jpg',
      },
      {
        text: 'Начать учиться чему-то новому',
        cost: '20',
        open: false,
        imglink: 'https://i.ytimg.com/vi/owbV7eAlaDE/maxresdefault.jpg',
      },
    ],
    }
  },
  watch:{
    
  }

}
</script>

<style scoped>
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
  .container-fluid{
    /* background-color: #212121; */
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
