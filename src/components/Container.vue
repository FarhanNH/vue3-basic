<script setup>
import { ref, useSlots } from 'vue';

// const slots = useSlots();
const counter = ref(0);
</script>
<template>
  <div>
    <slot v-if="$slots.header" name="header" :counter="counter">
      <p>Default Header</p>
    </slot>
  </div>
  <div>
    <slot v-if="$slots.default" name="default" :counter="counter">
      <p>Default Content</p>
    </slot>
  </div>
  <div>
    <slot v-if="$slots.footer" name="footer" :counter="counter">
      <p>Default Footer</p>
    </slot>
  </div>
  <!-- <div>
    <slot v-if="slots.header" name="header" :counter="counter">
      <p>Default Header</p>
    </slot>
  </div>
  <div>
    <slot v-if="slots.default" name="default" :counter="counter">
      <p>Default Content</p>
    </slot>
  </div>
  <div>
    <slot v-if="slots.footer" name="footer" :counter="counter">
      <p>Default Footer</p>
    </slot>
  </div> -->
  <button @click="counter++">Increase</button>
</template>

<style scoped></style>
