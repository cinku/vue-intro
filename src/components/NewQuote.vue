<template>
<div class="row">
    <div class="input-group mb-3">
        <input type="text" class="form-control" v-model.trim="newQuote" @keyup.enter="addQuote" />
        <button class="btn btn-success" v-on:click="addQuote">Add quote</button>
    </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      newQuote: ""
    };
  },
  methods: {
      addQuote() {
          this.$emit('addNewQuote', this.newQuote);
          this.newQuote = '';
      }
  }
};
</script>

<style>

</style>
