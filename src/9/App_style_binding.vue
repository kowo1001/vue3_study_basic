<template>
  <div :style="styleObject">
    <div>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
      Error voluptates deserunt fugiat quae sed doloremque ab odit dolore, quod reprehenderit quisquam perspiciatis architecto exercitationem iste,
      beatae nobis amet, at facere!</div>
    </div>
    <button v-on:click="fontSize--">-</button>
    <button v-on:click="fontSize++">+</button>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup () {
    // const styleObject = reactive({
    //   color: 'red',
    //   fontSize: '13px',
    // });
    const fontSize = ref(13);
    const styleObject = computed(() => {
      return {
        color: 'red',
        fontSize: fontSize.value + 'px',
      };
    });
    return { styleObject, fontSize };
  }
}

</script>

<style lang="scss" scoped>

</style>