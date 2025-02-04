<script setup>
import { nextTick, ref } from 'vue';

const props = defineProps(['name', 'initialCount']);

// let count = 0;
// let count = ref(0); //Reactive State
let counter = ref({
  count: Number(props.initialCount),
  name: 'John',
});
async function increment() {
  //   count++;
  //   document.getElementById('count').innerText = `Counter : ${count}`;
  //   count.value++;
  counter.value = {
    name: counter.value.name,
    count: counter.value.count + 1,
  };

  counter.value.count++;

  await nextTick(); //Waiting after process for DOM to update
}
function reset() {
  //   count = 0;
  //   document.getElementById('count').innerText = `Counter : ${count}`;
  //   count.value = 0;
  counter.value = {
    count: 0,
    name: 'John',
  };
}
</script>
<template>
  <div>
    <h1 id="count">Counter : {{ props.name }} {{ counter.count }}</h1>
    <button v-on:click="increment">Increase</button>
    <button v-on:click="reset">Reset</button>
  </div>
</template>
<style></style>
