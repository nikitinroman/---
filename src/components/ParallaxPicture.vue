<template>
  <div style="position: relative;">
    <parallax :fixed=true @scroll="scrollEvent">
      <img src="https://mymoscowcity.com/upload/iblock/a9c/a9c2b0b174448e6054cbbbd957fd0429.jpg" alt="parallax_bg">
    </parallax>
    <div id="trigger1" style="height: 300px; width: 200px; background-color: white">kekekkeeekeek</div>
  </div>
</template>

<script>
import ScrollMagic from 'scrollmagic';
import Parallax from 'vue-parallaxy'

let controller = new ScrollMagic.Controller();

// build scene
new ScrollMagic.Scene({
  triggerElement: "#trigger1",
  triggerHook: 0.9, // show, when scrolled 10% into view
  duration: "80%", // hide 10% before exiting view (80% + 10% from bottom)
  offset: 50 // move trigger to center of element
})
    .setClassToggle("#reveal1", "visible") // add class to reveal
    .addIndicators() // add indicators (requires plugin)
    .addTo(controller);

export default {
  components: {
    Parallax
  },
  methods:{
    scrollEvent() {
      console.log(0)
    }
  }
}
</script>

<style scoped>

</style>
