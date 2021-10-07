<template>
  <div class="card">
        <div :style="background-image:url( info.poster_path!= null?`https://image.tmdb.org/t/p/w300${info.poster_path}`:'https://via.placeholder.com/300x300/000000/FFFFFF?text=Image+NO+Found)'">
        <h3>{{info.original_title||info.original_name}}</h3>
        <div>{{info.title||info.name}}</div>
        <!-- <div>{{info.original_language}}</div> -->
        <div>
          <i v-for="n in 5" :key="n" class="fa-star" :class="(n <= vote()) ? 'fas' : 'far'"></i>
        </div>

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
      vote: function(){
        return  Math.ceil(this.info.vote_average/2);
   
    },

    
  }
}
</script>

<style scoped lang="scss">
@import '../assets/style/common.scss';
.card
{
  width: 12.5rem;
  height: 100%;
  background-image: url("info.poster_path!= null?`https://image.tmdb.org/t/p/w300${info.poster_path}`:'https://via.placeholder.com/300x300/000000/FFFFFF?text=Image+NO+Found'") ;
  color:white;

  i{
    color: yellow;
  }
}
</style>





