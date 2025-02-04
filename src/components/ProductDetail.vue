<script setup>
const product = defineProps({
  id: {
    type: Number,
    requered: true,
  },
  name: {
    type: String,
    requered: true,
    validator(value, props) {
      return value.trim().length !== 0;
    },
  },
  price: {
    type: Number,
    requered: true,
    validator(value, props) {
      return value > 0;
    },
  },
});
</script>
<template>
  <h1 id="title">Product</h1>
  <p>Id: {{ product.id }}</p>
  <p>Name: {{ product.name }}</p>
  <p>Price: {{ product.price }}</p>
</template>
<style scoped></style>
