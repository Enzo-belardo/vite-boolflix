<script>
import { store } from '../store'
export default{
    name: 'appHeader',
    data(){
      return {
         store,
         film: '',
       }
    },
    methods:{
        search(film) {
            this.$emit('change', film)
        }
    },
}
</script>

<template>
    <div class="search d-flex justify-content-between  align-items-center">
        <div class="d-flex align-items-center w-50">
            <div class="logo ms-3 ">
                <img src="https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png" alt="" class="">
            </div>
    
            <nav class="d-flex ">
                <ul class="text-light mt-3">
                    <li><a href="">Home</a></li>
                    <li><a href="">Movies</a></li>
                    <li><a href="#tv">Tv-show</a></li>
                    <li><a href="">Latest</a></li>
                    <li><a href="">My list</a></li>
                </ul>
            </nav>
        </div>
    
        <div class="me-3">
            <label for=""></label>
            <input @keyup.enter="search(film)" type="text" placeholder="inserisci il tuo film" v-model="film">
            <button @click="search(film)" class="btn btn-danger">Cerca</button>  
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;
 
.search{
    background-color: black;
    padding: 1rem 0;
}
.logo>img{
    width: 100px;
}
button{
    margin-left: 1rem;
    
}
ul{
    li{
        display: inline-block;
        list-style-type: none;
        margin-right: 1rem;
        a{
            text-decoration: none;
            color: white;
        }
    }
}

input{
    padding: .3rem;
}
</style>
