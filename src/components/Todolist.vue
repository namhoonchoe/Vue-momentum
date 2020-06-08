<template>
  <div>
    <Todoinput 	
      v-on:add="addTodoItem"
      />
    <Todos	
      v-bind:todolist="todoItems"	
      v-on:remove="removeTodoItem"
      />
  </div>
</template>

<script>
import Todoinput from '../todo/TodoInput';
import Todos from '../todo/Todos';

export default {

  data(){
    return {
      todoItems:[]
    }
  },
  methods:{
    fetchTodoItems() {
			for (let i = 2; i < localStorage.length; i++) {
				let item = localStorage.key(i);
				this.todoItems.push(item);
			}
    },
    addTodoItem(todoItem) {
      localStorage.setItem('todoItem', todoItem);
      this.todoItems.push(todoItem);

    },
    removeTodoItem(todoItem, index){
      localStorage.removeItem('todoItem');
      this.todoItems.splice(index,1);
    }
  },
  created() {
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
