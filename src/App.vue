<template>
  <div id="app">
    <div class="container">
    <Header @search="searchFilm"/>

    <Films :info="films"/>
    </div>
  </div>
</template>

<script>
import Films from './components/Films.vue'
import Header from './components/Header.vue'
import axios from 'axios';


export default {
  name: 'App',
  components: {
    Header,
    Films,
  },
  data(){
    return{
      searchText :"",
      films:[],
    }
  },
  methods:{
        searchFilm(text) {
            this.searchText = text;
                }
    },
  props:{

  },
   created(){
        // axios.get('https://api.themoviedb.org/3/search/movie',
        //         {
        //             params:{
        //                 api_key: '7e390297db8f760afc45d7092f6f5846',
        //                 query: searchText,
        //                 language: 'it-IT',
        //             }
        //         }
        // ).then( (res)=> {
        //     this.films = res.data.results;
        // });


        axios
        .get("https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+fut")
        .then( (res)=> {
            this.films = res.data.results;
        })
    }

}
</script>

<style lang="scss">
@import './assets/style/common.scss';

</style>
