<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Jumbotron from './components/Jumbotron.vue'
</script>

<template>
  <Header />
  <Jumbotron />
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + Vite" />
</template>

<style>
*, *::before, *::after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
img {
  width: auto;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #212529;
}

</style>
