<template>
  <div>
    <ul v-for="resource in resources" :key="resource.id">
      <learning-ressources
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"
      />
    </ul>
  </div>
</template>

<script>
import LearningRessources from './LearningRessource.vue';
export default {
  components: { LearningRessources },
  inject: ['resources'],
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
