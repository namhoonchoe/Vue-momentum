<template>
  <form v-on:submit.prevent="Username">
    <input v-bind:id=message>
  </form>
</template>

<script>
export default {
    data() {
      return {
        userName:'',
        message:'Write your name'
      }        
    },
    methods:{
      saveName(){
        const input = this.userName;
        this.$emit('addUsername',input);
        this.userName = '';
      },
      greetings(){

      },

    
     
    },
    computed:{
      
    }
  }

</script>

<style>

</style>