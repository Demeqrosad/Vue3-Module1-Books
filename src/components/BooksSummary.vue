<template>
  <div>
    <p>Books amount: {{ books.length }}</p>
    <p>Books price: {{ priceTotal }}</p>
  </div>
</template>

<script>
export default {
  name: 'BooksSummary',
  props: {
    books: {
      type: Array,
      required: true
    }
  },
  computed: {
    priceTotal: function () {
      return this.books.map(book => book.price).reduce((price, total = 0) => price + total)
    }
  }
}
</script>
