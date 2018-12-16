<template>
  <div>
      <label>
          <input type="checkbox" v-model="isAllCheck"/>
      </label>
      <span>
          <span>已完成{{completeSize}}</span>/全部{{todos.length}}
      </span>
      <button v-show="completeSize" @click="deleteCompleteTodos">删除已完成任务</button>
  </div>
</template>

<script>
export default {
    props:{
        todos:Array,
        deleteCompleteTodos: Function,
        selectAllTodos: Function
    },
    computed:{
        completeSize(){
            return this.todos.reduce((prevTotal, todo) => prevTotal+(todo.complete?1:0),0)
        },
        isAllCheck:{
            get(){
                return this.completeSize === this.todos.length;
            },
            set(value){ //value是当前checkout最新的值
                this.selectAllTodos(value);   
            }
        }
    }
}
</script>

<style>

</style>
