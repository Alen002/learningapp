<template>
  <div class="ressource">
    <li>
      <div>
        <header>
          <h3>{{ title }}</h3>
          <button>Delete</button>
        </header>
      </div>
      <p>{{ description }}</p>
      <nav><a :href="link">View</a></nav>
    </li>
  </div>
</template>

<script>
export default {
  props: ['title', 'description', 'link'],
};
</script>

<style scoped>
.ressource {
  background-color: lightblue;
}
</style>
