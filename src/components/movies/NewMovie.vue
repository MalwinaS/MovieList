<template>
     <base-modal v-if="inputIsInvalid" title="Invalid input" @close="closeDialog">
      <template #default>
        <p>Unfortunately, at least one input value is inavlid.</p>
        <p>Please check all inputs and amke sure you enter at least a few characters into each input field.</p>
      </template>
      <template #actions>
        <base-button @click="closeDialog">OK</base-button>
      </template>
    </base-modal>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          type="text"
          rows="3"
          ref="descInput"
        />
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
      <div>
        <base-button mode="flat" type="submit"
          >Add movie</base-button
        >
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addMovie'],
  data() {
    return {
      inputIsInvalid: false,
    }
  },
  methods: {
    submitData() {
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDesc = this.$refs.descInput.value;
      const enteredLink = this.$refs.linkInput.value;
      if(enteredTitle.trim() === '' || enteredDesc.trim() === '' || enteredLink.trim() === '') {
        this.inputIsInvalid = true
      } else {
      this.addMovie(enteredTitle, enteredDesc, enteredLink)
      }
    },
    closeDialog() {
      this.inputIsInvalid = false;
    }
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
