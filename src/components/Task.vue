<template>
  <div class="">
    <div class="container-fluid white poln" v-if="!Win">
      <header class="row">
        <nav class="col white text-black">
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
        <div class="col">
          <button type="button" @click=" close(task) " class="btn shadow-sm btn-white text-black goback"><img src="/res/backArrow.png" width="15" height="15" alt=""> Вернуться назад </button>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <p class="text-center mt-4 task-title"> {{title}} </p>
        </div>
      </div>
      <div class="row task p-3 bg-white" @click="sheck(stage); save() " v-for="(stage, index) in task.checkList.stages" :key="stage.text">
        <ul class="list-group list-group-horizontal list-group-flush mb-3">
          <li class="list-group-item z-depth-1" :style="stage.cleared? checkedstyle : ' background:#00000008;'">
            <b>{{index+1+'. '}}</b> {{stage.text}} <br>
            <img class="emoji" :src="stage.emojilink" width="65" height="65" alt="">
          </li>

        </ul>
      </div>
    </div>

    <div class="container-fluid poln" :style="'background:url('+task.checkList.winner.img+'); background-position:center; background-size: cover; '" v-if="Win">
      <div class="row rgba-black-light text-white" style="height:100vh;">
        <div class="col text-center">
          <h5 class=" " style="margin-top:5vh;">Достижение получено</h5>
          <p class="" style="font-size:50px!important; margin-top:5vh;"><b>{{task.checkList.winner.title}}</b> </p>
          <p class="" style="font-size:30px!important; margin-top:10vh;">{{task.checkList.winner.text}}</p>
          <p class="" style="font-size:30px!important; margin-top:5vh;"><b>+{{task.checkList.reward}}</b> <img src="/res/coin.png" class="mb-1" width="45" height="45" alt="Монетки:"></p>
          <button type="button" @click="close(task);addCoins(task.checkList.reward);" class="btn rgba-white-strong black-text  btn-lg rounded w-75 py-4 " style="font-size:20px; position:absolute; bottom:20px; left: 12%" name="button">Я молодец</button>
        </div>
      </div>
    </div>

    <!-- <Winner v-if="!Win"/> -->
  </div>
</template>

<script>
// import Winner from './Winner.vue'


export default {
  name: 'Task',
  components: {
    // Winner,
  },
  mounted(){
    if (localStorage.winnerArr) {
      try {
        this.winnerArr = JSON.parse(localStorage.getItem('winnerArr'));
      } catch(e) {
        localStorage.removeItem('winnerArr');
      }
    }

  },
  props: {
    task: Object,
    save: Function,
    coins: Number,
    close: Function,
    addCoins: Function,
  },
  created(){
    this.title = this.task.text
  },
  data(){
    return{
      checkedstyle:{"background":"#69f0ae",},
      title: '',
      Win: false,
      winnerArr:[],
    }
  },
  methods: {
    sheck(stage){
      stage.cleared = true
      let don = 0
      for (var i = 0; i < this.task.checkList.stages.length; i++) {
        this.task.checkList.stages[i].cleared
        if(this.task.checkList.stages[i].cleared == true){
          don++
        }
      }
      if (don == this.task.checkList.stages.length) {
        this.task.checkList.done = true
        this.Win = true
        this.winnerArr.push(this.task.checkList.winner)
        const parsed = JSON.stringify(this.winnerArr)
        localStorage.setItem('winnerArr', parsed)
      }
    }
  },
}
</script>

<style scoped>

  .bg{
    background:url('https://cdn.pixabay.com/photo/2017/11/11/15/52/young-man-2939344_960_720.jpg');
    background-position:center;
    background-size: cover;
  }
  .goback{
    padding: 0.6em;
    font-size: 16px;
    line-height: 19px;
    margin: 35px, 5px, 0, 21px;
    border-radius: 0px 65px 65px 0px;
  }
  .poln{
    min-height: 100vh;
  }

  .chckbox{
    width: 35px;
    height: 35px;
    margin: -10px;
    position:relative;
    top: 15px;
    color: green;
  }

  .list-group-item{
    border-radius: 10px!important;
    font-size: 24px;
    /* border: none; */
  }

  .navbar-brand{
    font-family: 'Oswald', sans-serif;
    font-weight: bold;
    font-size: 16px;
    line-height: 29px;
    display: flex;
    align-items: center;
    text-align: center;
  }

  .emoji{
    position: relative;
    right: -160px;
  }

  .task-title{
    font-family: 'Oswald', sans-serif;
    font-weight: 400;
    font-size: 30px;
    line-height: 29px;
  }
</style>
