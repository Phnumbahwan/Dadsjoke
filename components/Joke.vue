<template>
  <div class="joke">
    <p v-for="joke in jokes" :key="joke.id">
      <nuxt-link :to="'jokes/' + joke.id">
        {{ joke.joke }}
      </nuxt-link>
    </p>
  </div>
</template>

<script>
export default {
  name: 'Joke',
  props: ['jokes']
}
</script>

<style scoped>
  .joke > p {
    margin-bottom: 10px;
    padding: 10px;
    background-color: rgb(236, 236, 236);
  }
</style>
