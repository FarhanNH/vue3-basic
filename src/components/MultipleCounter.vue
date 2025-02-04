<script setup>
import { ref } from 'vue';
import Counter from './Counter.vue';
import CounterStateless from './CounterStateless.vue';
const items = ref([
  {
    name: 'John',
    initialCount: 0,
  },
  {
    name: 'Jane',
    initialCount: 0,
  },
  {
    name: 'Jack',
    initialCount: 0,
  },
]);
const counter = ref(0);
</script>

<template>
  <CounterStateless name="John" :counter="counter" />
  <CounterStateless name="Doe" :counter="counter" />
  <button @click="counter++">Increase</button>
  <div v-for="(item, index) in items" :key="index">
    <Counter :name="item.name" :initial-count="item.initialCount" />
  </div>
</template>

<style scoped></style>
