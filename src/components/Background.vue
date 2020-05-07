<template>
    <body id=bgImg>
      <img v-bind:src="imgsrc">
    </body>
</template>

<script>
export default {
  data(){
    return{
      imgsrc:''
    }
  },
  mehtods:{
    getImage(imgNumber){
      const imageList =  [
        '../assets/1.jpg',
        '../assets/2.jpg',
        '../assets/3.jpg',
        '../assets/4.jpg'];     
      this.imgsrc = imageList[imgNumber];
    },
    randImg(){
      const randNum = Math.floor(Math.random()*4);
      this.getImage(randNum)
    }
  },  
  mounted() {
    this.bgImg = this.randImg; 
  }
};

</script>

<style>

</style>