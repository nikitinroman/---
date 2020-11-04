<template>
  <div style="position: relative;">
    <parallax :fixed="true">
      <img src="https://mymoscowcity.com/upload/iblock/a9c/a9c2b0b174448e6054cbbbd957fd0429.jpg" alt="parallax_bg">
    </parallax>
    <div class="invisibleDiv" v-bind:class="{visibleDiv: (windowTop > 300)}">
      <div class="innerDiv">
        <div style="align-self: center; margin-top: 6px">
          <img height="220px" width="220px" src="https://images11.cosmopolitan.ru/upload/img_cache/53a/53a72f08cdb7dabc97b042badb78eb29_cropped_666x833.webp?webp" alt="photo">
        </div>
        <div class="titleDiv">
          <p style="font-size: x-large; font-weight: bold">Конный спорт 1</p>
        </div>
        <div>
          <p class="contentDiv">тут текст текст текст тут текст текстекст текст тут текст тектекст текст тут текст тексттекст текст тут текст тексттекст текст тут текст текстсттекст текст тут текст текстт текст тут текст текст текст</p>
        </div>
      </div>
      <div class="innerDiv">
        <div style="align-self: center; margin-top: 6px">
          <img height="220px" width="220px" src="https://images11.cosmopolitan.ru/upload/img_cache/53a/53a72f08cdb7dabc97b042badb78eb29_cropped_666x833.webp?webp" alt="photo">
        </div>
        <div class="titleDiv">
          <p style="font-size: x-large; font-weight: bold">Конный спорт 1</p>
        </div>
        <div>
          <p class="contentDiv">тут текст текст текст тут текст текстекст текст тут текст тектекст текст тут текст тексттекст текст тут текст тексттекст текст тут текст текстсттекст текст тут текст текстт текст тут текст текст текст</p>
        </div>
      </div>
      <div class="innerDiv">
        <div style="align-self: center; margin-top: 6px">
          <img height="220px" width="220px" src="https://images11.cosmopolitan.ru/upload/img_cache/53a/53a72f08cdb7dabc97b042badb78eb29_cropped_666x833.webp?webp" alt="photo">
        </div>
        <div class="titleDiv">
          <p style="font-size: x-large; font-weight: bold">Конный спорт 1</p>
        </div>
        <div>
          <p class="contentDiv">тут текст текст текст тут текст текстекст текст тут текст тектекст текст тут текст тексттекст текст тут текст тексттекст текст тут текст текстсттекст текст тут текст текстт текст тут текст текст текст</p>
        </div>
      </div>
      <div class="innerDiv">
        <div style="align-self: center; margin-top: 6px">
          <img height="220px" width="220px" src="https://images11.cosmopolitan.ru/upload/img_cache/53a/53a72f08cdb7dabc97b042badb78eb29_cropped_666x833.webp?webp" alt="photo">
        </div>
        <div class="titleDiv">
          <p style="font-size: x-large; font-weight: bold">Конный спорт 1</p>
        </div>
        <div>
          <p class="contentDiv">тут текст текст текст тут текст текстекст текст тут текст тектекст текст тут тектекст текст тут тектекст текст тут тектекст текст тут текст тексттекст текст тут текст тексттекст текст тут текст текстсттекст текст тут текст текстт текст тут текст текст текст</p>
        </div>
      </div>
      <!--
      <div class="innerDiv">
        <div style="align-self: center; margin-top: 6px">
          <img height="220px" width="220px" src="https://images11.cosmopolitan.ru/upload/img_cache/53a/53a72f08cdb7dabc97b042badb78eb29_cropped_666x833.webp?webp" alt="photo">
        </div>
        <div class="titleDiv">
          <p style="font-size: x-large; font-weight: bold">Конный спорт 1</p>
        </div>
        <div>
          <p class="contentDiv">тут текст текст текст тут текст текстекст текст тут текст тектекст текст тут тет тут текст текстекст текст тут текст тектекст текст тут текст тексттекст текст тут текст тексттекст текст тут текст текстсттекст текст тут текст текстт текст тут текст текст текст</p>
        </div>
      </div>-->

    </div>
  </div>
</template>

<script>
import Parallax from 'vue-parallaxy'


export default {
  name: "App",
  components: {
    Parallax
  },
  data() {
    return {
      windowTop: 0
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

.invisibleDiv {
  background-color: white;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: flex-start;
  flex-wrap: wrap;
  position: relative;
  top: 20%;
  left: 15%;
  height: 900px;
  width: 1000px;
  opacity: 0;
}

.visibleDiv {
  opacity: 0.9;
}

.innerDiv{
  display: flex;
  flex-direction: column;
  background-color: whitesmoke;
  justify-content: center;
  border-radius: 40px;
  width: 300px;
  height: auto;
  margin-bottom: 20px;
}
.contentDiv{
  height: auto;
  text-align: center;
}
.titleDiv{
  text-align: center;
  height: 40px;
  margin-top: -10px;
}
</style>
