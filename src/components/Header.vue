<template>
  <header class="my-5">
       <form action="" class="d-flex">
        <input type="text" class="form-control" placeholder="Search Film" v-model="inputText">
        <button type="submit" class="btn btn-primary mx-3" @click.prevent="$emit('search', inputText)">Search</button>
        <button class="btn btn-warning" @click.prevent="resetSearch"> Reset</button>
    </form>
  </header>
</template>

<script>
export default {
    name:"Header",
    data(){
        return{
            inputText:"",
        }
    },
    methods:{
        resetSearch(){
            this.inputText="";
            this.$emit('search', this.inputText)
        }
    }

}
</script>

<style scoped lang="scss">
@import '../assets/style/common.scss';

</style>