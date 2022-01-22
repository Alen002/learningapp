<template>
  <h3>App</h3>
  <ul v-for="ressource in storedRessources" :key="ressource.id">
    <learning-ressource
      :title="ressource.title"
      :description="ressource.description"
      :link="ressource.link"
    />
  </ul>
</template>

<script>
import LearningRessource from './components/learning-ressources/LearningRessource.vue';
export default {
  components: { LearningRessource },
  data() {
    return {
      storedRessources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'Official documentation of vue.js',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Search Engine',
          description: 'Google Search Engine',
          link: 'https://google.com',
        },
      ],
    };
  },
};
</script>

<style scoped></style>
