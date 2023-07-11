<template>
  <div>

  </div>
</template>

<script>
import { reactive } from 'vue'

const book = reactive({
  auth: 'Vue Team',
  year: '2020',
  title: 'Vue 3 Guide',
  description: '당신은 이 책을 지금 바로 읽습니다;',
  price: '무료'
})

let { author, title } = book

export default {
  setup() {
    // ref -> Object
    const count = ref(0);
    const state = reactive({
      count,
    });
    count.value++;
    count.value++;
    // console.log(count.value);
    // console.log('state.count: ', state.count);

    // ref -> Array
    const message = ref('Hello');
    const arr = reactive([message]);
    console.log('arr[0]: ', arr[0].value);
    return {};
  }
}
</script>

<style lang="scss" scoped>

</style>