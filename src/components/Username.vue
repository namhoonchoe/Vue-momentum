<template>
    <div class="greetings">
      <form v-if="userName === '' ">
          <input type="text" placeholder="Write your name here">
      </form>
      <p v-else> Welcome {{userName}} !</p>
    </div>
</template>

<script>
export default {
    data(){
      return{
       userName:''  
      }
    },
    methods:{
        getUsername(){

        },
        removeUsername(){

        }
    },
    name:'userName'
}
</script>

<style>

</style>