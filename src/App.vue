<template>
  <bg />
  <div id="app">
    <Navbar @show-login="showLoginForm" @show-register="showRegisterForm" />
    <div class="content">
      <slot>
        <LoginForm v-if="showLogin" @login="handleLogin" />
        <RegisterForm v-if="showRegister" @register="handleRegister" />
      </slot>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Navbar from './components/Navbar.vue';
import LoginForm from './components/LoginForm.vue';
import RegisterForm from './components/RegisterForm.vue';
import bg from './components/background.vue';

const showLogin = ref(true);
const showRegister = ref(false);

function showLoginForm() {
  showLogin.value = true;
  showRegister.value = false;
}

function showRegisterForm() {
  showLogin.value = false;
  showRegister.value = true;
}

function handleLogin(data) {
  alert(`Login with Username: ${data.username} and Password: ${data.password}`);
  showLogin.value = false;
}

function handleRegister(data) {
  alert(`Register with Username: ${data.username}, Email: ${data.email} and Password: ${data.password}`);
  showRegister.value = false;
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

.content {
  max-width: 400px;
  margin: auto;
  padding: 2em;
}
</style>
