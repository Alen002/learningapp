<template>
  <base-card class="base-card">
    <base-button
      @clickedButton="setSelectedTab('stored-ressources')"
      buttonTitle="Stored Ressources"
      type="text"
    />
    <base-button
      @clickedButton="setSelectedTab('add-ressource')"
      buttonTitle="Add Ressource"
      type="text"
    />
    <!-- <button @click="setSelectedTab('add-ressource')">click me</button>
    <button @click="setSelectedTab('stored-ressources')">click me</button> -->
  </base-card>
  <!-- dynamic component -->
  <component :is="selectedTab"></component>
</template>

<script>
import StoredRessources from './StoredRessources.vue';
import AddRessource from './AddRessource.vue';
import BaseButton from '../UI/BaseButton.vue';
import BaseCard from '../UI/BaseCard.vue';
export default {
  components: { BaseButton, BaseCard, StoredRessources, AddRessource },
  data() {
    return {
      selectedTab: 'stored-ressources',
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
  provide() {
    return { ressources: this.storedRessources };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>

<style scoped>
.base-card {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
</style>
