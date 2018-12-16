<template>
    <div>
        <h3>评论回复:</h3>
        <h2 v-show="comments.length===0">暂无评论</h2>
        <ul>
            <Item v-for="(comment, index) in comments" :key="index" :comment="comment" :deleteComment="deleteComment" :index="index"/>
        </ul>
    </div>
</template>
<script>
import Item from './Item.vue';
export default {
    props: ['comments', 'deleteComment'],
    components: {
        Item
    }
}
</script>
<style>

</style>


