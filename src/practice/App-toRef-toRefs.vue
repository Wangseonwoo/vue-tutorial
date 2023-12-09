<template>
  <div>
    <p>author: {{ author }}</p>
    <p>title: {{ title }}</p>
  </div>
</template>

<script>
import { reactive, toRef, toRefs } from 'vue';

export default {
  setup () {
    const book = reactive({
      author: 'Sunwoo',
      year: '2023',
      title: 'Vue3 Pr',
      description: '당신은 뷰3를 공부하고 있습니다.',
      price: '무료',
    });
    // 반응형을 잃어버리는 구조 분해할당
    const { author, title } = book;
    // 반응형을 유지하는 구조 분해할당
    const { year, description } = toRefs(book);
    const price = toRef(book, 'price');
    console.log(typeof author);
    // console.log(typeof year);
    // console.log(typeof price);

    return { author, title, price, description, year };
  }
}
</script>

<style lang="scss" scoped>

</style>