<template>
  <div class="main">
    <Appheader />
    <Nuxt />
  </div>
</template>

<script>
import Appheader from '../components/Appheader'

export default {
  components: {
    Appheader
  }
}
</script>

<style>
  body {
    font-family: sans-serif;
  }
</style>
