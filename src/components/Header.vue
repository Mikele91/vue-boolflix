<template>
  <header class="d-flex">
        <div class="logo"> <img src="https://hd2.tudocdn.net/815221?w=100&h=50" alt=""></div>
      <div class="contiainer w-100">
       <form action="" class="d-flex">
        <input type="text" class="form-control" placeholder="Search Film" v-model="inputText">
        <button type="submit" class="btn " @click.prevent="$emit('search', inputText)"  ></button>
        <!-- <button class="btn btn-warning" @click.prevent="resetSearch"> Reset</button> -->
    </form>

      </div>
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
header{
    border: 2px solid red;
    justify-content: space-between;
    align-items: center;
    height: 10rem;
    .logo{
        margin: 0 .625rem 
    };
    
.form-control:focus {
    color: #212529;
    background-color: #fff;
    outline: 0;
    box-shadow: 0 0 0 0.20rem rgb(255 0 0 / 0.8);
    }
}

</style>