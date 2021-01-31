<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
      <input v-model="bookData.finishedReading" id="finishedReading" type="checkbox">
      <label for="finishedReading">Finished Reading</label>
    </div>
    <div>
      <input v-model="bookData.ownership" id="borrowed" value="borrowed" type="radio">
      <label for="borrowed">Borrowed</label>
      <input v-model="bookData.ownership" id="bought" value="bought" type="radio">
      <label for="bought">Bought</label>
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: "",
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
