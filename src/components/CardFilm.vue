<template>
  <div class="film">
        <img :src="(info.poster_path!= null)?`https://image.tmdb.org/t/p/w300${info.poster_path}`:'https://via.placeholder.com/300x300/000000/FFFFFF?text=Image+NO+Found'" :alt="info.original_title">
        <h3>{{info.original_title||info.original_name}}</h3>
        <div>{{info.title||info.name}}</div>
        <!-- <div>{{info.original_language}}</div> -->
        <div>{{printStar(vote(info.vote_average))}}</div>

        <div class="lang"><lang-flag :iso='info.original_language' :squared="false"/></div>      
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags'

export default {
    name:"CardFilms",
    components: {
        LangFlag,
    },
    props:{
      info: Object,
      // serieTv:Object
    },
    methods:{
      vote: function(num){
        let changeStars =  Math.ceil(num/2);
        return changeStars
    },

    printStar: function(elm) {
        let star=[];
        for(let i = 0; i < 5 ; i++){
          if (elm < 5){
            star +=star.push('<i class="fas fa-star"></i> piena');
          } else{
            
            star+= star.push('<i class="far fa-star"></i> vuota');

          }
          return star
        }

    }
  }
}
</script>

<style scoped lang="scss">
@import '../assets/style/common.scss';
</style>





