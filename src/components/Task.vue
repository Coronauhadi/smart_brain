<template>
  <div class="container-fluid white poln">
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
        <button type="button" @click="task.show = false" class="btn shadow-sm btn-white text-black goback"><img src="/res/backArrow.png" width="15" height="15" alt=""> Вернуться назад </button>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <p class="text-center task-title"> {{title}} </p>
      </div>
    </div>
    <div class="row task p-3 bg-white" @click="stage.cleared = true" v-for="stage in task.checkList.stages" :key="stage.text">
      <ul class="list-group list-group-horizontal list-group-flush">
        <!-- <li class="list-group-item" :style="stage.cleared? checkedstyle : {}"> -->
          <!-- <input type="checkbox" class="chckbox" :disabled="stage.cleared" v-model="stage.cleared"> -->
        <!-- </li> -->
        <li class="list-group-item " :style="stage.cleared? checkedstyle : {}">{{stage.text}} <br> <img class="emoji" :src="stage.emojilink" width="65" height="65" alt=""> </li>
      </ul>
    </div>
    </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object,
    coins: Number,
  },
  created(){
    this.title = this.task.title
  },
  data(){
    return{
      // coins: 10,
      checkedstyle:{"background":"rgba(216, 216, 216, 0.5)",},
      title: '',
      // checkList: [
        // {
        //   title: 'Начать мыслить как самостоятельный человек',
        //   stages:[
        //     {text: 'Спросите себя: “Мыслю ли я как самостоятельный человек?” и ответьте “да”, так как по-настоящему самостоятельный человек должен быть уверен в своей самостоятельности.',
        //     cleared: false,
        //     emojilink:'https://developers.redhat.com/blog/wp-content/uploads/2019/04/Thinking-Emoji.png'},
        //     {text: 'Перестаньте просить о помощи у знакомых, сядьте в укромный угол, где вас никто не достанет. Самостоятельным людям не нужны друзья.',
        //     cleared: false,
        //     emojilink:'https://im0-tub-ru.yandex.net/i?id=d2e3c74eb436aed4cb89579970994f74&n=13',},
        //     {text: 'Если вы не уверены, что мыслите как самостоятельный человек, начните мыслить, как самостоятельный человек, так как настоящий самостоятельный человек должен мыслить как самостоятельный человек.',
        //     cleared: false,
        //     emojilink:'https://im0-tub-ru.yandex.net/i?id=41324c8cd773db02f9a0fd3a1ee54b36&n=13',},
        //   ],
        //   done: false,
        //   reward: 10,
        // },

      // ],
    }
  },
  methods: {

  },
}
</script>

<style scoped>
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
    border: none;
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
    font-weight: 500;
    font-size: 25px;
    line-height: 29px;
  }
</style>
