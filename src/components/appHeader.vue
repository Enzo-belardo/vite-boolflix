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
    <div>
        <label for=""></label>
        <input type="text" placeholder="inserisci il tuo film" v-model="film">
        <button>Clicca</button>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as * ;
@use '../styles/partials/variables' as * ;
</style>
