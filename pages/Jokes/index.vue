<template>
  <div>
    <SearchJoke v-on:Searching="SearchingJoke" />
    <Joke :jokes="jokes" />
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '../Jokes'
import SearchJoke from '../../components/SearchJoke'

export default {
  components: {
    Joke,
    SearchJoke
  },
  data () {
    return {
      jokes: []
    }
  },
  async created () {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
      console.log(this.jokes)
    } catch (e) {
      console.log('ERROR : ' + e)
    }
  },
  methods: {
    async SearchingJoke (text) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }
      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config)
        this.jokes = res.data.results
        console.log(this.jokes)
      } catch (e) {
        console.log('ERROR : ' + e)
      }
    }
  },
  head () {
    return {
      title: 'Dad Jokes',
      meta: [
        {
          hid: 'Description',
          name: 'Description',
          content: "Best place for dad's joke"
        }
      ]
    }
  }
}
</script>
