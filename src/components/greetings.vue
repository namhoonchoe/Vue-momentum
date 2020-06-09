<template>
  <div>
    <form v-show="this.userName === null">
      <input type = "text" 
             v-model.lazy="userName"  
             v-on:keypress.enter.prevent    
             class ="greetings-container"   
             placeholder = "Write your name"/>
        <span class="add_icon"
              v-on:cilck="saveUsername">
          <i class="far fa-plus-square"></i>
        </span>                               
    </form>
    <form v-show="this.userName  !== null ">
       <p v-on:click="modifyUsername"> 
         Welcome {{this.userName}}! 
       </p> 
    </form>
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

<style scoped>
   
.greetings-container {
    background-color: transparent;
    border:none; 
    border-bottom: 1px solid  white;
    margin-right:5px;
    outline:none;
    color: white;
    text-align:center;
  }

  input::placeholder {
    color:white;
  }
  
</style>