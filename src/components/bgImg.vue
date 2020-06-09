<template>
<div>
  <body>
    <img src="../assets/1.jpg" 
         v-show="randNum == 1"
         alt="bgimg1">
    <img src="../assets/2.jpg" 
         v-show="randNum == 2"
         alt="bgimg2">
    <img src="../assets/3.jpg" 
         v-show="randNum == 3"
         alt="bgimg3">
    <img src="../assets/4.jpg" 
         v-show="randNum == 4"
         alt="bgimg4">
  </body>  
  <section class="momentum--content">
    <div class="clock-container">
      <Clock/>
    </div>
    <section class="input-container">
     <h4 class="greetings">
      <greetings/>
     </h4> 
     <div class="todoList">
      <Todolist/>
     </div>
    </section>
    
  </section>
 
</div>

</template>

<script>
import Todolist from './Todolist.vue';
import Clock from './Clock.vue';
import greetings from './greetings.vue';

export default {
  components: {
    Todolist,
    Clock,
    greetings
    },
    data(){
      return {
        randNum: 0
      }
    },
    methods :{
      genRandom() {
          const imgNum = 4 ;
          this.randNum = Math.floor(Math.random()*imgNum)+1;
          return this.randNum
      }     
    } ,
    created(){
        this.genRandom();
    }

}

</script>

<style scoped>
  img{
      width:100vw; 
      height:100vh; 
   }
  .momentum--content{
    padding-top: 8rem;
  }
  .clock-container{
    font-size: 3rem;
  }
  
  
</style>