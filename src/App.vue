<template>
  <div id="app">

    <!-- heading -->
    <header>
      <h1>Books<span>.app</span></h1>
    </header>

    <!-- books list -->
    <books-list
      @remove="removeBook"
      :books="books" />

    <!-- no books message -->
    <p v-show="!books.length">No books...</p>

    <books-length-msg
      :books="books" />

    <!-- add book form -->
    <book-form
      @add="addBook" />

  </div>
</template>

<script>
import BooksList from './components/BooksList.vue'
import BooksLengthMsg from './components/BooksLengthMsg.vue'
import BookForm from './components/BookForm.vue'

export default {
  name: 'App',
  data: () => ({
    books: [
      {
        title: 'The Catcher in the Rye',
        price: 20
      },
      {
        title: 'Of Mice and Men',
        price: 18
      }
    ]
  }),
  methods: {
    removeBook (index) {
      this.books.splice(index, 1)
    },

    addBook (book) {
      this.books.push({ ...book })
    }
  },
  components: {
    BooksList,
    BooksLengthMsg,
    BookForm
  }
}
</script>
