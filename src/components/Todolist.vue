<template>
  <div>
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
import Todoinput from '../todo/TodoInput';
import Todos from '../todo/Todos';


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
    addTodoItem: function(todoItem) {
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

  name:'Todolist',

  components: {
    'Todoinput': Todoinput,
    'Todos':Todos
  }
  
};
</script>

<style>

</style>
