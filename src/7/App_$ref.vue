<template>
  <button @click="increment">{{ count }}</button>
</template>

<script setup>
let count = $ref(0)

function increment() {
  // no need for .value
  count++
}
</script>

<style lang="scss" scoped>

</style>