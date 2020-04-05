<template>
  <div class="container-fluid elegant-color-dark poln text-white text-center">
    <div class="row">
      <div class="col">
        <h1 class="heading">smart brain</h1>
        <div class="mt-10">

          <div class="buttw-1 mx-auto waves-effect waves-light " @click="nextPage('StatPage')" style="position: relative;">
            <div class="buttw-2 "></div>
            <span class="st" style="">Стать самостоятельным</span>
          </div>

          <div class="buttd-1 mt-4 mx-auto waves-effect waves-light " style="position: relative;">
            <div class="buttd-2 "></div>
            <span class="text-danger st" style="">Остаться неудачником</span>
          </div>
          <!-- <button type="button" class="butt text-white waves-effect waves-light" name="button"> Стать самостоятельным </button> -->
          <!-- <button type="button" class="butt-dang text-danger waves-effect waves-light mt-4" name="button">Остаться неудачником</button> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloPage',
  props: {
    nextPage: Function,
  },
  data(){
    return{

    }
  },
  methods: {

  },
}
</script>

<style scoped>
  .st{
    width: 80%;
    position:absolute;
    /* top:28px; */
    /* left:65px; */
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
  .buttd-1{
    width: 90%;
    box-shadow: 0px 0px 15px #FF4444;
    font-size: 22px;
    border-radius: 7px;

  }
  .buttd-2{
    width: 100%;
    height: 90px;
    border: 6px solid #FF4444;
    box-shadow: inset 0px 0px 15px #FF4444;
    filter: blur(1px);
    border-radius: 7px;
  }
  .poln{
    min-height: 100vh;
  }
  .heading{
    /* font-weight: bold; */
    font-size: 70px;
    font-style: normal;
    margin-top: 100px;
  }
  .mt-10{
    margin-top: 150px;
  }

</style>
