<script setup>
// Fallthrough Attributes, Syaratnya di dalam child component harus single element
import MyButton from './MyButton.vue';
import Container from './Container.vue';

function clickHandler() {
  alert('Button clicked');
}
</script>
<template>
  <Container>
    <template #header="attributes">
      <h1>Button App {{ attributes.counter }}</h1>
    </template>
    <!-- <MyButton class="button" @click="clickHandler" name="John" contoh="Doe" /> -->
    <template v-slot:default="attributes">
      <MyButton class="button" @click="clickHandler" :name="attributes.counter" contoh="Doe" />
    </template>
    <template v-slot:footer>
      <p>Copyright 2025 @FarhanNH</p>
    </template>
  </Container>
</template>

<style scoped>
.button {
  background-color: #4caf50;
  border: none;
  color: white;
}
</style>
