<template>
    <div>
      <Slider></Slider>
      <Parallax></Parallax>
      <div style="height: 100vh; background-color: white"></div>
    </div>
</template>

<script>
import Slider from './components/Slider'
import Parallax from './components/ParallaxPicture'

export default {
  components: {
    Slider,
    Parallax,
  }
}
</script>

<style>
body {
  margin: 0;
  height: 100vh;
}
</style>
