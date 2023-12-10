<template>
  <main>
    <div class="container py-4">
      <PostCreate @create-post="createPost"></PostCreate>
      <hr class="my-4">

      <div class="row g-3">
        <div v-for="post in posts" :key="post.id" class="col col-4">
          <AppCard :title="post.title" :content="post.content" :is-like="post.isLike" :type="post.type"></AppCard>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { reactive } from "vue";
import AppCard from "./AppCard.vue"
import PostCreate from "./PostCreate.vue";

export default {
  components: {
    AppCard,
    PostCreate
},
  setup () {
    const posts = reactive([
      {id: 1, title: '제목1', content: '내용1', isLike: true, type: 'news'},
      {id: 2, title: '제목2', content: '내용2', isLike: true, type: 'news'},
      {id: 3, title: '제목3', content: '내용3', isLike: true, type: 'news'},
      {id: 4, title: '제목4', content: '내용4', isLike: true, type: 'news'},
      {id: 5, title: '제목5', content: '내용5', isLike: false, type: 'notice'},
      {id: 6, title: '제목6', content: '내용6', isLike: false, type: 'notice'},
    ])
    const createPost =(newPost)=> {
      posts.push(newPost);
    }

    return { posts, createPost, }
  }
}
</script>

<style lang="scss" scoped>

</style>