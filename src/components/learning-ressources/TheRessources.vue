<template>
  <base-card class="base-card">
    <base-button
      @click="setSelectedTab('stored-ressources')"
      buttonTitle="Stored Ressources"
    />
    <base-button
      @click="setSelectedTab('add-ressource')"
      buttonTitle="Add Ressource"
    />
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
    };
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
