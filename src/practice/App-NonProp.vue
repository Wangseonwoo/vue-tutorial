<template>
  <div class="container py-4">
    <AppNonPropBtn class="mybutton" id="hi" @click="sayHi"></AppNonPropBtn> 
  </div> 
</template>

<script>
import AppNonPropBtn from './App-NonPropBtn.vue';

export default {
    setup() {
      const sayHi = ()=> {
        alert('Hi~~');
      };
        return { sayHi, }
    },
    components: { AppNonPropBtn }
}
</script>

<style lang="scss" scoped>

</style>