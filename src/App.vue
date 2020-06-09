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
  text-align: center;
  color:#f5f5f5;
  box-sizing:border-box;
}
body{
    position:absolute;
    margin:0px;
    border:0px;
    min-width:100%;
    min-height:auto;
    z-index: -1;
  }



</style>
