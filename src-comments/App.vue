<template>
  <div id="app">
    <header>
      sdf
    </header>
    <div class="container">
      <Add :addComment="addComment"/>
      <List :comments="comments" :deleteComment="deleteComment"/>
    </div>
  </div>
</template>

<script>
import Add from './components/Add.vue';
import List from './components/List.vue';

export default {
  name: 'app',
  data(){
    return {
      comments: [ // 数据在哪个组件， 更新数据的行为就应该定义在哪个组件
        {
          name: 'Bob',
          content: 'Vue 还不错'
        },
        {
          name: 'Cat',
          content: 'Vue so easy'
        },
         {
          name: 'Bz',
          content: 'Vue so so'
        }
      ]
    }
  },
  methods: {
    // 添加评论
    addComment(comment){
      this.comments.unshift(comment);
    },
    // 删除指定下标的评论
    deleteComment(index){
      this.comments.splice(index, 1);
    }
  },
  components: {
    Add,
    List
  }
}
</script>

<style>

</style>
