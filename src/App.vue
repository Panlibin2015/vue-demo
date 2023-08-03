<script setup>
import { ref, computed, reactive } from 'vue';
const isActive = ref(true);

const classObject = computed(() => ({
  active: isActive.value,
}));

function changeActive() {
  isActive.value = !isActive.value;
}

// 绑定数组
const activeClass = ref('active');
const fontStyleClass = ref('fontStyle');

// 样式对象
const styleObject = reactive({
  color: 'red',
  fontSize: '13px',
});
</script>

<template>
  <h1>绑定Class一</h1>
  <div v-bind:class="{ active: isActive }">绑定样式</div>
  <button @click="changeActive()">改变样式</button>
  <h1>绑定Class二</h1>
  <div
    class="fontStyle"
    v-bind:class="{ active: isActive, fontStyle2: isActive }"
  >
    绑定样式
  </div>
  <h1>绑定Class三</h1>
  <div :class="classObject">绑定样式</div>

  <h1>绑定Class三</h1>
  <div :class="[activeClass, fontStyleClass]">绑定数组</div>

  <h1>绑定Class四</h1>
  <div :class="[isActive ? 'active' : 'fontStyle']">绑定数组</div>
  <hr />

  <h1>绑定Style</h1>
  <div :style="{ 'font-size': 18 + 'px', color: 'blue' }">绑定Style</div>

  <h1>绑定Style二</h1>
  <div :style="styleObject">绑定Style</div>
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
