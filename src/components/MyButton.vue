<script setup>
// Disable attribut from parent component
// defineOptions({
//   inheritAttrs: false,
// });

import { useAttrs } from 'vue';

const props = defineProps(['test']);
console.log(props);

const attributes = useAttrs();
console.log(attributes);
</script>
<template>
  <button>My Button : {{ attributes.name }}</button>
</template>
