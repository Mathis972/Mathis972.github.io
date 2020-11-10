<template>
  <section
    class="section is-medium has-background-primary"
    style="padding-bottom: 14rem"
  >
    <h1 class="title">Mes travaux</h1>
    <h2 class="subtitle">Me lancer dans de nouvelles technologies arrive souvent notamment grâce à mon cursus scholaire.<br>
      A poursuivre les nouveautés, parfois certains projets prennent plus de temps et de passions, les voici
    </h2>
  </section>
  <section
    class="section "
    id="Projects"
  >
    <div class="container">
      <div class="columns is-multiline is-centered ">
        <div
          class="column is-half-tablet is-one-third-desktop"
          v-for="project in state.projects"
          :key="project.title"
        >
          <div class="box">
            <article class="media">
              <div class="media-left">
                <figure class="image is-64x64">
                  <img
                    src="https://bulma.io/images/placeholders/128x128.png"
                    alt="Image"
                  >
                </figure>
              </div>
              <div class="media-content">
                <div class="content">
                  <p>
                    <a
                      :href="!project.backLink ? project.githubLink : project.backLink"
                      target="blank"
                    >
                      <strong>{{ project.title }}</strong>
                    </a>
                    <br>
                    <span v-html="project.description"></span><br>
                    <a
                      v-if="project.siteLink"
                      :href="project.siteLink"
                      target="blank"
                    >
                      Site hébergé ici
                    </a>
                  </p>
                </div>

              </div>

            </article>
            <div
              v-if="project.backLink"
              class="is-flex is-justify-content-space-evenly"
            >
              <button class="button is-primary">Back</button>
              <button class="button is-link">Front</button>
            </div>
          </div>
        </div>
      </div>
      <ul>
        <li
          v-for="project in state.projects"
          :key="project.title"
        >
          <a
            :href="project.githubLink"
            target="blank"
            v-if="!project.backLink"
          >{{
          project.title
        }}</a>
          <span v-else>{{ project.title }}(<a :href="project.githubLink">Back</a>,
            <a :href="project.backLink"> Front</a>)
          </span>

          <span v-html="project.description"></span>
          <a
            v-if="project.siteLink"
            :href="project.siteLink"
            target="blank"
          >
            Site hébergé ici
          </a>
        </li>
      </ul>
    </div>
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
          title: "BOT Ekip 🤖",
          description: `Un BOT discord permettant de jouer à action/vérité et de générer via une
        API des surnoms sous la forme d'émoji + mot + émoji (les émojis sont
        scrapés au préalable). <br /><sub>Ex: 🐝 Attitude 🐝</sub>`,
        },
        {
          githubLink: "https://github.com/Mathis972/spotify-app",
          title: "Spotify App 🎵",
          description: `Une application spotify permettant de générer ses statistiques et les lyrics de la chanson en
        cours d'écoute. Ce projet est un WIP.`,
          siteLink: "https://nuxt-spotify-stats.herokuapp.com/spotify",
        },
        {
          githubLink: "https://github.com/Mathis972/PROJET_DEV_B2_FRONT",
          title: "RestoStar 👨‍🍳",
          description: `Un site web fullstack de livraison de restaurant à la Deliveroo et Uber eats développée dans le cadre du projet de fin
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
.subtitle {
  line-height: 1.5;
}
#Projects {
  margin-top: -14rem;
}
</style>