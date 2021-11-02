<template>
  <div id="app">
    <img alt="myPhoto" src="./assets/img/photo.jpg" class="my_photo" />
    <HelloWorld msg="My name is Elaine" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
.my_photo {
  width: 200px;
}
</style>
