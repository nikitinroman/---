<template>
  <div>
    <div class="navBox">
      <div class="navBar">
        <div class="navBut" v-for="item in navbar" v-bind:key="item.href" v-bind:class="{ activeDivLink: item.id==slideId }">
          <a class="usualLink" :href="item" v-bind:class="{ activeLink: item.id==slideId }">{{item.title}}</a>
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
        <div class="miniInfoDiv"><h1>Немного слов 0</h1></div>
        <div class="miniInfoDiv"><p>Тут слов немного больше, но не много</p></div>
        <div class="miniInfoDiv"><p>Тут слов прям много много много много много много много много многоТут слов прям много много много много много много много много много</p></div>
      </div>
    </div>
    <div class="shortInfo" v-else-if="slideId==1" style="left: 70%; top: 50%;">
      <div class="infoDiv">
        <div class="miniInfoDiv"><h1>Немного слов 1</h1></div>
        <div class="miniInfoDiv"><p>Тут слов немного больше, но не много</p></div>
        <div class="miniInfoDiv"><p>Тут слов прям много много много много много много много много многоТут слов прям много много много много много много много много много</p></div>
      </div>
    </div>
    <div class="shortInfo" v-else-if="slideId==2"  style="left: 5%; top: 55%;">
      <div class="infoDiv">
        <div class="miniInfoDiv"><h1>Немного слов 2</h1></div>
        <div class="miniInfoDiv"><p>Тут слов немного больше, но не много</p></div>
        <div class="miniInfoDiv"><p>Тут слов прям много много много много много много много много многоТут слов прям много много много много много много много много много</p></div>
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
          href: '/sosi',
          title: 'Обо мне'
        },
        {
          id: 1,
          href: '/lol',
          title: 'Хобби'
        },
        {
          id: 2,
          href: '/mem',
          title: 'Образование'
        },
        {
          id: 3,
          href: '/pek',
          title: 'Цели'
        },
        {
          id: 4,
          href: '/kek',
          title: 'Прочее'
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
.infoDiv:hover{
  transition: all 3s ease-in;
  transform: scale(1.04);
}
.miniInfoDiv{
  width: 300px;
  height: auto;
  border-radius: 50px;
  background-color: white;
  text-align: center;
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
