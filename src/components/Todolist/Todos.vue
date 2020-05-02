<template>
    <div>
        <section class="todos">
          <li v-for="(todoItem, index) in propsdata" :key="todoItem">
            <i class="checkBtn fas fa-check" aria-hidden="true"></i>
           {{todoItem}}  
           <span class="remove-btn" type ="button" v-on:click="removeTodo(todoItem, index)">
             <i class="fas fa-minus-square"></i>
           </span>
          </li>
        </section>
    </div>
</template>
<script>
export default {
     props: ['propsdata'],
     methods: {
       removeTodo(todoItem, index) {
         this.$emit('removeTodo', todoItem, index);
       }
     }
}

</script>

<style scoped>
    
</style>