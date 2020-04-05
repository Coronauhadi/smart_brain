<template>
  <div class="container-fluid elegant-color-dark poln text-white text-center">
    <div class="row">
      <div class="col">
        <h1 class="heading" v-if="stat!=4">Когда у вас день рождения?</h1>
        <h1 class="heading" v-else>Возможно наше приложение не сделает вас самостоятельным. Так как вы {{znak}}.</h1>
        <div v-if="stat!=4" class="d-flex justify-content-around ">
          <span class="sp" id="d1" @click="stat=1">год</span>
          <span class="sp" id="d2" @click="stat=2">месяц</span>
          <span class="sp" id="d3" @click="stat=3">день</span>
          <hr class="anim" :style="cor">
        </div>

        <div class="buttw-1 mx-auto waves-effect waves-light mt-5" @click="nextPage('MainPage')" v-if="stat==4"  style="position: relative;">
          <div class="buttw-2 "></div>
          <span class="st" style="">все равно попытаться</span>
        </div>

        <div class="d-flex justify-content-between flex-wrap mt-5" v-if="stat==1"  style="">
          <a v-for="year in yearsAr" @click="years = year; stat = 2" :key="year.name" class="btn-outline-white btn-sm rounded yars mx-1 mt-2 py-2" >{{year}}</a>
        </div>
        <div class="d-flex justify-content-between flex-wrap mt-5" v-if="stat==2"  style="">
          <a v-for="(m, index) in mesAr" @click="mes = index+1; stat = 3" :key="m.name" class="btn-outline-white rounded mess mx-1 mt-2 py-2" >{{m}}</a>
        </div>
        <div class="d-flex justify-content-center flex-wrap mt-5" v-if="stat==3"  style="">
          <a v-for="(d) in dayAr" @click="day = d; stat = 4" :key="d.name" class="btn-outline-white btn-sm rounded day mx-1 mt-2" >{{d}}</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AgePage',
  props: {
    nextPage: Function,
  },
  mounted(){
    this.getCoords(this.stat)
    this.setYear()
    this.setDay()
  },
  data(){
    return{
      dayAr: [],
      mesAr: ['январь', 'февраль', 'март', 'апрель', 'май', 'июнь', 'июль', 'август', 'сентябрь', 'октябрь', 'ноябрь', 'декабрь'],
      yearsAr: [],
      day: '1',
      mes: '11',
      years: '2000',
      znak: '',
      stat: 1,
      cor: {
        bottom: '-10px',
        left: '10px'
      },

    }
  },
  methods: {
    getCoords: function(val) {
      let elem = document.getElementById('d'+val)
      let box = elem.getBoundingClientRect();
      this.cor.width = elem.offsetWidth +'px'
      this.cor.top = box.top + pageYOffset + 40 +'px'
      this.cor.left = box.left + pageYOffset  +'px'
    },
    setYear: function() {
      for (var i = 1990; i < 2020; i++) {
        this.yearsAr.push(i)
      }
    },
    setDay: function() {
      this.dayAr = []
      let days = 32 - new Date(this.years, this.mes-1, 32).getDate();
      for (var i = 1; i < days+1; i++) {
        this.dayAr.push(i)
      }
    },
    znakZ: function(d, m) {
        let aTmp = [
            [1, 'iWwWj'],
            [19, 'Козерог'],
            [18, 'Водолей'],
            [20, 'Рыбы'],
            [19, 'Овен'],
            [20, 'Телец'],
            [21, 'Близнецы'],
            [22, 'Рак'],
            [22, 'Лев'],
            [22, 'Дева'],
            [22, 'Весы'],
            [22, 'Скорпион'],
            [21, 'Стрелец']
        ];
        if (d < 1 || d > 31) {
            m = 0;
            d = 0;
        }
        if (m < 1 || m > 12) {
            m = 0;
            d = 0;
        }
        if (d > aTmp[m][0]) m += 1;
        if (m > 12) m = 1;
        return aTmp[m][1];
    }


  },
  watch:{
    stat: function(val) {
      if (val < 4) {
        this.getCoords(val)
      }
      if (val == 4) {
        this.znak = this.znakZ(this.day, this.mes)
      }
    },
  mes: function(val) {
    val
    this.setDay()
  }
  }
}
</script>

<style scoped>
  .st{
    width: 80%;
    position:absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    -moz-transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
    -o-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }
  .buttw-1{
    width: 90%;
    box-shadow: 0px 0px 15px #FFFFFF;
    font-size: 22px;
    border-radius: 7px;

  }
  .buttw-2{
    width: 100%;
    height: 90px;
    border: 6px solid #FFFFFF;
    box-shadow: inset 0px 0px 15px #FFFFFF;
    filter: blur(1px);
    border-radius: 7px;
  }
  .yars{
    width: 60px;
    font-size: 20px;
  }
  .mess{
    width: 100px;
    font-size: 24px;
  }
  .day{
    width: 60px;
    font-size: 24px;
  }
  .anim{
    transition: all 0.5s ease;
  }
  .poln{
    min-height: 100vh;
  }
  .heading{
    margin-top: 50px;
    font-size: 55px;
  }
  a{
  }
  .sp{
    /* font-family: Raleway; */
    font-size: 40px;
  }
  .stat{
    position: relative;
  }
  hr{
    position: absolute;
    bottom: -10px;
    left: 10px;
    color: white;
    width: 83px;
    border-top: 5px solid red;
  }
</style>
