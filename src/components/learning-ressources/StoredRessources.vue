<template>
  <div>
    <ul v-for="resource in resources" :key="resource.id">
      <learning-ressources
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"
        :id="resource.id"
        @getId="getId"
      />
    </ul>
  </div>
</template>

<script>
import LearningRessources from './LearningRessource.vue';
export default {
  data() {
    return { id: '' };
  },
  components: { LearningRessources },
  inject: ['resources'],
  methods: {
    getId(id) {
      console.log('stored Ressources___', id);
      this.$emit('getId', id);
    },
  },
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
