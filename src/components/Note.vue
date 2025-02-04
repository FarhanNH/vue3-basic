<script setup>
import { onBeforeMount, onMounted, onUpdated, reactive, ref, useTemplateRef } from 'vue';

const notes = reactive([]);
const note = ref('');
const noteInput = useTemplateRef('noteInput');
const notesList = useTemplateRef('notesList');

function addNote() {
  notes.push(note.value);
  note.value = '';
  noteInput.value.focus();
  if (notesList.value) {
    notesList.value.forEach((li) => {
      console.log(li.textContent);
    });
  }
}

onBeforeMount(() => {
  console.log('onBeforeMount');
});

onMounted(() => {
  console.log('onMounted');
});

onUpdated(() => {
  console.log('onUpdated');
});
</script>
<template>
  <h1>Create Note</h1>
  <div>
    <input type="text" v-model="note" ref="noteInput" />
    <button @click="addNote">Add</button>
  </div>
  <h1>Note List</h1>
  <ul>
    <li v-for="(note, index) in notes" :key="index" ref="notesList">
      {{ note }}
    </li>
  </ul>
</template>
<style></style>
