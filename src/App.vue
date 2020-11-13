<template>

  <Navbar />
  <Projects></Projects>

  <Parcours />
  <Contact></Contact>
  <Footer />
</template>

<script>
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";
import Navbar from "./components/Navbar.vue";
import Parcours from "./components/Parcours.vue";
import Footer from "./components/Footer.vue"

export default {
  name: "App",
  components: {
    Projects,
    Contact,
    Navbar,
    Parcours,
    Footer
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
