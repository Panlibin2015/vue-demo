<script setup>
import { ref, computed, reactive } from 'vue';
const count = ref(0);
const name = ref('Vue.js');

function greet(event) {
  alert(`Hello ${name.value}!`);
  // `event` 是 DOM 原生事件
  if (event) {
    alert(event.target.tagName);
  }
}

function say(message) {
  alert(message);
}

function warn(message, event) {
  // 这里可以访问原生事件
  if (event) {
    event.preventDefault();
  }
  alert(message);
}
</script>

<template>
  <button @click="count++">按钮{{ count }}</button>
  <button @click="greet()">Greet</button>
  <button @click="say('Hello')">Say</button>
  <button @click="warn('Say', $event)">Warn</button>
  <!-- 使用内联箭头函数 -->
  <button @click="(event) => warn('Form cannot be submitted yet.', event)">
    Submit
  </button>
</template>

<style></style>
