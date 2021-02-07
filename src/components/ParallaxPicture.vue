<template>
  <div>
  <div style="position: relative; height: 0px">
    <parallax :fixed="true">
      <img src="https://i.ytimg.com/vi/vMDA6LySU1M/maxresdefault.jpg" alt="parallax_bg">
    </parallax>
  </div>
  <div>
    <div style="border-radius: 50px; background-color: whitesmoke; max-width: 200px; margin: 20px auto; opacity: 0.9">
      <a name="hobbies"></a>
      <h1 style="text-align: center;">Мои хобби</h1>
    </div>
    <Card :about-me-list="aboutMeList" :window-top="windowTop" :window-top-val="300"></Card>
  </div>
  </div>
</template>

<script>
import Parallax from 'vue-parallaxy'
import Card from './Card'


export default {
  components: {
    Parallax,
    Card
  },
  data() {
    return {
      windowTop: 0,
      aboutMeList: [
        {
          id: 0,
          title: 'Русский бильярд',
          content: 'Одно из первых моих серьезных увлечений- русский бильярд. Так уж вышло, что мой отец- заядлый любитель этого вида спорта и с самого детства он привил мне любовь к бильярду. ',
          img: 'http://www.80store.ru/images/bilyateka/kak-igrat-v-russkij-biljard.jpg'
        },
        {
          id: 1,
          title: 'Конный спорт',
          content: 'С самого раннего детства любил животных, а в особенности- дельфинов и лошадей. Поэтому когда в нашем маленьком городе открылся конный клуб "Буцефал", я сразу записался на занятия.',
          img: 'https://ss.sport-express.ru/userfiles/materials/158/1589321/origin_0122dabe.jpg'
        },
        {
          id: 2,
          title: 'Скейтбординг',
          content: 'Не стоит бояться попробовать что-то новое. Видели ребят на странных досках с колесами, рассекающих по тротуарам/дорогам? Попробуйте и сами! Жизнь всего одна, не нужно бояться добавлять в нее краски!',
          img: 'https://www.wikihow.com/images/thumb/4/48/Ride-a-Penny-Board-Step-6-Version-3.jpg/aid4670207-v4-728px-Ride-a-Penny-Board-Step-6-Version-3.jpg'
        },
        {
          id: 3,
          title: 'Программирование',
          content: 'В программирование я пришел в 2018 году. С тех пор я успел изучить и освоить несколько языков программирования, машинное обучение, а сейчас- изучаю фронтенд разработку.',
          img: 'https://dev.by/storage/images/48/01/93/24/derived/4876d6d2df43ae47dd25a4a767408c77.jpg'
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
};
</script>


<style scoped>

</style>
