<template>
  <div id="app">
    <div class="container">
    <Header @search="searchFilm"/>

    <Films :info="searchText"/>
    </div>
  </div>
</template>

<script>
import Films from './components/Films.vue'
import Header from './components/Header.vue'


export default {
  name: 'App',
  components: {
    Header,
    Films,
  },
  data(){
    return{
      searchText :"",
    }
  },
  methods:{
        searchFilm(text) {
            this.searchText = text;
                }
    },
  props:{

  },

}
</script>

<style lang="scss">
@import './assets/style/common.scss';

</style>
