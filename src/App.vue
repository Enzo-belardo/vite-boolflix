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
      key:'e0881c78a00708611e8a0dd128480c52',
      url: 'https://api.themoviedb.org/3/movie/550?api_key=e0881c78a00708611e8a0dd128480c52',
    }
  },
  methods:{
    getMovie(){
      axios.get(this.url,{
        params:{

        }

      })
      .then((response) =>{
        console.log(response.data)
        this.store.movie = response.data.data
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
    <appHeader/>
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
