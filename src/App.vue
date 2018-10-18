<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>

    <router-view />
  </div>
</template>

<script>
import Skills from './components/Skills'

export default {
  name: 'App',
  components: {
    Skills
  }
}
</script>

<style>
#app {
  width: 50%;
}
body {
  align-items: center;
  background-color: #eeeeee;
  display: grid;
  font-family: 'Montserrat', sans-serif;
  grid-template-rows: auto;
  justify-items: center;
}
body.html {
  height: 100%;
  margin: 0;
}
nav {
  padding: 20px 20px 20px 0;
}
nav a {
  padding: 10px;
  text-decoration: none;
  background: #fff;
  border-radius: 3px;
  color: rgb(0, 110, 255);
  font-weight: bold;
  margin-right: 15px;
}
</style>
