<template>
  <div class="container-fluid elegant-color-dark poln text-white text-center">
    <div class="row">
      <div class="col">
        <h1 class="heading ">Насколько по <br> 3-балльной шкале вы самостоятельный человек?</h1>
        <div class="d-flex justify-content-around mt-5">
          <a @click="nextPage('AgePage')"  class="btn-outline-white btn-lg waves-effect waves-light  px-4 " >1</a>
          <a @click="nextPage('AgePage')"  class="btn-outline-white btn-lg waves-effect waves-light  px-4  " >2</a>
          <a @click="nextPage('AgePage')"  class="btn-outline-white btn-lg waves-effect waves-light  px-4  " >3</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StatPage',
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
  .poln{
    min-height: 100vh;
  }
  .heading{
    margin-top: 80px;
    font-size: 55px;
  }
  a{
    font-size: 35px;
  }
</style>
