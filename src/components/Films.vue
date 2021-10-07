<template>
<div  class="cards ">
    <div class="genere">Film</div>
    <div class="films d-flex">
        <div v-for= "(film, index) in infoFilm" :key="index" >
            <CardFilm :info= "film"/>
        </div>
    </div>

    <div class="genere">Serie Tv</div>
    <div class="serie d-flex">
        <div v-for= "(serie, index) in infoTv" :key="index" >
            <CardFilm :info= "serie"/>
        </div>
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
        
        }
    },
    props:{
        infoFilm:Array,
        infoTv:Array,
        },
}
</script>

<style scoped lang="scss">
.genere{
    font: 700;
    background-color: black;
    color: white;
}
  /* width */
::-webkit-scrollbar {
  height: 8px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey;
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: red;
  border-radius: 15px;
}
.films, .serie{
    // height: 30rem;
    overflow-x: auto;
 
}

</style>