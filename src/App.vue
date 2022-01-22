<template>
  <h3>App</h3>
  <ul>
    <base-list-item :storedRessources="storedRessources" />
  </ul>
</template>

<script>
import BaseListItem from './components/BaseListItem.vue';
export default {
  components: { BaseListItem },
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
