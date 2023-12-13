<template>
  <main>
    <div class="container py-4">
      <!-- <PostCreate @create-post="createPost"></PostCreate> -->
      <!-- <hr class="my-4">
      <div class="row g-3">
        <div v-for="post in posts" :key="post.id" class="col col-4">
          <PostItem :title="post.title" :content="post.content" :is-like="post.isLike" :type="post.type"></PostItem>
        </div>
      </div> -->
      <hr>
      <AppCard>
        <!-- 
        <template v-slot:header>제목입니다.</template>
        <template v-slot:default>내용입니다.</template>
        <template v-slot:footer>푸터입니다.</template> 
        -->
        <template #header>제목입니다.</template>
        <template #default="{childMssage, helloMessage}">내용입니다. <br> 
          {{ childMssage }} <br>
          {{ helloMessage }} 
        </template> <!-- prop처럼 자식 컴포넌트에서 받아올수 있다. -->
        <template #footer>푸터입니다.</template>
        <!-- <template #[slotArgs]>푸터입니다.</template> -->
        <!-- #[slotArgs] ->  v-bind, v-on v-slot 에서 종종 동적으로 변경이 필요할경우 사용 가능히디 -->
        
      </AppCard>
      <hr>
      <AppCard></AppCard>
    </div>
  </main>
</template>

<script>

// import PostItem from "./PostItem.vue"
// import PostCreate from "./PostCreate.vue";
import AppCard from "./AppCard.vue";

export default {
  components: {
    // PostItem,
    // PostCreate,
    AppCard
},
  setup () {
    // PostItme.vue 사용
    // const posts = reactive([
    //   {id: 1, title: '제목1', content: '내용1', isLike: true, type: 'news'},
    //   {id: 2, title: '제목2', content: '내용2', isLike: true, type: 'news'},
    //   {id: 3, title: '제목3', content: '내용3', isLike: true, type: 'news'},
    //   {id: 4, title: '제목4', content: '내용4', isLike: true, type: 'news'},
    //   {id: 5, title: '제목5', content: '내용5', isLike: false, type: 'notice'},
    //   {id: 6, title: '제목6', content: '내용6', isLike: false, type: 'notice'},
    // ])
    // const createPost =(newPost)=> {
    //   posts.push(newPost);
    // }

    // const slotArgs = ref('header'); v-bind, v-on v-slot 에서 종종 동적으로 변경이 필요할경우 사용 가능히디

    return {}
  }
}
</script>

<style lang="scss" scoped>

</style>