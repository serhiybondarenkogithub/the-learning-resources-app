<template>
  <base-card>
    <form @submit.prevent="submitData">
      <div>
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput">
      </div>
      <div>
        <label for="description">Description</label>
        <input id="description" name="description" type="text" ref="descInput">
      </div>
      <div>
        <label for="link">Link</label>
        <input id="link" name="link" type="text" ref="linkInput">
      </div>
      <div>
        <base-button type="submit">Submit</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ["addResource"],
  methods: {
    submitData() {
      console.log(this.$refs.titleInput.value)
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDescription = this.$refs.descInput.value;
      const enteredUrl = this.$refs.linkInput.value;

      this.addResource(enteredTitle, enteredDescription, enteredUrl);
    }
  }
}
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