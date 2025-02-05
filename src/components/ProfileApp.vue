<script setup>
import { provide, reactive } from 'vue';
import Profile from './Profile.vue';

const profile = reactive({
  name: 'John Doe',
  email: 'john@example.com',
});
provide('profile', profile);
</script>
<template>
  <input type="text" v-model="profile.name" placeholder="Name" />
  <Profile />
</template>

<style scoped></style>
