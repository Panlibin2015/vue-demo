<script setup>
import { ref } from 'vue';
const msg = ref('文本插值');
const isButtonDisabled = ref(true);
const dynamicId = ref('text');
const rawHtml = ref('<span style="color: red">This should be red.</span>');

const objectOfAttrs = {
  id: 'container',
  class: 'wrapper',
};
</script>

<template>
  <div>
    <h1>模板语法</h1>
    <h3>文本插值</h3>
    <span>Message: {{ msg }}</span>
    <h3>原始HTML</h3>
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <h3>Attribute绑定</h3>
    <div v-bind:id="dynamicId"></div>
    <div :id="dynamicId"></div>
    <h3>布尔型Attribute</h3>
    <button :disabled="isButtonDisabled">Button</button>
    <h3>动态绑定多个值</h3>
    <div v-bind="objectOfAttrs"></div>
    <h1>使用JavaScript表达式</h1>
    "{{ var a = 1}}"
  </div>
</template>

<style></style>
