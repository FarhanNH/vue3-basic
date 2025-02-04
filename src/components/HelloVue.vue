<script setup>
console.info('HelloVue');
const hello = '<h1>Hello Vue<h1/>';
// const classHello = 'hello';
// const id = 'hello';
const buttonDisabled = true;
const data = {
  id: 'hello',
  class: 'hello',
};

function helloFunction() {
  return 'Hello World';
}
</script>
<template>
  <!-- <h1 :id v-bind:class="classHello">{{ hello }}</h1> -->
  <h1 v-bind="data">{{ hello.toUpperCase() }}</h1>
  <!-- <div :class="classHello" v-html="hello"></div> -->
  <h2>{{ 100 * 200 }}</h2>
  <h2>{{ helloFunction() }}</h2>
  <div :class="data.class" v-html="hello"></div>
  <button :disabled="buttonDisabled">Button</button>
</template>

<style>
.hello {
  color: green;
}
</style>
