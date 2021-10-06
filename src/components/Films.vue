<template>
<div  class="cards d-flex">
  <div v-for= "(film, index) in infoFilm" :key="index" >
    <CardFilm :info= "film"/>
  </div>
   <div v-for= "(serie, index) in infoTv" :key="index" >
    <CardFilm :serieTv= "serie"/>
  </div>
</div>
</template>

<script>
import CardFilm from './CardFilm.vue'
// import axios from 'axios';

export default {
    name:"Films",
    components:{
        CardFilm,   
    },
    data(){
        return{
            // films:[],
        }
    },
    props:{
        infoFilm:Array,
        infoTv:Array,
        },
}
</script>

<style scoped lang="scss">
.cards{
    overflow-x: auto;
}

</style>