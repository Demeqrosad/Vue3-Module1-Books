<template>
  <form @submit.prevent="handleSubmit">
    <label>
    Title:
      <input v-model="form.title" type="text" name="title">
    </label>
    <label>
      price:
      <input v-model="form.price" type="number" name="price">
    </label>
    <button>Add book</button>
  </form>
</template>

<script>
export default {
  name: 'BookForm',
  data: () => ({
    form: {
      title: '',
      price: 0
    }
  }),
  methods: {
    handleSubmit () {
      const formPayload = {}
      formPayload.title = this.form.title
      formPayload.price = parseInt(this.form.price, 10)
      this.$emit('add', formPayload)
      this.form.title = ''
      this.form.price = 0
    }
  }
}
</script>
