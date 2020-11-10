<template>
  <Navbar />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <Projects></Projects>
  <Contact></Contact>
  <Parcours />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";
import Navbar from "./components/Navbar.vue";
import Parcours from "./components/Parcours.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Projects,
    Contact,
    Navbar,
    Parcours,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* background: #00022e; */
}
html {
  scroll-behavior: smooth;
}
</style>
