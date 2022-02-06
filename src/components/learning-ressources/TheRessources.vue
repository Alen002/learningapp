<template>
  <base-card class="base-card">
    <base-button
      @clickedButton="setSelectedTab('stored-ressources')"
      buttonTitle="Stored Ressources"
      type="text"
      :mode="storedResButtonMode"
    />
    <base-button
      @clickedButton="setSelectedTab('add-ressource')"
      buttonTitle="Add Ressource"
      type="text"
      :mode="addResButtonMode"
    />
    <h1>{{ testing }}</h1>
  </base-card>
  <!-- dynamic component -->
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
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
      storedResources: [
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
  inject: ['provideEnteredData'],
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'stored-ressources' ? null : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'add-ressource' ? null : 'flat';
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date(),
        description: description,
        link: url,
        title: title,
      };

      this.storedResources.push(newResource);
      this.selectedTab = 'stored-ressources';
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
