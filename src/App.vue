<template>
  <div id="app">
    <Clock/>
    <userName/> 
    <Todolist/>
    <bgImg/>
  </div>
</template>

<script>
import Todolist from './components/Todolist.vue';
import Clock from './components/Clock.vue';
import bgImg from './components/bgImg.vue';
import userName from './greetings/userName.vue';

export default {
 
  name:'App',
  components: {
    Todolist,
    Clock,
    userName,
    bgImg

  
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
