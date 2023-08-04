<script setup>
import { ref, computed, reactive } from 'vue';

const items = ref([{ message: 'Foo' }, { message: 'Bar' }]);
const myObject = reactive({ name: 'LeaBing', age: 12 });
</script>

<template>
  <li v-for="item in items">
    {{ item.message }}
  </li>

  <hr />
  <span v-for="item in items">{{ item.message }} <br /></span>
  <hr />
  <li v-for="(item, index) in items">{{ index }} - {{ item.message }}</li>
  <hr />
  <h1>v-for 与对象</h1>
  <li v-for="(item, key, index) in myObject">
    {{ index }} - {{ key }}-{{ item }}
  </li>
  <hr />
  <h1></h1>
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
