<template>
  <div class="container py-4">
    <div class="card">
      <div class="card-header">ProvideInject Component</div>
      <div class="card-body">
        <button @click="count++">Click</button>  
        <Child></Child>
      </div>
    </div>
  </div>
</template>

<script>
import { provide, readonly, ref } from 'vue';
import Child from './Child.vue';

export default {
    setup() {
      const staticMessage = 'static message';
      const message = ref('message');
      const count = ref(10);
      const updateMessage = appendMessage =>{
        message.value = message.value + appendMessage;
      }
      provide('static-message', staticMessage); // provide를 활용하여 Prop Drilling을 해결할수 있다 -> 계층 구조에 상관없이 자식구조에게 데이터 전송가능
      provide('message', { message: readonly(message), updateMessage });  // 데이터를 받는 자식 컴포넌트는 inject를 사용하여 받는다.
      provide('count', count);
        return { count };
    },
    components: { Child }
}
</script>

<style lang="scss" scoped>

</style>