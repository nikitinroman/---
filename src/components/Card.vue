<template>
  <div class="invisibleDiv" v-bind:class="{visibleDiv: (windowTop > windowTopVal)}">
    <div class="innerDiv" v-for="item in aboutMeList" v-bind:key="item.id">
      <div style="align-self: center; margin-top: 22px">
        <a :href="item.link"><img class="imgClass" :src="item.img" alt="photo"></a>
      </div>
      <div class="titleDiv">
        <p style="font-size: x-large; font-weight: bold">{{item.title}}</p>
      </div>
      <div style="margin-bottom: 5px">
        <p class="contentDiv">{{item.content}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: "Card",
  props: {
  aboutMeList: {
    type: Array,
    required: true,
  },
  windowTop: {
    type: Number,
    required: true,
  },
  windowTopVal: {
    type: Number,
    required: true,
  }
  }
}
</script>

<style scoped>
.invisibleDiv {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: flex-start;
  flex-wrap: wrap;
  position: relative;
  margin: 30px auto;
  width: 70%;
  opacity: 0;
  transform: translateY(10%);
  transition: 0.5s;
}

.visibleDiv {
  transform: translateY(0);
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
.innerDiv:hover .imgClass{
  height: 240px;
  width: 250px;
  border-radius: 40px;
  margin-top: -5px;
}
.contentDiv{
  height: auto;
  text-align: center;
  margin: 10px 10px;
}
.titleDiv{
  text-align: center;
  height: 40px;
  margin-top: -15px;
  margin-bottom: 5px;
}
.imgClass{
  height: 220px;
  width: 220px;
  border-radius: 10px;
  transition: 0.5s;
}
</style>
