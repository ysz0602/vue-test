<template>
  <div id="app">
    <TodoHeader :addTodo="addTodo"/>
    <TodoList :todos="todos" :deleteTodo="deleteTodo"/>
    <TodoFooter :todos="todos" :deleteCompleteTodos="deleteCompleteTodos" :selectAllTodos="selectAllTodos"/>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue';
import TodoList from './components/TodoList.vue';
import TodoFooter from './components/TodoFooter.vue';
export default {
  name: 'app',
  data(){
    return {
      todos: [
        {title:'吃飯', complete: false},
        {title:'睡觉', complete: true},
        {title:'coding', complete: false},
      ]
    }
  },
  methods: {
    addTodo(todo){
      this.todos.unshift(todo);
    },
    deleteTodo(index){
      this.todos.splice(index, 1);
    },
    // 删除所有选中的todo
    deleteCompleteTodos(){
      this.todos = this.todos.filter(todo =>!todo.complete);
    },
    // 全选/全不选
    selectAllTodos(check){
      this.todos.forEach(todo => todo.complete = check)
    }
  },
  components: {
    TodoHeader,
    TodoList,
    TodoFooter
  }
}
</script>

<style>

</style>
