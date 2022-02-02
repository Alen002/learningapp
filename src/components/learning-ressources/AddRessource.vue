<template>
  <base-card>
    <h2>Add Ressource</h2>
    <form>
      <div class="form-control">
        <label for="title">Title</label>
        <input type="text" id="title" name="title" />
      </div>

      <div class="form-control">
        <label for="description">Description</label
        ><textarea id="description" name="description" rows="3"></textarea>
      </div>

      <div class="form-control">
        <label for="link">Link</label>
        <input type="url" id="link" name="link" />
      </div>
      <div><base-button type="submit" buttonTitle="Add Ressource" /></div>
    </form>
  </base-card>
</template>

<script>
export default {};
</script>

<style scoped>
.form-control {
  background-color: lightgreen;
}
</style>
