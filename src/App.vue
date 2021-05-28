<template>
  <div id="app">
    <div class="box a">a</div>
    <div class="box b">b</div>
    <div class="box c">c</div>
  </div>
</template>

<script>
// https://greensock.com/docs/v3/Plugins/ScrollTrigger
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
  name: 'App',
  components: {

  },
  mounted(){
    gsap.to(".c", {
      scrollTrigger: {
        trigger: ".c",
        toggleActions: "restart pause reverse pause"
      },
      x: 400,
      rotation: 360,
      duration: 2
    });
  }
}
</script>

<style>
#app {
  height:4000px;
}
.box {
  width:100px;
  height:100px;
  background:chartreuse;
}
.box + .box {
  margin-top:200px;
}
</style>
