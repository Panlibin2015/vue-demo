<script setup>
import { reactive, computed } from 'vue';

const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery',
  ],
});

// 一个计算属性 ref
// 每次访问都会被缓存
const publishedBooksMessage = computed(() => {
  return author.books.length > 3 ? 'Yes' : 'No';
});
// const publishedBooksMessage = author.books.length > 3 ? 'Yes' : 'No';

// 每次都需要重新计算
function calculateBooksMessage() {
  return author.books.length > 0 ? 'Yes' : 'No';
}

function addBook() {
  author.books.push('BOok');
}
</script>

<template>
  <p>Has published books:</p>
  ref：
  <span>{{ publishedBooksMessage }}</span>
  <br />
  方法获取：
  <span>{{ calculateBooksMessage() }}</span>
  <br />
  <button @click="addBook">添加📚</button>
</template>
