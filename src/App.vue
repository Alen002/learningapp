<template>
  <h3>App</h3>
  <stored-ressources :ressources="storedRessources" />
</template>

<script>
import StoredRessources from './components/learning-ressources/StoredRessources.vue';
export default {
  components: { StoredRessources },
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

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}

ul {
  list-style: none;
  padding: 0;
  margin: auto;
}
</style>
