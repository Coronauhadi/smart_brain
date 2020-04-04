<template>
  <div class="container-fluid elegant-color-dark poln text-white text-center">
    <div class="row">
      <div class="col">
        <h1 class="heading">smart brain</h1>
        <div class="mt-10">

          <div class="buttw-1 mx-auto waves-effect waves-light " style="position: relative;">
            <div class="buttw-2 "></div>
            <span class="" style="position:absolute; top:28px; left:46px;">Стать самостоятельным</span>
          </div>

          <div class="buttd-1 mx-auto waves-effect waves-light " style="position: relative;">
            <div class="buttd-2 "></div>
            <span class="text-danger" style="position:absolute; top:28px; left:46px;">Стать самостоятельным</span>
          </div>
          <!-- <button type="button" class="butt text-white waves-effect waves-light" name="button"> Стать самостоятельным </button> -->
          <button type="button" class="butt-dang text-danger waves-effect waves-light mt-4" name="button">Остаться неудачником</button>
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
  .buttw-1{
    width: 316px;
    box-shadow: 0px 0px 15px #FFFFFF;
    font-size: 22px;
    border-radius: 10px;

  }
  .buttw-2{
    width: 316px;
    height: 90px;
    border: 6px solid #FFFFFF;
    box-shadow: inset 0px 0px 15px #FFFFFF;
    filter: blur(2px);
    border-radius: 10px;
  }
  .buttw-1{
    width: 316px;
    box-shadow: 0px 0px 15px #FFFFFF;
    font-size: 22px;
    border-radius: 10px;

  }
  .buttw-2{
    width: 316px;
    height: 90px;
    border: 6px solid #FFFFFF;
    box-shadow: inset 0px 0px 15px #FFFFFF;
    filter: blur(2px);
    border-radius: 10px;
  }
  .poln{
    min-height: 100vh;
  }
  .heading{
    /* font-weight: bold; */
    font-size: 70px;
    font-style: normal;
    margin-top: 40%;
  }
  .mt-10{
    margin-top: 150px;
  }

</style>
