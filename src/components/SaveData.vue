<template>
  <div class="hello">
    asdas
  </div>
</template>

<script>
export default {
  name: 'SaveData',
  props: {
    nextPage: Function,
  },
  mounted(){
    console.log('save');

    const parsed = JSON.stringify(this.taskList)
    localStorage.setItem('taskList', parsed)

    const parsed2 = JSON.stringify(this.shopList)
    localStorage.setItem('shopList', parsed2)

    this.nextPage('MainPage')
    console.log('next');
  },
  data(){
    return{
      shopList: [
        {
          title:'Умение завязывать галстук',
          img: 'https://cdn.pixabay.com/photo/2015/03/26/09/41/tie-690084_960_720.jpg',
          url: 'https://www.youtube.com/watch?v=RZMsRcf43MI',
          price: 12,
          open: false,
        },
        {
          title:'Умение завязать шнурки',
          img: 'https://cdn.pixabay.com/photo/2017/02/08/16/01/business-2049312_960_720.jpg',
          url: 'https://www.youtube.com/watch?v=cXvfZyYV1no',
          price: 7,
          open: false,
        },
        {
          title:'Умение готовить яичницу',
          img: 'https://cdn.pixabay.com/photo/2019/06/10/15/53/egg-4264639_960_720.jpg',
          url: 'https://www.youtube.com/watch?v=vgfdAxcXdKY',
          price: 11,
          open: false,
        },
        {
          title:'Умение жарить мясо',
          img: 'https://cdn.pixabay.com/photo/2019/05/26/20/10/meat-4231141_960_720.jpg',
          url: 'https://www.youtube.com/watch?v=qeJC7ES_QHY',
          price: 19,
          open: false,
        },
        {
          title:'Умение наливать пиво',
          img: 'https://cdn.pixabay.com/photo/2018/05/31/16/51/glass-of-beer-3444480_960_720.jpg',
          url: 'https://www.youtube.com/watch?v=8Q47L1rP43c',
          price: 41,
          open: false,
        },

      ],
      taskList:[
      {
        text: 'Начать мыслить как самостоятельный человек',
        cost: 0,
        open: false,
        show: false,
        imglink: 'https://sun9-65.userapi.com/c858232/v858232718/1c2ac2/ifHMdhcUqMk.jpg',
        checkList: {
          stages:[
            {text: 'Спросите себя: “Мыслю ли я как самостоятельный человек?” и ответьте “да”, так как по-настоящему самостоятельный человек должен быть уверен в своей самостоятельности.',
            cleared: false,
            emojilink:'/res/самостоятельный/1.png',},
            {text: 'Перестаньте просить о помощи у знакомых, сядьте в укромный угол, где вас никто не достанет. Самостоятельным людям не нужны друзья.',
            cleared: false,
            emojilink:'/res/самостоятельный/2.png',},
            {text: 'Если вы не уверены, что мыслите как самостоятельный человек, начните мыслить, как самостоятельный человек, так как настоящий самостоятельный человек должен мыслить как самостоятельный человек.',
            cleared: false,
            emojilink:'/res/самостоятельный/3.png',},
          ],
          winner:{
            title: 'Просветлённый',
            text: 'Теперь вы знаете все секреты этого непонятного мира',
            img: 'https://cdn.pixabay.com/photo/2017/11/11/15/52/young-man-2939344_960_720.jpg',
          },
          done: false,
          reward: 23,
        },

      },

      {
        text: 'Начать управлять своими финансами',
        cost: 15,
        open: false,
        show: false,
        imglink: 'https://i.kym-cdn.com/photos/images/newsfeed/001/562/655/8fa.jpg',
        checkList: {
          stages:[
            {text: 'Знаете ли вы, сколько тратите в месяц? Составьте список доходов и расходов, чтобы понять, какие статьи можно сократить.',
            cleared: false,
            emojilink:'/res/финансы/1.png',},
            {text: 'В первую очередь стоит сократить расходы на тарифы жкх, ведь самостоятельные люди добывают воду и газ из недр земли.',
            cleared: false,
            emojilink:'/res/финансы/2.png',},
            {text: 'Чтобы сэкономить на электричестве, просто проведите провод из подъездного трансформатора к себе домой.',
            cleared: false,
            emojilink:'/res/финансы/3.png',},
          ],
          winner:{
            title: 'Финансист',
            text: 'Теперь вам не страшны никакие кризисы',
            img: 'https://forex-invest.tv/images/stories/doveritelnoe-upravlenie/spisok-brokerov-foreks-s-pamm-schetami-1b.jpeg',
          },
          done: false,
          reward: 26,
        },

      },

      {
        text: 'Начать заниматься спортом',
        cost: 13,
        open: false,
        show: false,
        imglink: 'https://pbs.twimg.com/media/ECcJDmkX4AAfA7M.jpg',
        checkList: {
          stages:[
            {text: 'Самостоятельный человек должен поддерживать свое тело в тонусе. Встаньте пораньше, отложите зарядку и ложитесь спать дальше. В здоровом теле - здоровый дух.',
            cleared: false,
            emojilink:'/res/финансы/1.png',},
            {text: 'Запишитесь в спортзал. Ходить необязательно.',
            cleared: false,
            emojilink:'/res/финансы/2.png',},
            {text: 'Если вы всё-таки сходили в спортзал, убедитесь, что у вас ничего не получается, и бросьте эту затею.',
            cleared: false,
            emojilink:'/res/финансы/3.png',},
          ],
          winner:{
            title: 'Спортсмен',
            text: 'В здоровом теле - здоровый дух',
            img: 'https://econet.ru/uploads/pictures/298439/content_11_1__econet_ru.jpg',

          },
          done: false,
          reward: 19,
        },

      },


      {
        text: 'Стать самодостаточным',
        cost: 18,
        open: false,
        show: false,
        imglink: 'https://i.kym-cdn.com/photos/images/original/001/562/654/1fd.jpg',
        checkList: {
          stages:[
            {text: 'Возьмите за привычку искать виноватых. Если виноваты вы, оборачивайте обстоятельства в свою пользу. Люди не любят виноватых, а вам не нужно быть на плохом счету у других.',
            cleared: false,
            emojilink:'/res/самодостаточность/1.png',},
            {text: 'Если начальник просит вас о чём-нибудь, не постесняйтесь выполнить его просьбу, раз уж он завидует вашей самостоятельности. Если же вас попросит о помощи коллега или младший сотрудник, не спешите ему помогать, ведь вам нужно беречь свои силы.',
            cleared: false,
            emojilink:'/res/самодостаточность/2.png',},
            {text: 'Если вас просят срочно выполнить какую-то работу, не спешите этим заниматься, если на кону не стоит ваше повышение. Самодостаточный и самостоятельный человек сам решит, когда ему стоит взяться за дело.',
            cleared: false,
            emojilink:'/res/самодостаточность/3.png',},
          ],
          winner:{
            title: 'Циник и мизантроп',
            text: 'Интересно, почему люди на меня так смотрят?',
            img: 'https://avatars.mds.yandex.net/get-zen_doc/1909059/pub_5d28df68f0d4f400afcbd9e9_5d28e763d11ba200ac67487c/scale_1200',
          },
          done: false,
          reward: 40,
        },

      },

      {
        text: 'Начать готовить самому себе ',
        cost: 30,
        open: false,
        show: false,
        imglink: 'https://ak0.picdn.net/shutterstock/videos/1013024960/thumb/1.jpg',
        checkList: {
          stages:[
            {text: 'Посмотрите рецепт в интернете и постарайтесь его приготовить. Поняв, что это не ваше, откладывайте готовку всякий раз.',
            cleared: false,
            emojilink:'/res/готовить/1.png',},
            {text: 'Пересмотрите статьи расходов и решите, что пользоваться службой доставки - не такая уж и плохая идея.',
            cleared: false,
            emojilink:'/res/готовить/2.png',},

          ],
          winner:{
            title: 'Повар',
            text: 'С мазиком пойдёт',
            img: 'https://avatars.mds.yandex.net/get-pdb/2295191/d117cafe-a8c6-4a59-8ea2-e831a217f7ef/s1200?webp=false',
          },
          done: false,
          reward: 54,
        },

      },

      {
        text: 'Начать учиться чему-то новому',
        cost: 14,
        open: false,
        show: false,
        imglink: 'https://i.ytimg.com/vi/owbV7eAlaDE/maxresdefault.jpg',
        checkList: {
          stages:[
            {text: 'Подпишитесь на все научпоп каналы на ютубе и читайте книжки по саморазвитию.',
            cleared: false,
            emojilink:'/res/учиться/1.png',},
            {text: 'Начните ходить на тренинги по личностному росту. Другой человек разберётся в вас и вашем кошельке гораздо лучше вас самих!',
            cleared: false,
            emojilink:'/res/учиться/2.png',},
            {text: 'Потеряв деньги, не отчаивайтесь. Следующий тренинг вас научит не попадаться в такие шарлатанские схемы.',
            cleared: false,
            emojilink:'/res/учиться/3.png',},
          ],
          winner:{
            title: 'Бизнес',
            text: 'Речь идёт о трёхзначных суммах',
            img: 'https://marketologist.today/assets/images/resources/32/russkoe-chudo.jpg',
          },
          done: false,
          reward: 5,
        },

      },

      {
        text: 'Начать одеваться самостоятельно',
        cost: 37,
        open: false,
        show: false,
        imglink: 'https://avatars.mds.yandex.net/get-pdb/404799/25e23fc6-a07e-4788-a8ea-a37036b9ec76/s1200',
        checkList: {
          stages:[
            {text: 'Если вы ещё не умеете завязывать шнурки - пора этому научиться. Найдите пару руководств на wikihow, поймите, что мелкая моторика - это не так-то просто и носите обувь на липучках.',
            cleared: false,
            emojilink:'/res/самостоятельный/1.png',},
            {text: 'Покупайте только ту одежду, которую увидели в рекламе. Дороже - значит лучше. Даже с бахромой. Даже с узором с бабушкиного ковра.',
            cleared: false,
            emojilink:'/res/самостоятельный/2.png',},
            {text: 'Если вашу одежду необходимо подшить - не торопитесь браться за нитки и иголку. Умные люди для этих целей придумали скотч. (Если вам кажется, что одежда держится неуверенно, значит, вы использовали недостаточно скотча)',
            cleared: false,
            emojilink:'/res/самостоятельный/3.png',},
          ],
          winner:{
            title: 'Модник',
            text: 'Хм.... Мама сказала симпотяга.',
            img: 'https://mtdata.ru/u1/photoA316/20958923256-0/original.jpg',
          },
          done: false,
          reward: 50,
        },

      },

    ],
    }
  },
  methods: {

  },
}
</script>

<style scoped>

</style>
