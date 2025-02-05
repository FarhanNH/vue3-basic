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

function increment(value) {
  counter.value += value;
}
</script>

<template>
  <CounterStateless name="John" :counter="counter" :increment="1" @click="increment" />
  <CounterStateless name="Doe" :counter="counter" :increment="2" @click="increment" />
  <!-- <CounterStateless name="John" :counter="counter" @click="() => (counter += 1)" />
  <CounterStateless name="Doe" :counter="counter" @click="() => (counter += 2)" /> -->
  <!-- <button @click="counter++">Increase</button> -->
  <div v-for="(item, index) in items" :key="index">
    <Counter :name="item.name" :initial-count="item.initialCount" />
  </div>
</template>

<style scoped></style>
