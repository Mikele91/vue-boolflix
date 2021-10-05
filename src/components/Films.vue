<template>
<div>
  <div class="d-flex" v-for= "(film, index) in films" :key="index" >
    <CardFilm :info= "film"/>
  </div>
</div>
</template>

<script>
import CardFilm from './CardFilm.vue'

import axios from 'axios';

export default {
    name:"Films",
    components:{
        CardFilm,
    },
    data(){
        return{
            films:[],
        }
    },
    props:{
        info:String
        },
    updated(){
        axios.get('https://api.themoviedb.org/3/search/movie',
                {
                    params:{
                        api_key: '7e390297db8f760afc45d7092f6f5846',
                        query: this.info,
                        language: 'it-IT',
                    }
                }
        ).then( (res)=> {
            this.films = res.data.results;
        });


        // axios
        // .get("https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+fut")
        // .then( (res)=> {
        //     this.films = res.data.results;
        // })
    }
}
</script>

<style scoped lang="scss">


</style>