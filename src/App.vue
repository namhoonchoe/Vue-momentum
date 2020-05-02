<template>
  <div id="app">
    <Todoinput 	
            v-on:add="addTodoItem"
            ></Todoinput>
    <Todos	
            v-bind:todolist="todoItems"	
            v-on:remove="removeTodoItem"
            ></Todos>
  </div>
</template>

<script>
import Todoinput from './components/Todolist/TodoInput.vue';
import Todos from './components/Todolist/Todos.vue';


export default {

  data(){
    return {
      todoItems: []
    };
  },
  methods:{
    fetchTodoItems: function() {
			for (let i = 0; i < localStorage.length; i++) {
				let item = localStorage.key(i);
				this.todoItems.push(item);
			}
    },
    addTodoItem:  function(todoItem) {
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);

    },
    removeTodoItem: function(todoItem, index){
      localStorage.removeItem(todoItem);
      this.todoItems.splice(index,1);
    }
  },
  created: function() {
		this.fetchTodoItems();
	},

  name:'App',

  components: {
    'Todoinput': Todoinput,
    'Todos':Todos
  }
  
};
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
