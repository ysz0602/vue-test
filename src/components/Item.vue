<template>
    <li>
        <div class="handle">
            <a href="javascript:;" @click="deleteItem">删除</a>
        </div>
        <p class="user"><span>{{ comment.name}}</span>说:</p>
        <p class="contence">{{comment.content}}</p>
    </li>
</template>
<script>
export default {
    props: {
        comment: Object,
        deleteComment: Function,
        index: Number
    },
    methods:{
        deleteItem(){
            const {comment,index,deleteComment} = this;
            if(window.confirm(`确定删除${comment.name}的评论吗?`)){
                deleteComment(index);
            }
        }
    }
}
</script>
<style>

</style>


