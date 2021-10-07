<template>
<div  class="cards ">
    <div class="films d-flex">
        <div v-for= "(film, index) in infoFilm" :key="index" >
            <CardFilm :info= "film"/>
        </div>
    </div>
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
.films, .serie{
    height: 30rem;
    overflow-x: auto;
}

</style>