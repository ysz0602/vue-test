<template>
  <ul>
      <TodoItem v-for="(todo, index) in todos" :todo="todo" :key="index" :deleteTodo="deleteTodo" :index="index"/>
  </ul>
</template>
<script>
import TodoItem from './TodoItem.vue';
export default {
    props: {
        todos:Array,
        deleteTodo: Function
    },
    data(){
        return {
        
        }
    },
    components: {
        TodoItem,
    }
}
</script>

<style>

</style>
