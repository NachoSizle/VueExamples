<template>
  <div class="project-card--container">
    <h1>{{ myTitle }}</h1>
    <slot name="subtitle"></slot>
    <p>{{ myDescription }}</p>
    <button v-if="buttonConfig.showButton">{{ buttonConfig.myButtonText }}</button>
    <slot name="footer-text"></slot>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    myTitle: {
      type: String,
      required: true,
      default: 'Hello World',
    },
    myDescription: String,
    buttonConfig: Object
  }
}
</script>

<style scoped>
  .project-card--container {
    max-width: 200px;
    max-height: 300px;
    width: 100%;
    height: 100%;
  }

  .subtitle {
    background-color: aquamarine;
  }
</style>