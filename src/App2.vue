<script setup>
import { ref } from 'vue';
// `setup` 是一个特殊的钩子，专门用于组合式 API。
const count = ref(0);
function increment() {
  // 在 JavaScript 中需要 .value
  count.value++;
}
</script>

<template>
  <div>{{ count }}</div>
  <button @click="count++">按钮</button>
  <button @click="increment">自增</button>
</template>

<style></style>
