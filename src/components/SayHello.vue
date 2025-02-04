<script setup>
import { computed, reactive, ref } from 'vue';

const person = reactive({
  firstName: '',
  lastName: '',
  show: false,
});

function sayHello() {
  person.firstName = document.getElementById('firstName').value;
  person.lastName = document.getElementById('lastName').value;
  person.show = true;
}

function reset() {
  person.firstName = '';
  person.lastName = '';
  person.show = false;
  document.getElementById('firstName').value = '';
  document.getElementById('lastName').value = '';
  counter.value = 0;
}

const fullName = computed((oldValue) => {
  console.log('fullName called');
  console.log(oldValue);
  return `Hello ${person.firstName} ${person.lastName}`;
});

const counter = ref(0);

function increment() {
  console.log('increment called');
  counter.value++;
}

// function changeFirstName() {
//   person.firstName = document.getElementById('firstName').value;
// }

// function changeLastName() {
//   person.lastName = document.getElementById('lastName').value;
// }

function changeFirstName(event) {
  person.firstName = event.target.value;
}

function changeLastName() {
  person.lastName = event.target.value;
}
</script>

<template>
  <div>
    <form>
      <button v-on:click="counter++">Increment {{ counter }}</button> <br />
      <!-- <button v-on:click="increment">Increment {{ counter }}</button> <br /> -->
      <input placeholder="First Name" type="text" id="firstName" @input="changeFirstName" /> <br />
      <input placeholder="Last Name" type="text" id="lastName" @input="changeLastName" /> <br />
      <button v-on:click.prevent="sayHello">Say Hello</button>
      <button v-on:click="reset">Reset</button>
      <!-- <h1>
        <div v-if="person.show">Hello,</div>
        {{ person.firstName }} {{ person.lastName }}
      </h1> -->
    </form>
  </div>
  <h1>{{ fullName }}</h1>
</template>

<style></style>
