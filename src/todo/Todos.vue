<template>
  <section class="todos">
    <ul>
      <li v-for="(todoItem, index) in todolist" :key="index">
        <i class="checkBtn fas fa-check" aria-hidden="true"></i>
        {{todoItem}}  
        <span class="remove-btn" type ="button" v-on:click="removeTodo">
          <i class="fas fa-minus-square"></i>
        </span>
      </li>
    </ul>
  </section>
</template>
<script>
export default {
     props: ['todolist'],
     methods: {
       removeTodo (todoItem, index) {
         this.$emit('remove', todoItem, index);
       }
     }
};

</script>

<style scoped>
    li {
      text-align: center;
      list-style: none;
    }
</style>