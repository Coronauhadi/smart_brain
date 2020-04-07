<template>
  <div class="container-fluid z-depth-2 white navs">
    <div class=" row pt-1" style="">

        <div class="h50 col text-center bor " @click="openpage('PricePage')">
        <div class="d-flex flex-column mt-2">
          <!-- <i class="far  fa-lg fa-list-alt"></i> -->
          <!-- <i class="far  fa-list-alt"></i> -->
          <i :class="'fas fa-lg fa-award '+(nameMenu=='PricePage'?'cl':'') "></i>
          <small :class="' '+(nameMenu=='PricePage'?'cl':'')">Достижения</small>
        </div>
      </div>
      <div class="h50 col text-center bor " @click="openpage('MainPage')">
        <div class="d-flex flex-column mt-2">
          <i :class="'fas  fa-lg fa-brain '+(nameMenu=='MainPage'?'cl':'')"></i>
          <small :class="' '+(nameMenu=='MainPage'?'cl':'')">Задания</small>
        </div>
      </div>
      <div class="h50 col text-center bor " @click="openpage('ShopPage')">
        <div class="d-flex flex-column mt-2">
          <i :class="'fas fa-lg fa-warehouse '+(nameMenu=='ShopPage'?'cl':'') "></i>
          <small :class="' '+(nameMenu=='ShopPage'?'cl':'')">Магазин</small>
        </div>
      </div>
      <div class="h50 col text-center bor " @click="openpage('ProfilePage')">
        <div :class="'d-flex flex-column mt-2 '+(nameMenu=='ProfilePage'?'cl':'') ">
          <i :class="'far fa-lg fa-list-alt '+(nameMenu=='ProfilePage'?'cl':'')"></i>
          <small :class="' '+(nameMenu=='ProfilePage'?'cl':'')">Профиль</small>
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
      nameMenu: 'MainPage'
    }
  },
  methods: {
    openpage(page){
      this.nextPage(page)
      this.nameMenu = page
    },
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
