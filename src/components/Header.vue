<template>
  <header class="d-flex">
        <div class="logo"> <img src="https://loghi-famosi.com/wp-content/uploads/2020/04/Netflix-Logo.png" alt=""></div>
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
    background-color: rgb(0 0 0 / 0.8);
    // border: 2px solid red;
    justify-content: space-between;
    align-items: center;
    height: 5rem;
    .logo img{
        width: 6.25rem;
        margin: 0 .625rem 
    };
    
.form-control:focus {
    color: #212529;
    background-color: #fff;
    outline: 0;
    box-shadow: 0 0 0 0.20rem rgb(255 0 0 / 0.8);
    };
}

</style>