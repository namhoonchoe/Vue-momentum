<template>
  <div id="app">
    <Todoinput 	v-on:add="addTodoItem"></Todoinput>
    <Todos	v-bind:todolist="todoItems"	v-on:remove="removeTodoItem"></Todos>
  </div>
</template>

<script>
import Todoinput from './components/Todolist/TodoInput.vue'
import Todos from './components/Todolist/Todos.vue'




export default {
  data(){
    return {
      todoItems: []
    }
  },
  methods:{
    clearAll(){
      localStorage.clear();
      this.todoItems = [];
    },
    addTodo(todoItem) {
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    },
    removeTodo(todoItem, index){
      localStorage.removeItem(todoItem);
      this.todoItems.splice(index,1);
    }
  },
  created() {
    if (localStorage.length >0){
      for (let i=0; i<localStorage.length; i++){
        this.todoItems.push(localStorage.key(i));
      }
    }
  },
  name: 'App',
  components: {
    'Todoinput': Todoinput,
    'Todos':Todos
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
