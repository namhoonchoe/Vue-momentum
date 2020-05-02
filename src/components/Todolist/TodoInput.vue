<template>
    <div>
      <div class="todoinput">
        <input type="text"
          v-model = "newTodoItem"
          placeholder="Write to do here"    
          v-on:keypress.enter="addTodo"
        >
        <span class="add_icon" v-on:click="addTodo">
         <i class="far fa-plus-square"></i>
        </span>
      </div>
    </div>
</template>

<script>
export default {
      data() {
        return {
            newTodoItem:''
        };      
      },
      methods: {
       addTodo: function() {
           let input = this.newTodoItem;
           this.$emit('add',input)
           this.newTodoItem = '';
        },
       clearInput: function() {
           this.newTodoItem = '';
        }
          }
      };

</script>
<style scoped>

</style>