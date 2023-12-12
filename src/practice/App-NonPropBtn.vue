<template>
  <div class="p-3 bg-danger">
    <button type="button" class="btn btn-primary" v-bind="$attrs"> My Button</button> <!-- v-bind="$attrs"를 활용 원하는 요소에 상속 -->
  </div>
</template>

<script>
export default {
  inheritAttrs: false,  // 이 기능이 없다면 root element에 nonProps가 상속 되기 때문에 원하는 요소에 이벤트를 상속을 못한다
                        // 만약 다중 노드라면 어디에 적용을 할것인지 v-bind="$attrs"를 사용하여 명시해줘야 한다
  setup () {
    

    return {}
  }
}
</script>

<style lang="scss" scoped>

</style>