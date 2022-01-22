<template>
  <div>
    <li v-for="ressource in storedRessources" :key="ressource.id">
      <h3>List Items</h3>
      <p>{{ ressource.title }}</p>
      <p>{{ ressource.description }}</p>
      <a :href="link">{{ link }}</a>
    </li>
  </div>
</template>

<script>
export default {
  props: {
    storedRessources: { type: Array, required: true },
    /* id: { type: String, required: true },
    title: { type: String, required: true },
    description: { type: String, required: true },
    link: { type: String, required: true }, */
  },
};
</script>

<style scoped></style>
