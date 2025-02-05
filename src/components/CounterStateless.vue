<script setup>
const { counter, name, increment } = defineProps({
  counter: Number,
  name: String,
  increment: Number,
});
// const { counter, name, increment } = defineProps(['counter', 'name', 'icrement']);
const emits = defineEmits(['click']);
function handleClick() {
  emits('click', increment);
}
</script>
<template>
  <h1>Counter {{ name }} : {{ counter }}</h1>
  <button @click="$emit('click', increment)">Click</button>
  <!-- <button @click="handleClick">Click</button> -->
  <!-- <button @click="emits('click', increment)">Click</button> -->
</template>
<style scoped></style>
