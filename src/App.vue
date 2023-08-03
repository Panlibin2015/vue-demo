<script>
import { ref } from 'vue';

export default {
  // `setup` 是一个特殊的钩子，专门用于组合式 API。
  setup() {
    const count = ref(0);

    function increment() {
      // 在 JavaScript 中需要 .value
      count.value++;
    }
    // 将count暴露给模板
    return {
      count,
      increment,
    };
  },
};
</script>

<template>
  <div>{{ count }}</div>
  <button @click="count++">按钮</button>
  <button @click="increment">自增</button>
</template>

<style></style>
