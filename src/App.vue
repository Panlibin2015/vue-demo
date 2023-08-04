<script setup>
import { ref, computed, reactive } from 'vue';

const text = ref('Hello');
const checked = ref(true);
const checkedNames = ref([]);
</script>

<template>
  <input :value="text" @input="(event) => (text = event.target.value)" />
  <input v-model="text" />
  <br />
  <input v-model.lazy="text" />
  <span>{{ text }}</span>
  <hr />
  <input type="checkbox" id="checkbox" v-model="checked" />
  <label for="checkbox">{{ checked }}</label>
  <hr />
  <div>Checked names: {{ checkedNames }}</div>

  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
  <label for="jack">Jack</label>

  <input type="checkbox" id="john" value="John" v-model="checkedNames" />
  <label for="john">John</label>

  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
  <label for="mike">Mike</label>
</template>

<style></style>
