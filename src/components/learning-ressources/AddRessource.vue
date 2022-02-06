<template>
  <base-dialog
    v-if="inputIsInvalid"
    title="Invalid Input"
    @close="confirmError"
  >
    <template #default>
      <p>Unfortunately, at least one input value is invalid.</p>
      <p>
        Please check all inputs and make sure you enter at least a few
        characters into each input field.
      </p>
    </template>
    <template #actions>
      <base-button buttonTitle="Close" @clickedButton="confirmError" />
    </template>
  </base-dialog>

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
      inputIsInvalid: false,
    };
  },
  methods: {
    submitData() {
      const title = this.titleInput;
      const description = this.desInput;
      const link = this.urlInput;

      if (
        title.trim() === '' ||
        description.trim() === '' ||
        link.trim() === ''
      ) {
        this.inputIsInvalid = true;
        return;
      }
      this.addResource(title, description, link);
    },
    confirmError() {
      this.inputIsInvalid = false;
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
