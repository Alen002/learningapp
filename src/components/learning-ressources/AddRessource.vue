<template>
  <base-card>
    <h2>Add Ressource</h2>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input type="text" id="title" name="title" v-model="titleInput" />
      </div>

      <div class="form-control">
        <label for="description">Description</label
        ><textarea
          id="description"
          name="description"
          rows="3"
          v-model="desInput"
        ></textarea>
      </div>

      <div class="form-control">
        <label for="link">Link</label>
        <input type="url" id="link" name="link" v-model="urlInput" />
      </div>
      <div>
        <base-button type="submit" buttonTitle="Add Ressource" />
      </div>
    </form>
    {{ enteredData }}
  </base-card>
</template>

<script>
export default {
  data() {
    return {
      id: 'test',
      titleInput: '',
      desInput: '',
      urlInput: '',
      enteredData: [],
    };
  },
  methods: {
    submitData() {
      console.log('submitData');
      const title = this.titleInput;
      const description = this.desInput;
      const url = this.urlInput;
      console.log('submitData___', title, description);
      this.addResource(title, description, url);
    },
  },
  inject: ['addResource'],
  provide() {
    return {
      provideEnteredData: this.submitData,
    };
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
