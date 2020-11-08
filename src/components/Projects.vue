<template>
  <section class="section" id="Projects">
    <h1 class="title">Mes travaux</h1>
    <ul>
      <li v-for="project in state.projects" :key="project.title">
        <a :href="project.githubLink" target="blank" v-if="!project.backLink">{{
          project.title
        }}</a>
        <span v-else
          >{{ project.title }}(<a :href="project.githubLink">Back</a>,
          <a :href="project.backLink"> Front</a>)
        </span>

        <span v-html="project.description"></span>
        <a v-if="project.siteLink" :href="project.siteLink" target="blank">
          Site hébergé ici
        </a>
      </li>
    </ul>
  </section>
</template>

<script>
import { reactive } from "vue";
export default {
  setup() {
    const state = reactive({
      projects: [
        {
          githubLink: "https://github.com/Mathis972/Ekip-bot",
          title: "BOT Ekip ",
          description: `: BOT discord permettant de jouer à action/vérité et de générer via une
        API des surnoms sous la forme d'émoji + mot + émoji (les émojis sont
        scrapés au préalable). <br /><sub>Ex: 🐝 Attitude 🐝</sub>`,
        },
        {
          githubLink: "https://github.com/Mathis972/spotify-app",
          title: "Une application spotify ",
          description: `permettant de générer ses statistiques et les lyrics de la chanson en
        cours d'écoute. Ce projet est un WIP.`,
          siteLink: "https://nuxt-spotify-stats.herokuapp.com/spotify",
        },
        {
          githubLink: "https://github.com/Mathis972/PROJET_DEV_B2_FRONT",
          title: "Un site web fullstack de livraison de restaurant ",
          description: `à la Deliveroo et Uber eats développée dans le cadre du projet de fin
        d'année de ma seconde année en école d'informatique.`,
          backLink: "https://github.com/Mathis972/PROJET_DEV_B2",
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
</style>