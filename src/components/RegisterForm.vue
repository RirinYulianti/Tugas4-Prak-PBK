<template>
    <div class="card">
      <h2>Register</h2>
      <form @submit.prevent="handleSubmit">
        <input type="text" v-model="username" placeholder="Username" required />
        <input type="password" v-model="password" placeholder="Password" required />
        <input type="email" v-model="email" placeholder="Email" required />
        <button type="submit">Register</button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { defineEmits } from 'vue';
  
  const emit = defineEmits(['register']);
  
  const username = ref('');
  const password = ref('');
  const email = ref('');
  
  function handleSubmit() {
    emit('register', { username: username.value, password: password.value, email: email.value });
  }
  </script>
  
  <style scoped>
  .card {
    position: fixed;
    top: 25%;
    left: 40%;
    background-color: transparent;
    border: 1px solid white;
    backdrop-filter: blur(10px);
    padding: 5em;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  h2 {
    margin-bottom: 2em;
    color: white;
    font-weight: bold;
  }
  
  input {
    display: block;
    width: 100%;
    margin-bottom: 1em;
    padding: 1em;
    justify-content: center;
    align-items: center;
    background-color: transparent;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  button {
    width: 100%;
    padding: 1em;
    border: none;
    margin-left: 15px;
    background-color: #007BFF;
    color: white;
    cursor: pointer;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  