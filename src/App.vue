<template>
  <div id="app">
    <div >
    <Header @search="searchFilm"/>
    <Films :infoFilm="films" :infoTv=" seriesTv"/>
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
      
      films:[],
      seriesTv:[],
    }
  },
  methods:{
        searchFilm(text) {
          axios.get('https://api.themoviedb.org/3/search/movie',
                {
                    params:{
                        api_key: '7e390297db8f760afc45d7092f6f5846',
                        query: text,
                        language: 'it-IT',
                    }
                }
                ).then( (res)=> {
                  this.films = res.data.results;
                  }); 
          axios.get('https://api.themoviedb.org/3/search/tv',
        {
            params:{
                api_key: '7e390297db8f760afc45d7092f6f5846',
                query: text,
                language: 'it-IT',
            }
        }
        ).then( (res)=> {
          this.seriesTv = res.data.results;
          });       
        },
  },

}
</script>

<style lang="scss">
@import './assets/style/common.scss';

   /* width */
::-webkit-scrollbar {
  width: 5px;
  
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey;
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: black;
  border-radius: 10px;
}
</style>
