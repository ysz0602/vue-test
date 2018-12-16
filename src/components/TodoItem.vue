<template>
  <li @mouseenter="handleEnter(true)" @mouseleave="handleEnter(false)" :style="{background:bgColor}">
    <label>
      <input type="checkbox" v-model="todo.complete"/>
      <span>{{todo.title}}</span>
    </label>
    <button v-show="isShow" @click="deleteItem">删除</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: Object,
    deleteTodo:Function,
    index: Number,
  },
  data(){
    return {
      bgColor: 'white', // 默认背景颜色
      isShow: false // 默认不显示
    }
  },
  methods:{
    handleEnter(isEnter){
      if(isEnter){
        this.bgColor = 'red'
        this.isShow = true;
      } else {
        this.bgColor = 'white'
        this.isShow = false;
      }
    },
    deleteItem(){
      const { todo, index, deleteTodo} = this
      if(window.confirm(`确认删除${todo.title}吗?`)){
        deleteTodo(index)
      }
    }
  }
}
</script>

<style>

</style>
