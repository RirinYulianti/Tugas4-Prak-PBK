<template>
    <div class="card">
      <h2>Login</h2>
      <form @submit.prevent="handleSubmit">
        <input type="text" v-model="username" placeholder="Username" required />
        <input type="password" v-model="password" placeholder="Password" required />
        <button type="submit">Login</button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { defineEmits } from 'vue';
  
  const emit = defineEmits(['login']);
  
  const username = ref('');
  const password = ref('');
  
  function handleSubmit() {
    emit('login', { username: username.value, password: password.value });
  }
  </script>
  
  <style scoped>
  .card {
    position: fixed;
    top: 25%;
    left: 42%;
    background-color: transparent;
    backdrop-filter: blur(10px);
    padding: 3em;
    border: 1px solid white;
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
    padding: 0.5em;
    background-color: transparent;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  button {
    width: 100%;
    padding: 0.5em;
    margin-left: 5px;
    border: none;
    background-color: #007BFF;
    color: white;
    cursor: pointer;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  