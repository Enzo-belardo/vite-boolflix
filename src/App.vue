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
      url: 'https://api.themoviedb.org/3/search/movie',
    }
  },
  methods:{
    getMovie(title){
      axios.get(this.url,{
        params:{
          api_key: this.apikey,
          query: title

        }

      })
      .then((response) =>{
        console.log(response.data.results)
        this.store.movie = response.data.results
      })
    } 
  },
  created(){
    this.getMovie()
  }
 
}

</script>

<template>
  <header>
    <appHeader @change="getMovie"/>
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
