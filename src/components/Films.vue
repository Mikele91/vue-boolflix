<template>
<div>
  <div v-for= "(film, index) in films" :key="index" >
      <CardFilms :info= "film"/>
  </div>
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
            queryVar:""
        }
    },
    props:["info"],
    methods:{
        
        
    },
    created(){
        // axios.get('https://api.themoviedb.org/3/search/movie',
        //         {
        //             params:{
        //                 apy_key: '7e390297db8f760afc45d7092f6f5846',
        //                 query: this.queryVar,
        //                 language: 'it-IT'

        //             }
        //         }
        // )


        axios
        .get("https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+fut")
        .then( (res)=> {
            this.films = res.data.results;
        })
    }
}
</script>

<style scoped lang="scss">


</style>