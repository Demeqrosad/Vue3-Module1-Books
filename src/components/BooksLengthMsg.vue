<template>
  <div>
    <p v-if="!books.length">Go get some books!</p>
    <p v-else-if="books.length === 1">One single book!</p>
    <p v-else-if="books.length < 6">Not too many of them…</p>
    <p v-else>{{ books.length }} books</p>
  </div>
</template>

<script>
export default {
  name: 'BooksLengthMsg',
  props: {
    books: {
      type: Array,
      required: true
    }
  }
}
</script>
