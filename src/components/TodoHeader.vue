<template>
  <div class="todo-header">
      <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="title" @keyup.enter="addItem" />
  </div>
</template>

<script>
export default {
    props: {
        addTodo: Function
    },
    data(){
        return {
            title: ''
        }
    },
    methods:{
        addItem(){
            //1. 检查输入的合法性
            const title = this.title.trim();
            if(!title) {
                alert("必须输入")
                return;
            }
            //2.根据输入生成一个TODO对象
            const todo = {
                title,
                complete:false
            }
            //3.添加TODO
            this.addTodo(todo)
            //4.清除
            this.title = '';
        }
    }
}
</script>

<style>

</style>
