<template>
  <div>
    {{ teacher.name }}
    <h3>강의가 있습니까?</h3>
    <!-- <p>{{ teacher.lecture.length > 0 ? '있음 😃' : '없음 😅' }}</p> -->
    <p> {{ hasLecture  }}</p>
    <h2> 이름 </h2>
    <p>{{ fullName }}</p>
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup () {
    const teacher = reactive({
      name: '선우',
      lecture: ['html', 'css', 'js'],
    });
    const hasLecture = computed(() =>  teacher.lecture.length > 0 ? '있음 😃' : '없음 😅'); // Computed 는 값이 cashing 되어서 function 보다 비용이 적게듬

    const firstName = ref('홍');
    const lastName = ref('길동');

    // const fullName = computed(() => firstName.value +' ' +lastName.value);
    // console.log('Console 출력' + fullName.value);
    
    const fullName = computed({
      get() {
        return firstName.value +' ' +lastName.value;
      },
      set(value) {
        return [firstName.value, lastName.value] = value.split(" ");
      }
    });
    console.log(fullName.value);
    
    fullName.value = '왕 선우';
    console.log(fullName.value);

    return { teacher, hasLecture, fullName }
  }
}
</script>

<style lang="scss" scoped>

</style>