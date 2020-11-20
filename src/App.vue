<template>
    <div>
      <Slider></Slider>
      <Parallax></Parallax>
      <Education></Education>
      <Github></Github>
      <Footer></Footer>
    </div>
</template>

<script>
import Slider from './components/Slider'
import Parallax from './components/ParallaxPicture'
import Education from "./components/Education"
import Github from "./components/Github";
import Footer from "./components/Footer";

export default {
  components: {
    Slider,
    Parallax,
    Education,
    Github,
    Footer
  }
}
</script>

<style>
body {
  margin: 0;
  height: 100vh;
}
html{
  scroll-behavior: smooth;
}
</style>
