<script setup>
import { ref, computed, reactive } from 'vue';
const awesome = ref(true);
const type = ref('B');
const ok = ref(true);
</script>

<template>
  <h1>条件渲染 v-if</h1>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <hr />
  <h1>条件渲染 v-else</h1>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>
  <button @click="awesome = !awesome">Toggle</button>
  <hr />
  <h1>条件渲染 v-else-if</h1>
  <div v-if="type === 'A'">A</div>
  <div v-else-if="type === 'B'">B</div>
  <div v-else>NOT A/B</div>
  <hr />
  <h1>条件渲染 v-if template</h1>
  <template v-if="ok">
    <a>a</a>
    <b>b</b>
  </template>
  <hr />
  <h1>条件渲染 v-show</h1>
  <a v-show="awesome">awesome</a>
</template>

<style>
.fontStyle {
  font-size: 45px;
}

.fontStyle2 {
  font-size: 12px;
}

.active {
  display: block;
  color: red;
}
</style>
