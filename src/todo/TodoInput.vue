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

</style>