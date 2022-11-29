<template>
  <div id="app">

    <HeaderComp @Text="valueText"/>
    <MainComp/>

  </div>
</template>

<script>

import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

import axios from 'axios' 


export default {
  name: 'App',
  components: {
    
    HeaderComp,
    MainComp,
  },

  data(){

    return{

      arrayFilms:[],

      api_key:'?api_key=40b9be3bc2bac6086df4f70ef377f1b4',
      valueQuery:'all'
    } 

  },

  mounted() {

    
  },

  beforeUpdate(){

  
  },

  methods:{

    valueText(InputText){

      axios.get(`https://api.themoviedb.org/3/search/movie${this.api_key}&query=${this.valueQuery}`).then((response)=>{

      this.arrayFilms = response.data.results

      console.log(this.arrayFilms);
      

    })

      this.valueQuery = InputText

      console.log(this.valueQuery)
      
    }
    
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
