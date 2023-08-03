<script setup>
import { reactive } from 'vue';
// `setup` 是一个特殊的钩子，专门用于组合式 API。
const state = reactive({ count: 0 });
function increment() {
  // 在 JavaScript 中需要 .value
  state.count++;
}
</script>

<template>
  <div>{{ state.count }}</div>
  <button @click="state.count++">按钮</button>
  <button @click="increment">自增</button>
</template>

<style></style>
