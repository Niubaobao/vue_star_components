<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!--<router-view></router-view>-->
    <download></download>
    <star :max="6" :size="100" :scort="4"></star>
  </div>
</template>

<script>
  import Download from './components/download.vue'
  import Star from './components/star_com.vue'
  export default {
    name: 'app',
    components: {
      Download,
      Star
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
