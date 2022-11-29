<template>
  <div id="app">

    <HeaderComp @Text="valueText"/>
    <MainComp :dataFilms = 'arrayFilms'/>

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

      arrayTvSeries:[],
      arrayFilms:[],
      api_key:'?api_key=40b9be3bc2bac6086df4f70ef377f1b4',
      valueQuery:''

    } 

  },

  methods:{

    valueText(InputText){

      axios.get(`https://api.themoviedb.org/3/search/movie${this.api_key}&query=${this.valueQuery}`).then((response)=>{

      if(this.valueQuery == ''){

        this.arrayFilms = []
      }else{

       this.arrayFilms = response.data.results

      console.log(this.arrayFilms);
      }

    })

    axios.get(`https://api.themoviedb.org/3/search/tv${this.api_key}&query=${this.valueQuery}`).then((response)=>{
      
      this.arrayTvSeries = ''

      this.arrayTvSeries = response.data.results

      console.log(this.arrayTvSeries);

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
