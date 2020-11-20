<template>
  <div>
    <a name="aboutme"></a>
    <div class="navBox">
      <div class="navBar">
        <div @click="goToHash(item.href)" class="navBut" v-for="item in navbar" v-bind:key="item.href" v-bind:class="{ activeDivLink: item.id==slideId }">
          <a class="usualLink" :href="item.href" v-bind:class="{ activeLink: item.id==slideId }">{{item.title}}</a>
        </div>
      </div>
    </div>
    <div>
      <splide :options="options" @splide:move="slideId = -1" @splide:moved="splideMove" @splide:mounted="splideMounted">
        <splide-slide v-for="item in images" v-bind:key="item">
          <img :src="item" height="796" width="100%">
        </splide-slide>
      </splide>
    </div>
    <div class="shortInfo" v-if="slideId==0" style="left: 40%; top: 25%;">
      <div class="infoDiv">
        <div class="miniInfoDiv"><h1>Привет, друг!</h1></div>
        <div class="miniInfoDiv"><p>Меня зовут Никитин Роман</p></div>
        <div class="miniInfoDiv"><p>Я студент Финансового университета при Правительстве Российской Федерации</p></div>
      </div>
    </div>
    <div class="shortInfo" v-else-if="slideId==1" style="left: 70%; top: 50%;">
      <div class="infoDiv">
        <div class="miniInfoDiv"><h1>Мои хобби</h1></div>
        <div class="miniInfoDiv"><p>Я люблю развиваться разносторонне</p></div>
        <div class="miniInfoDiv"><p>Обожаю спорт и технологии. Увлекаюсь всем от скейта до машинного обучения</p></div>
      </div>
    </div>
    <div class="shortInfo" v-else-if="slideId==2"  style="left: 5%; top: 55%;">
      <div class="infoDiv">
        <div class="miniInfoDiv"><h1>Сила в знаниях</h1></div>
        <div class="miniInfoDiv"><p>В свободное время люблю познавать новое</p></div>
        <div class="miniInfoDiv"><p>Прошел много различных курсов по машинному обучению, статистике и фронтенд-разработке</p></div>
      </div>
    </div>
  </div>
</template>

<script>
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import '@splidejs/splide/dist/css/themes/splide-sea-green.min.css';

export default {
  components: {
    Splide,
    SplideSlide,
  },
  data() {
    return {
      slideId: 0,
      images: [
        "https://sun9-13.userapi.com/impf/c850436/v850436650/31cd6/QtXPMGRIORU.jpg?size=1200x900&quality=96&proxy=1&sign=513e5a5cd827a1893c706003d8163e51",
        "https://sun9-10.userapi.com/impf/c850436/v850436650/31cdf/OgqzwG3CpX8.jpg?size=1200x675&quality=96&proxy=1&sign=9fa0bb04c227522f44917e8f10150a91",
        "https://sun9-55.userapi.com/impf/c850436/v850436650/31ce8/f3lvdaFnJqY.jpg?size=1200x675&quality=96&proxy=1&sign=e12cf4eb968992cecbe9c13ecb9709c4"
      ],
      navbar:[
        {
          id: 0,
          href: '#aboutme',
          title: 'Обо мне'
        },
        {
          id: 1,
          href: '#hobbies',
          title: 'Хобби'
        },
        {
          id: 2,
          href: '#education',
          title: 'Образование'
        },
        {
          id: 3,
          href: '#github',
          title: 'Цели'
        },
        {
          id: 4,
          href: '#footer',
          title: 'Контакты'
        },
      ],

      options: {
        width: 10000,
        rewind : true,
        perPage: 1,
        gap    : '0rem',
        autoplay    : true,
        pauseOnHover: false,
        arrows      : false,
      },
    };
  },
  methods: {
    splideMove(splide){
      this.slideId = splide.index
      return this.slideId
    },
    splideMounted(splide){
      this.slideId = splide.index
      return this.slideId
    },
    goToHash(href){
      window.location.hash=href
    }
  },
}
</script>

<style scoped>
.splide {
  padding: 0;
}
.navBox{
  width: 100%;
  top: 3%;
  position: absolute;
  z-index: 1;
}
.navBar{
  position: relative;
  display: flex;
  justify-content: space-around;
}
.navBut{
  display: flex;
  min-width: 100px;
  height: 35px;
  background-color: whitesmoke;
  align-items: center;
  justify-content: center;
  border-radius: 50px;
  transition: 1s;
}
.shortInfo{
  position: absolute;
  border: 1px white;
}
.infoDiv {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
.miniInfoDiv{
  width: 300px;
  height: auto;
  border-radius: 50px;
  background-color: whitesmoke;
  text-align: center;
  margin-bottom: 5px;
}
.activeDivLink{
  background-color: #3a201e;
  opacity: 0.5;
}
.activeLink{
  color: white !important;
}
.usualLink{
  text-decoration: none;
  color: black;
}
.navBut:hover{
  background-color: #3a201e;
  opacity: 0.5;
}
.navBut:hover .usualLink{
  color: white !important;
}
</style>
