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
        <div v-for="movies in store.movie">
            <img src="" alt="">
            <h3>{{ movies.original_title }}</h3>
            <p>{{ movies.title }}</p>
            <p>{{ movies.original_language }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;

</style>
