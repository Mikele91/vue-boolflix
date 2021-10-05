<template>
  <div class="film">
       <!-- <img :src=`https://image.tmdb.org/t/p/w300${backdrop_path}` :alt="info.original_title"> -->
        <h3>{{info.original_title}}</h3>
        <div>{{info.title}}</div>
        <div><strong>{{info.original_language}}</strong></div>
  </div>
</template>

<script>
export default {
    name:"CardFilms",
    props:{
      info: Object
    }

}
</script>

<style scoped lang="scss">

</style>