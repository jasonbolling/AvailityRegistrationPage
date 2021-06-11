<template>
  <div id="app">
  <img src="./assets/pngkey.com-youtube-subscribe-button-png-4746448.png">
  <h1>Welcome, Please Enter Your Information</h1>
  <RegistrationInterface></RegistrationInterface>
  <Vue></Vue>
  </div>
</template>

<script>
import RegistrationInterface from './components/RegistrationInterface.vue';
import Vue from 'vue';
import Vuetify from 'vuetify';
Vue.use(Vuetify);
export default {
  name: 'App',
  components: {
    RegistrationInterface,
    Vue,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img {
    align-content: center;
    width: 200px;
}
</style>
