<template>
<body>
    <img src="../assets/1.jpg" 
         v-if="randNum == 1"
         alt="bgimg1">
    <img src="../assets/2.jpg" 
         v-else-if="randNum == 2"
         alt="bgimg2">
    <img src="../assets/3.jpg" 
         v-else-if="randNum == 3"
         alt="bgimg3">
    <img src="../assets/4.jpg" 
         v-else
         alt="bgimg4">
</body>  
</template>

<script>
export default {
    data(){
      return {
        randNum: 0
      }
    },
    methods :{
      genRandom() {
          const imgNum = 8;
          this.randNum = Math.floor(Math.random()*imgNum);
          return this.randNum
      }     
    } ,
    created(){
        this.genRandom();
    }

}

</script>

<style>
    .body{
        position:absolute;
        margin-top: 0px;
        margin-left:0px;
        width:100%;
        z-index: -1;
    }
</style>