<template>
    <nav class="navbar">
      <button @click="emit('show-login')">Login</button>
      <button @click="emit('show-register')">Register</button>
    </nav>
  </template>
  
  <script setup>
  import { defineEmits } from 'vue';
  
  const emit = defineEmits(['show-login', 'show-register']);
  </script>
  
  <style scoped>
  .navbar {
    position: fixed;
    top: 5%;
    left: 35%;
    backdrop-filter: blur(10px);
    padding: 1em;
    display: flex;
    justify-content: flex-end;
  }
  
  button {
    margin-left: 10px;
    padding: 0.5em 1em;
    border: none;
    margin-left: 100px;
    background-color: #007BFF;
    color: white;
    cursor: pointer;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: #0056b3;
  }
  </style>
  