<template>
  <div class="card">
    <div v-if="hasHeader" class="card-header">
      <slot name="header"></slot>
    </div>
    <div class="card-body">
      <slot :child-mssage="childMessage" helloMessage="안녕하세요">#body</slot> <!-- props처럼 부모요소에게 값을 바인딩 할수있다 -->
    </div>
    <div v-if="$slots.footer" class="card-footer text-muted"> <!-- $slots 내장 객체를 사용하여 값이 없으면 렌더링이 안되게 가능하다  -->
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
  setup (props, {slots}) {
    // context.slots
    const hasHeader = computed(()=> !!slots.header);
    const childMessage = ref('자식 컴포넌트 메시지');

    return { childMessage, hasHeader }
  }
}
</script>

<style lang="scss" scoped>

</style>