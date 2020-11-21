<template>
  <section
    class="section is-medium has-background-primary"
    style="padding-bottom: 14rem"
    id="Projects"
  >
    <h1 class="title">Mes travaux</h1>
    <h2 class="subtitle">Me lancer dans de nouvelles technologies arrive souvent notamment grâce à mon cursus scholaire.<br>
      Voici quelques un des projets dans lesquels je me suis lancé.
    </h2>
  </section>
  <section class="section projects">

    <div class="container">
      <div class="columns is-multiline is-centered ">
        <div
          class="column is-half-tablet is-one-third-desktop"
          v-for="project in state.projects"
          :key="project.title"
        >
          <ProjectCard :project="project" />

        </div>
      </div>

    </div>
  </section>
</template>

<script>
import { reactive } from "vue";
import ProjectCard from "./ProjectCard"
export default {
  components: {
    ProjectCard
  },
  setup() {
    const state = reactive({
      projects: [
        {
          githubLink: "https://github.com/Mathis972/Ekip-bot",
          title: "BOT Ekip 🤖",
          description: `Un BOT discord permettant de jouer à action/vérité et de générer via une
        API des surnoms sous la forme d'émoji + mot + émoji (les émojis sont
        scrapés au préalable). <br /><sub>Ex: 🐝 Attitude 🐝</sub>`,
          technologies: [
            'node.js',
            'Javascript'
          ]
        },
        {
          githubLink: "https://github.com/Mathis972/spotify-app",
          title: "Spotify App 🎵",
          description: `Une application spotify permettant de générer ses statistiques et les lyrics de la chanson en
        cours d'écoute. Ce projet est un WIP.`,
          siteLink: "https://nuxt-spotify-stats.herokuapp.com/spotify",
          technologies: [
            'Vue.js',
            'Vuex',
            'Javascript',
            'Buetify'
          ]
        },
        {
          githubLink: "https://github.com/Mathis972/PROJET_DEV_B2_FRONT",
          title: "RestoStar 👨‍🍳",
          description: `Un site web fullstack de livraison de restaurant à la Deliveroo et Uber eats développée dans le cadre du projet de fin
        d'année de ma seconde année en école d'informatique.`,
          backLink: "https://github.com/Mathis972/PROJET_DEV_B2",
          technologies: [
            'Vue.js',
            'Vuex',
            'Javascript',
            'PHP',
            'Symfony',
            'Vuetify',
            'HTML/CSS'
          ]
        },
      ],
    });
    return {
      state,
    };
  },
};
</script>

<style>
.subtitle {
  line-height: 1.5;
}
.projects {
  margin-top: -8rem;
}
</style>