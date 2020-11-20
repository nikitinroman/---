<template>
  <div class="bigDiv">
    <a name="github"></a>
    <h1 style="text-align: center;">Моя главная цель- сделать как можно больше и как можно лучше.</h1>
    <Card :about-me-list="projectsList" :window-top="windowTop" :window-top-val="2100"></Card>
  </div>
</template>

<script>
import Card from './Card'

export default {
  components: {
    Card
  },
  data() {
    return {
      windowTop: 0,
      projectsList: [
        {
          id: 0,
          title: 'Frog&road game',
          content: 'Один из первых моих проектов на Python',
          img: 'https://wanted5games-games-live.s3.amazonaws.com/game-img/5706.jpg',
          link: 'https://github.com/nikitinroman/GameFrog'
        },
        {
          id: 1,
          title: 'Бот Вконтакте',
          content: 'Бот в социальной сети Вконтакте на Python',
          img: 'https://sun9-7.userapi.com/c831208/v831208545/e06ab/I-OyStqubaw.jpg',
          link: 'https://github.com/nikitinroman/bot_vk'
        },
        {
          id: 2,
          title: 'Кофейня',
          content: 'Один из первых моих проектов на Python, автоматизация кофейни.',
          img: 'https://upload.wikimedia.org/wikipedia/ru/thumb/d/d3/Starbucks_Corporation_Logo_2011.svg/1200px-Starbucks_Corporation_Logo_2011.svg.png',
          link: 'https://github.com/nikitinroman/Coffee'
        },
        {
          id: 3,
          title: 'Сайт-визитка',
          content: 'Первая попытка написать что-то прикольное на Vue',
          img: 'https://cs9.pikabu.ru/post_img/2020/04/24/11/1587758241158384820.png',
          link: 'https://github.com/nikitinroman/vizitka'
        },
        {
          id: 4,
          title: 'Data science university',
          content: 'Тут будет ссылка на гит с нотбуками',
          img: 'https://miro.medium.com/max/925/1*E1haIGB9K4K89PsFZgm-pw.jpeg',
          link: 'https://github.com/nikitinroman/GameFrog'
        },
        {
          id: 5,
          title: 'Заглушка',
          content: 'Заглушка, перейдя по ссылке, почитайте о ней на вики',
          img: 'https://images.obi.ru/product/RU/412x329/278773_1.jpg',
          link: 'https://ru.wikipedia.org/wiki/%D0%A4%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D1%8F-%D0%B7%D0%B0%D0%B3%D0%BB%D1%83%D1%88%D0%BA%D0%B0'
        },
      ]
    };
  },
    mounted() {
      window.addEventListener("scroll", this.onScroll);
    },
    beforeDestroy() {
      window.removeEventListener("scroll", this.onScroll);
    },
    methods: {
      onScroll(e) {
        this.windowTop = e.target.documentElement.scrollTop;
      }
    }
}
</script>

<style scoped>
.bigDiv{
  height: 110vh;
  background-color: white;
  padding-top: 1px;
}
</style>
