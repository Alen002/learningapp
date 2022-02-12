<template>
  <li>
    <base-card>
      <header>
        <h3>{{ id }}</h3>
        <h3>{{ title }}</h3>
        <base-button mode="flat" />
      </header>

      <p>{{ description }}</p>
      <nav><a :href="link">View</a></nav>
      <base-button buttonTitle="Delete" @clickedButton="getId" />
    </base-card>
  </li>
</template>

<script>
import BaseCard from '../UI/BaseCard.vue';
import BaseButton from '../UI/BaseButton.vue';
export default {
  components: { BaseCard, BaseButton },
  props: {
    title: { type: String, required: true },
    description: { type: String, required: true },
    link: { type: String, required: true },
    id: { type: String, required: true },
  },

  data() {
    return {
      buttonCapture: 'delete',
      result: 'TEST',
      counter: 0,
    };
  },
  methods: {
    getId() {
      console.log('Learning Ressources___', this.id);
      this.$emit('getId', this.id);
    },
  },
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>
