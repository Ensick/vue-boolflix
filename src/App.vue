<template>
  <div id="app">

    <HeaderComp/>
    <MainComp/>

    
  </div>
</template>

<script>

import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

/* import axios from 'axios' */


export default {
  name: 'App',
  components: {
    
    HeaderComp,
    MainComp,
  }
}
</script>

<style lang="scss">

 *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

#app {

  font-family: Avenir, Helvetica, Arial, sans-serif;
  height: 100vh;
  background-color: lightgray;
}
</style>
