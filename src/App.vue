<template>
  <the-ressources />
  <the-header title="Remember Stuff" />
  <stored-ressources :ressources="storedRessources" />
  <add-ressources />
</template>

<script>
import StoredRessources from './components/learning-ressources/StoredRessources.vue';
import TheHeader from './components/layouts/TheHeader.vue';
import TheRessources from './components/learning-ressources/TheRessources.vue';
import AddRessources from './components/learning-ressources/AddRessource.vue';

export default {
  components: { StoredRessources, TheHeader, TheRessources, AddRessources },
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
