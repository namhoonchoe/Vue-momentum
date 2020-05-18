<template>
  <div>
    <form v-show="this.userName === null " >
      <input type = "text" 
             v-model.lazy="userName"           
             placeholder = "Write your name"/>
        <span class="add_icon"
              v-on:submit.prevent="saveUsername">
          <i class="far fa-plus-square"></i>
        </span>       
                        
    </form>
    <div v-show="this.userName  !== null ">
       <p> Welcome {{this.userName}}! </p>
        <span class="modify_icon" 
              v-on:click="modifyUsername">
          <i class="far fa-plus-square"></i>
        </span>  
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      userName:null
    }
  },
  methods:{
    getUsername(){
      this.userName = localStorage.getItem('userName');
    },
    saveUsername(userName){
       this.getUsername();   
       localStorage.setItem('userName',userName);      
    },
    modifyUsername(){
      localStorage.removeItem('userName');
      this.saveUsername();
    }
   }
  
  }

</script>

<style>

</style>