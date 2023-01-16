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
}
</script>

<template>
    <div class="search">
        <label for=""></label>
        <input type="text" placeholder="inserisci il tuo film" v-model="film">
        <button @click="$emit('change', film)">Clicca</button>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;
 
.search{
    text-align: end;
}
button{
    margin-left: 1rem;
    

}
</style>
