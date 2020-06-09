<template>
    <div>
        <input type="text"
          class="todoinput"
          v-model = "newTodoItem"
          placeholder="Write to do here"    
          v-on:keypress.enter="addTodo"
        >
        <span class="add_icon" v-on:click="addTodo">
         <i class="far fa-plus-square"></i>
        </span>
    </div>
</template>

<script>
export default {
      data() {
        return {
            newTodoItem:''
        }      
      },
      methods: {
       addTodo() {
         const input = this.newTodoItem;
         this.$emit('add',input)
         this.newTodoItem = '';
        },
       clearInput() {
        this.newTodoItem = '';
        }
          }
      }

</script>
<style scoped>
 

  .todoinput {
    background-color: transparent;
    border:none; 
    border-bottom: 1px solid  white;
    margin-right: 5px;
    outline:none;
    color: white;
    text-align:center;

  }
  

  input::placeholder {
    color:white;

  }
</style>