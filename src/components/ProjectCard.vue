<template>
  <div class="box">
    <article class="media">
      <!-- <div class="media-left">
        <figure class="image is-64x64">
          <img
            src="https://bulma.io/images/placeholders/128x128.png"
            alt="Image"
          >
        </figure>
      </div> -->
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

          </p>
        </div>

      </div>

    </article>
    <div
      v-if="project.backLink"
      class="is-flex is-justify-content-space-evenly"
    >
      <button class="button is-primary"><a
          :href="project.backLink"
          target="blank"
          style="color: white"
        >Back</a></button>
      <button class="button is-info"><a
          :href="project.githubLink"
          target="blank"
          style="color: white"
        >Front</a></button>
    </div>
    <button
      v-if="project.siteLink"
      class="button is-primary"
    >
      <a
        :href="project.siteLink"
        target="blank"
        style="color: white"
      >Site hébergé ici</a>
    </button>
  </div>

</template>

<script>
export default {
  //TODO add techonlogies used section
  props: {
    project: Object
  },


}
</script>

<style >
</style>