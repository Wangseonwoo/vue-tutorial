<template>
  <div class="row">
    <div class="col col-2">
      <select v-model="type" class="form-select" aria-label="Default select example">
        <option value="news">뉴스</option>
        <option value="notice">공지사항</option>
      </select>
    </div>
    <div class="col col-8">
      <input v-model="title" type="text" class="form-control">
    </div>
    <div class="col col-2 d-grid">
      <button class="btn btn-primary" @click="createPost">추가</button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  emits: ['createPost'],
  setup (props, { emit }) {
    const type = ref('news');
    const title = ref('');
    const createPost = () => {
      const newPost = {
        type: type.value,
        title: title.value,
      }
      emit('createPost', newPost);
    }

    return { title, createPost, type, }
  }
}
</script>

<style lang="scss" scoped>

</style>