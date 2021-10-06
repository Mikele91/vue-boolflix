<template>
  <div class="film">
        <img :src="`https://image.tmdb.org/t/p/w300${info.backdrop_path}`" :alt="info.original_title">
        <h3>{{info.original_title||info.original_name}}</h3>
        <div>{{info.title||info.name}}</div>
        <!-- <div>{{info.original_language}}</div> -->
        <div>{{info.vote_count}}</div>

        <div class="lang"><lang-flag :iso='info.original_language' :squared="false"/></div>      
  </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags'

export default {
    name:"CardFilms",
    components: {
        LangFlag
    },
    props:{
      info: Object,
      // serieTv:Object
    }

}
</script>

<style scoped lang="scss">

</style>