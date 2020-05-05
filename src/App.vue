<template>
  <div id="app">
    <Clock/>
    <Todolist/>
  </div>
</template>

<script>
import Todolist from './components/Todolist.vue';
import Clock from './components/Clock.vue';

export default {

  name:'App',

  components: {
    Todolist,
    Clock
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
