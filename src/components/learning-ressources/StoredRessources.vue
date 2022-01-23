<template>
  <div>
    <ul v-for="ressource in ressources" :key="ressource.id">
      <learning-ressources
        :title="ressource.title"
        :description="ressource.description"
        :link="ressource.link"
      />
    </ul>
  </div>
</template>

<script>
import LearningRessources from './LearningRessource.vue';
export default {
  components: { LearningRessources },
  props: { ressources: { type: Array, required: true } },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
