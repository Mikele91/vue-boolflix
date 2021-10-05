<template>
  <div class="container">
      <CardFilms/>
  </div>
</template>

<script>
import CardFilms from './CardFilm.vue'

import axios from 'axios';

export default {
    name:"Films",
    components:{
        CardFilms,
    },
    data(){
        return{
            films:[],
        }
    },
    props:["info"],
    created(){
        axios
        .get("https://api.sampleapis.com/rickandmorty/characters")
        .then( (res)=> {
            this.films = res.data;
        })
    }
}
</script>

<style scoped lang="scss">


</style>