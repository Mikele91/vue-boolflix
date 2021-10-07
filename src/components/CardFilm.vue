<template>
  
    <div class="card" :style="`background-image:url( ${info.poster_path ? `https://image.tmdb.org/t/p/w300${info.poster_path}` : `https://via.placeholder.com/300x300/000000/FFFFFF?text=Image+NO+Found)`}`">
      <div  class="effect_hover">
      <h3 class="text-center">{{info.original_title||info.original_name}}</h3>
      <div>{{info.title||info.name}}</div>
      <div class="text_overview">{{info.overview|| "Nessuna Descrizione"}}</div>
      <!-- <div>{{info.original_language}}</div> -->
      <div>
        <i v-for="n in 5" :key="n" class="fa-star" :class="(n <= vote()) ? 'fas' : 'far'"></i>
      </div>

      <div class="lang"><lang-flag :iso='info.original_language' :squared="false"/></div>      
      </div>
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
  width: 20rem;
  height: 100%;
  background-size: cover;
  background-position: center;
  .effect_hover{
    padding: .3125rem;
    opacity: 0;
    width: 100%;
    height: 100%;
    overflow-y: auto;

    .text_overview{
      font-size: 12px;
      
    }
  }

  .effect_hover:hover{
    color:white;
    background-color: rgb(255 0 0 / 0.6);
    
    opacity: 1;
};


  i{
    // color: yellow;
  }
}
</style>





