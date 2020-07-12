<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/jokes">Jokes</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  name: 'Appheader'
}
</script>

<style>
  body {
    padding: 10px;
  }
  .header {
    display: flex;
    background-color: rgb(255, 255, 255);
  }
  .header > ul {
    padding: 10px;
    display: flex;
    margin-left: auto;
    list-style: none;
  }
  .header > ul > li {
    text-decoration: none;
  }
  a {
    text-decoration: none;
    color:rgb(0, 0, 0);
    padding: 10px;
  }
</style>
