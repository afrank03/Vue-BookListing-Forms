<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div class="c-book-form__book--finished">
      <label for="finishedReading">Finished Reading</label>
      <input type="checkbox" id="finishedReading" v-model="bookData.finishedReading" />

      <label for="borrowed">Borrowed</label>
      <input type="radio" id="borrowed" v-model="bookData.ownership" value="borrowed" />

      <label for="bought">bought</label>
      <input type="radio" id="bought" v-model="bookData.ownership" value="bought" />
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
        finishedReading: false,
        ownership: [],
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
