<template>
  <div class="container py-4">
    <!-- <LifecycleChild></LifecycleChild> -->
  </div>
</template>

<script>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue';
// import LifecycleChild from './LifecycleChild.vue'

export default {
  components: {
    // LifecycleChild,
  },
  setup () {
    console.log('setup');
    const message =ref('');
    // onBeforeMount(()=> {
    //   console.log('onBeforeMount');
    // })
    // onMounted(()=> {
    //   console.log('onMounted');
    // })
    onBeforeUpdate(()=> {
      console.log('onBeforeUpdate');
    });
    onUpdated(()=> {
      console.log('onUpdated');
    })
    return {message,}
  },
  // beforeCreate() {
  //   console.log('beforeCreate');
  // },
  // created() {
  //   console.log('created');
  // },
}
</script>

<style lang="scss" scoped>

</style>