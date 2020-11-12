<template>

  <Navbar />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <Projects></Projects>

  <Parcours />
  <Contact></Contact>
  <footer class="footer">
    <div class="content has-text-centered">
      <p>
        <strong>Bulma</strong> by <a href="https://jgthms.com">Jeremy Thomas</a>. The source code is licensed
        <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
        is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
      </p>
    </div>
  </footer>
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
