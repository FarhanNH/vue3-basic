<script setup>
const items = [
  { id: 1, name: 'item a', done: true },
  { id: 2, name: 'item b', done: false },
  { id: 3, name: 'item c', done: false },
];
</script>

<template>
  <h1>Todo List</h1>
  <template v-for="item in items">
    <ul v-if="!item.done" :key="item.id">
      <li v-for="(value, key) in item" :key="key">{{ key }} : {{ value }}</li>
    </ul>
  </template>
  <hr />
  <ul>
    <li v-for="item in items" :key="item.id">
      {{ item.name }}
    </li>
  </ul>
  <hr />
  <div v-for="n in 3" :key="n">
    <h3>Hello {{ n }}</h3>
  </div>
</template>

<style></style>
