<script>
import { store } from '../store';
export default{
    name: 'appMain',
    data(){
      return {
         store,
       }
   },
}

</script>

<template>
    <div>
        <h2>movies</h2>
        <div v-for="movies in store.movie">
            <img src="" alt="">
            <h3>{{ movies.original_title }}</h3>
            <p>{{ movies.title }}</p>
            <p>{{ movies.original_language }}</p>
        </div>
        <h2>tv show</h2>
        <div v-for="serie in store.series">
            <img src="" alt="">
            <h3>{{ serie.original_name }}</h3>
            <p>{{ serie.original_language }}</p>
            <p>{{ serie.vote_average }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;

</style>
