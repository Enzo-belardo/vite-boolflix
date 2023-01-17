<script>
import { store } from '../store';
export default{
    name: 'appMain',
    data(){
      return {
         store,
       }
   },
   methods:{
    getImagePath: function (img){
        return new URL(`../assets/img/${img}.png`, import.meta.url).href;
    }
   }
}

</script>

<template>
    <div class="">
        <h2>movies</h2>
        <div class="d-flex">
            <div v-for="movies in store.movie">
                <img :src="'https://image.tmdb.org/t/p/w300/' + movies.poster_path"
                :alt="movies.title">
                <h3>{{ movies.original_title }}</h3>
                <p>{{ movies.title }}</p>
                <img class="flag" :src="getImagePath(movies.original_language)" alt="flag">
                <p>{{ serie.vote_average }}</p>
            </div>
        </div>

        <h2>tv show</h2>
        <div class="d-flex">
            <div v-for="serie in store.series">
                <img :src="'https://image.tmdb.org/t/p/w342/' + serie.poster_path"
                :alt="serie.title">
                <h3>{{ serie.original_name }}</h3>
                <img class="flag" :src="getImagePath(serie.original_language)" alt="flag">  
                <p>{{ serie.vote_average }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;

.flag{
    width: 25px;
}


</style>
