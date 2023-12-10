<template>
  <div class="card">
    <div class="card-body">
      <span class="badge bg-secondary ">{{ typeName }}</span>
      <h5 class="card-title mt-2 ">{{title}}</h5>
      <p class="card-text">{{ content }}</p>
      <a href="#" :class="isLikeClass" class="btn">좋아요</a>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    type: {
      type: String,
      default: 'news',
    },
    title: {
      type: String,
      required: true
    },
    content: {
      type: String,
      // required: true
    },
    isLike: {
      type: Boolean,
      default: false
    }
  },

  setup (props) {
    const isLikeClass =computed(()=> props.isLike ?'btn-danger' : 'btn-outline-danger');
    const typeName = computed(() => props.type === 'news' ? '뉴스' : '공지사항');
    return { isLikeClass, typeName, }
  }
}
</script>

<style lang="scss" scoped>

</style>