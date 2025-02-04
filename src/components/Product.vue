<script setup>
import { onWatcherCleanup, ref, watch, watchEffect } from 'vue';
import ProductDetail from './ProductDetail.vue';

const productId = ref('product1');
// const productId = ref('');
const product = ref(null);

watchEffect(async () => {
  onWatcherCleanup(() => {
    console.log('cleanup');
  });

  console.log('call watch callback');
  const response = await fetch(`/${productId.value}.json`);
  product.value = await response.json();
});

// watch(
//   productId,
//   async (newVal, oldVal) => {
//     const response = await fetch(`/${newVal}.json`);
//     product.value = await response.json();
//     //   if (newVal) {
//     //     const response = await fetch(`/${newVal}.json`);
//     //     product.value = await response.json();
//     //   } else {
//     //     product.value = null;
//     //   }
//   },
//   { immediate: true }
// );
</script>
<template>
  <label for="productId"
    >Product Id :
    <select v-model="productId">
      <option value="product1">Product 1</option>
      <option value="product2">Product 2</option>
      <option value="product3">Product 3</option>
    </select>
  </label>
  <div v-if="product">
    <ProductDetail :id="product.id" :name="product.name" :price="product.price" />
    <!-- <h1>Product</h1>
    <p>id : {{ product.id }}</p>
    <p>name : {{ product.name }}</p>
    <p>price : {{ product.price }}</p> -->
  </div>
</template>
<style></style>
