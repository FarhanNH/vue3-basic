<script setup>
import { inject } from 'vue';
import ProfileAddress from './ProfileAddress.vue';

const profile = inject('profile');
</script>
<template>
  <h1>Profile</h1>
  <p>Name: {{ profile.name }}</p>
  <p>Email: {{ profile.email }}</p>
  <ProfileAddress />
</template>

<style scoped></style>
