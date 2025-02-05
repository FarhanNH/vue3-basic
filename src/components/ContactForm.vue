<script setup>
const contact = defineModel({
  type: Object,
  required: true,
  default: {
    name: '',
    email: '',
    age: 0,
    type: 'Regular',
    complain: false,
    message: '',
  },
  get: (value) => {
    value.email = value.email.toLowerCase();
    return value;
  },
});
</script>
<template>
  <h1>Contact Us</h1>
  <form>
    <div>
      <label for="name"
        >Name:
        <input type="text" id="name" v-model="contact.name" />
      </label>
    </div>
    <div>
      <label for="email"
        >Email:
        <input type="email" id="email" v-model="contact.email" />
      </label>
    </div>
    <div>
      <label for="age"
        >Age:
        <input type="number" id="age" v-model.number="contact.age" />
      </label>
    </div>
    <div>
      <label for="type"
        >Type:
        <select id="type" v-model="contact.type">
          <option value="Regular">Regular</option>
          <option value="VIP">VIP</option>
        </select>
      </label>
    </div>
    <div>
      <label for="complain"
        >Complain:
        <input type="checkbox" id="complain" v-model="contact.complain" />
      </label>
    </div>
    <div>
      <label for="message"
        >Message:
        <textarea id="message" v-model="contact.message"></textarea>
      </label>
    </div>
  </form>
</template>
<style scope></style>
