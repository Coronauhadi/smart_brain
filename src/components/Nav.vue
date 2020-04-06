<template>
  <div class="container-fluid z-depth-2 white navs">
    <div class=" row pt-1" style="">

      <div class="h50 col text-center bor ">
        <div class="d-flex flex-column mt-2">
          <!-- <i class="far  fa-lg fa-list-alt"></i> -->
          <!-- <i class="far  fa-list-alt"></i> -->
          <i class="fas fa-lg fa-award"></i>
          <small class="">Достижения</small>
        </div>
      </div>
      <div class="h50 col text-center bor ">
        <div class="d-flex flex-column mt-2">
          <i class="fas cl fa-lg fa-brain"></i>
          <small class="cl">Задания</small>
        </div>
      </div>
      <div class="h50 col text-center bor ">
        <div class="d-flex flex-column mt-2">
          <i class="fas fa-lg fa-warehouse"></i>
          <small class="">Магазин</small>
        </div>
      </div>
      <div class="h50 col text-center bor ">
        <div class="d-flex flex-column mt-2">
          <i class="far  fa-lg fa-list-alt"></i>
          <small class="">Профиль</small>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav',
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
  .bor{

  }
  .cl{
    color:#FF8800;
  }
  .navs{

    position: fixed;
    height: 50px;
    bottom: 0;
    left: 0;
    z-index: 80;
    width: 100%;
  }
  .h50{
    height: 50px;
  }
</style>
