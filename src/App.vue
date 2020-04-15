<template>
  <div id="app" >
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <setup msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import setup from './components/setup.vue'

export default {
  name: 'App',
  components: {
    setup
  }
}
</script>

<style>
#app {
  min-height: 100vh;
  height: 100%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* background-image:url('shades.png'); */
  background-image: url('./assets/this.jpg');
  background-position: center;
  background-size: 100%;;
  /* color: #2c3e50; */
  /* margin-top: 60px; */
}
</style>
