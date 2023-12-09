<template>
  <div>
    {{ message }}
    <button @click="addMessage">add click</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup () {
    const message =ref('Hello vue!');
    const addMessage = () => {
      message.value = message.value +'!';
    }
    return { message, addMessage }
  }
}
</script>

<style lang="scss" scoped>

</style>