<template>
  <div>
    <li v-for="(item, index) in items" :key="item.id">
      {{ item.message }}
    </li>
    <ul>
      <li 
        v-for="user in activeUsers"
        :key="user.id"
      >
      {{ user.name }}
      </li>
    </ul>
    <h2 v-if="visible">Hello Vue3!</h2>
    <h1 v-else>false 입니다.</h1>
    <button v-on:click="visible = !visible">toggle</button>
    <hr />
    <button v-on:click="type = 'A'">A</button>
    <button v-on:click="type = 'B'">B</button>
    <button v-on:click="type = 'C'">C</button>
    <button v-on:click="type = 'D'">D</button>

    <h2 v-if="type === 'A'">A 입니다.</h2>
    <h2 v-else-if="type === 'B'">B 입니다.</h2>
    <h2 v-else-if="type === 'C'">C 입니다.</h2>
    <h2 v-else>A, B, C가 아닙니다.</h2>
    <hr />
    <template v-if="visible">
      <h1>Title</h1>
      <p>Paragraph 1</p>
      <p>Paragraph 2</p>
    </template>
    <hr />
    <h1 v-show="ok">Title 입니다.</h1>
    <button @click="ok = !ok">show toggle </button>
  </div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
  setup() {
    const myObject = reactive({
      title: '제목입니다.',
      author: '홍길동',
      publishedAt: '2016-04-10',
    });

    const items = reactive([
      { id: 1, message: 'Java' },
      { id: 2, message: 'HTML' },
      { id: 3, message: 'CSS' },
      { id: 4, message: 'Javascript' },
    ]);

    
    const visible = ref(false);
    const type = ref('A');
    const ok = ref(true);
    return { visible, type, ok, items }
  },
};
</script>

<style lang="scss" scoped>

</style>