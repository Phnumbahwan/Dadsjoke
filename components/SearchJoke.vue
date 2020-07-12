<template>
  <div>
    <form @submit.prevent="onSubmit">
      <input v-model="title" type="text" >
      <input type="submit" value="Search Joke"/>
    </form>
  </div>
</template>

<script>
export default {
  name: 'SearchJoke',
  data () {
    return {
      title: ''
    }
  },
  methods: {
    onSubmit () {
      this.$emit('Searching', this.title)
    }
  }
}
</script>
