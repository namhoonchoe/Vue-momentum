<template>
  <div id="app">
    <bgImg/>   
  </div>      
</template>

<script>

import bgImg from './components/bgImg.vue';

export default {
 
  name:'App',
  components: {
    bgImg
  }
  
}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:#f5f5f5










  
}
body{
    position:absolute;
    margin:0;
    min-width:100%;
    min-height:100%;
    z-index: -1;
  }



</style>
