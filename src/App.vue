<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { SVG } from '@svgdotjs/svg.js'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    console.log(`MOUNTED AND DRAWING ======+`);

    // initialize SVG.js
    var draw = SVG().addTo('body')

    // draw pink square
    draw.rect(100, 100).move(50, 50).fill('#f06')

    setTimeout(() => {
      console.log(`DOIN IT`)
      draw.animate(2000, 1000, 'now').attr({ fill: '#f03' })
    }, 2000);
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
