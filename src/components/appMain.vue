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
    },
    getStar(numbers) {
        return Math.ceil(numbers / 2)
    },
   }
}

</script>

<template>
    <div class="bg">
        <div class="bg-danger text-light">
            <div class="container">
                <h2 class="ms-3">Movie</h2>
            </div>
        </div>
        <div class="container  d-flex flex-wrap justify-content-between">
            <div v-for="movies in store.movie" style="width: 15rem;" class="card mt-3 mb-3">
                <img :src="'https://image.tmdb.org/t/p/w300/' + movies.poster_path"
                :alt="movies.title" class="card-img-top">
                <div class="card-body bg-dark rounded d-flex flex-column justify-content-between">
                    <div class="text-light">
                        <p>{{ movies.title }}</p>
                        <h3>{{ movies.original_title }}</h3>
                        <img class="flag mb-2" :src="getImagePath(movies.original_language)" alt="flag">
                    </div>
                    <div class="text-light">
                        <i v-for="n in getStar(movies.vote_average)" class="fa-solid fa-star"></i>
                    </div>
                    <div class="d-flex align-items-end mt-2">
                        <button type="button" class="btn btn-danger">Guarda ora</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="bg">
        <div class="bg-danger text-light">
            <div class="container"> 
                <h2 class="ms-3">Series</h2>
            </div>
        </div>
        <div id="tv" class="container  d-flex flex-wrap justify-content-between">
            <div v-for="serie in store.series" style="width: 15rem;" class="card mt-3 mb-3">
                <img :src="'https://image.tmdb.org/t/p/w300/' + serie.poster_path"
                :alt="serie.title">
                <div class="card-body bg-dark rounded d-flex flex-column justify-content-between">
                    <div class="text-light">
                        <h3>Titolo: {{ serie.original_name }}</h3>
                        <img class="flag mb-2" :src="getImagePath(serie.original_language)" alt="flag">  
                    </div>
                    <div class="text-light">
                        <i v-for="n in getStar(series.vote_average)" class="fa-solid fa-star"></i>
                    </div>
                    <div class="d-flex align-items-end mt-2">
                        <button type="button" class="btn btn-danger">Guarda ora</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;
.bg{
    background-color: gray;
}
.flag{
    width: 25px;
}
.card-custom{
    height: 200px;
}


</style>
