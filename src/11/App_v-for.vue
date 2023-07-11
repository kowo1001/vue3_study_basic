<template>
  <div>
    <ul>
      <template v-for="(item, index) in evenItems">
        <!-- <li v-if="item.id % 2 === 0"> -->
          ID: {{ item.id }} 인덱스: {{ index }}, {{ item.message }}
        <!-- </li> -->
      </template>
      <li v-for="(value, key, index) in myObject" :key="key">
        {{ key }} - {{ value }} - {{ index }}
      </li>
    </ul>
    <hr />
    <ul>
      <li v-for="(value, key, index) in myObject">
      {{ index }} - {{ key }} - {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
import { reactive, computed } from 'vue';

export default {
  setup () {
    const items = reactive([
      { id: 1, message: 'JAVA' },
      { id: 2, message: 'HTML' },
      { id: 3, message: 'CSS' },
      { id: 4, message: 'JavaScript' },
    ])    

    const myObject = reactive({
      title: '제목',
      author: '홍길동',
      publishedAt: '2016-01-01',
    });

    const evenItems = computed(() => items.filter(item => item.id % 2 === 0));
    return { items, evenItems, myObject }
  }
}
</script>

<style lang="scss" scoped>

</style>