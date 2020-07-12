<template>
  <div>
    <nuxt-link to="/Jokes">
      <small>Back To Jokes</small>
    </nuxt-link>
    <h2>{{ joke }}</h2>
    <hr>
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      joke: {}
    }
  },
  async created () {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config)
      this.joke = res.data.joke
      console.log(this.joke)
    } catch (e) {
      console.log('ERROR : ' + e)
    }
  }
}
</script>
