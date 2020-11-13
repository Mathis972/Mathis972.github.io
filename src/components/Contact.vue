<template>
  <section
    class="section "
    id="Contact"
  >
    <div class="container ">
      <button
        class="button is-primary"
        @click="show = !show"
        v-if="!show"
      >Vous souhaiteriez prendre contact ? 🍷</button>
      <transition
        name="slide-right"
        @after-enter="slideLeft = true"
        @after-leave="slideLeft = false"
      >
        <h1
          class="title"
          v-if="show"
        >Développeur web fullstack 💻</h1>
      </transition>

      <transition name="bounce">
        <h2
          v-if="isTextDisplayed"
          class="subtitle"
        >{{textToDisplay}}</h2>
      </transition>
      <transition
        name="slide-left"
        @after-enter="isTextDisplayed = true"
        @after-leave="isTextDisplayed = false"
      >
        <div
          class="social-links is-flex is-justify-content-center "
          v-if="slideLeft"
        >
          <a
            :href="social.link"
            target="_blank"
            class="button m-3"
            v-for="social in socials"
            :key="social.title"
            v-html="social.icon"
          ></a>

        </div>
      </transition>
    </div>

  </section>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const show = ref(false);
    const slideLeft = ref(false);
    const isTextDisplayed = ref(false);
    const textToDisplay = ref("Je suis en recherche d'une alternance ou d'un stage alterné dans le domaine du web pour poursuivre ma formation, N'hésitez pas à me contacter 👍")

    const socials = ref([
      {
        link: "https://github.com/Mathis972",
        icon: `<svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
        >
          <path fill="currentColor" d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-4.466 19.59c-.405.078-.534-.171-.534-.384v-2.195c0-.747-.262-1.233-.55-1.481 1.782-.198 3.654-.875 3.654-3.947 0-.874-.312-1.588-.823-2.147.082-.202.356-1.016-.079-2.117 0 0-.671-.215-2.198.82-.64-.18-1.324-.267-2.004-.271-.68.003-1.364.091-2.003.269-1.528-1.035-2.2-.82-2.2-.82-.434 1.102-.16 1.915-.077 2.118-.512.56-.824 1.273-.824 2.147 0 3.064 1.867 3.751 3.645 3.954-.229.2-.436.552-.508 1.07-.457.204-1.614.557-2.328-.666 0 0-.423-.768-1.227-.825 0 0-.78-.01-.055.487 0 0 .525.246.889 1.17 0 0 .463 1.428 2.688.944v1.489c0 .211-.129.459-.528.385-3.18-1.057-5.472-4.056-5.472-7.59 0-4.419 3.582-8 8-8s8 3.581 8 8c0 3.533-2.289 6.531-5.466 7.59z" />
        </svg>`,
        title: "Github"
      },
      {
        link: "https://www.linkedin.com/in/mathis-marie-claire-9ba037183/",
        icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
          <path fill="currentColor" d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>`,
        title: "LinkedIn"
      }, {
        link: 'mailto:mathis.marieclaire@ynov.com',
        icon: `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M0 3v18h24v-18h-24zm6.623 7.929l-4.623 5.712v-9.458l4.623 3.746zm-4.141-5.929h19.035l-9.517 7.713-9.518-7.713zm5.694 7.188l3.824 3.099 3.83-3.104 5.612 6.817h-18.779l5.513-6.812zm9.208-1.264l4.616-3.741v9.348l-4.616-5.607z"/></svg>`,
        title: "Mail"
      }
    ]);


    return {
      socials,
      show,
      textToDisplay,
      slideLeft,
      isTextDisplayed
    }
  }
  //TODO réseau sociaux petit composant en fin de page, pas de formulaire
  // https://github.com/Akryum/vue-observe-visibility pour ajouter des effets selon la visibilité ?
  // des animations de ce style http://findmatthew.com/
};
</script>

<style>
/* slide animations */
.slide-right-enter-active,
.slide-left-enter-active {
  transition: all 0.5s ease;
}
.slide-right-leave-active,
.slide-left-leave-active {
  transition: all 0.5s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-right-enter-from,
.slide-right-leave-to {
  transform: translateX(100px);
  opacity: 0;
}
.slide-left-enter-from,
.slide-left-leave-to {
  transform: translateX(-100px);
  opacity: 0;
}

/* bounce animation */
.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
.social-links .button:hover {
  color: white;
  background: #f2b5d4;
  border-color: transparent;
  transform: scale(110%);
}
.social-links .button {
  color: black;
  background: #f72585;
  transition: 0.3s;
  border-color: transparent;
}
</style>