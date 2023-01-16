<script>
import { store } from './store.js';
import appHeader from './components/appHeader.vue';
import appMain from './components/appMain.vue';
import appFooter from './components/appFooter.vue';
import axios from 'axios';

export default {
  name: 'AppVue',
  components: {
    appHeader,
    appMain,
    appFooter,
  },
  data() {
      return {
      store,
      apikey:'e0881c78a00708611e8a0dd128480c52',
      urlSeries: 'https://api.themoviedb.org/3/search/tv',
      urlMovie: 'https://api.themoviedb.org/3/search/movie',
    }
  },
  methods:{
    getSerieTV(series){
      axios.get(this.urlSeries,{
        params:{
          api_key: this.apikey,
          query: series
        }
      })
      .then((response)=>{
        console.log(response.data.results)
        this.store.series = response.data.results
      })

    },


    getMovie(movies){
      axios.get(this.urlMovie,{
        params:{
          api_key: this.apikey,
          query: movies
        }
      })
      .then((response) =>{
        console.log(response.data.results)
        this.store.movie = response.data.results
      })
    },
    getSearch(search){
      this.getMovie( search),
      this.getSerieTV(search)
    }

  },

  created(){
    
  }
 
}

</script>

<template>
  <header>
    <appHeader @change="getSearch"/>
  </header>
  <main>
    <appMain/>
  </main>
  <footer>
    <appFooter/>
  </footer>
</template>

<style lang="scss">
@use './styles/general' as * ;
@use './styles/partials/variables' as * ;
@use "bootstrap/scss/bootstrap" as *;

</style>
