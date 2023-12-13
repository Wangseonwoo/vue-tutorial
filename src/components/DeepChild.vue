<template>
  <div class="card">
    <div class="card-header"> Deep Child Component</div>
    <div class="card-body">
      <p>staticMessage: {{ staticMessage }}</p>
      <p>message: {{ message }}</p>
      <p>count: {{ count }}</p>
    </div>
  </div>
</template>

<script>
import { inject } from 'vue';

export default {
  setup () {
    const staticMessage = inject('static-message', 'default message'); // 상위 컴포넌트에서 provide로 제공한 데이터를 inject를 활용하여 받아옴 default 활용 가능
    const { message, updateMessage } = inject('message');
    updateMessage('!');
    const count = inject('count');
    return { staticMessage, message, count }
  }
}
</script>

<style lang="scss" scoped>

</style>