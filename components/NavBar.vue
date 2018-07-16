<template>
  <div class="navbar">
    <span class="nav-title">Nuxt Example App</span>
    <nuxt-link
      to="/"
      class="button--grey">Home</nuxt-link>
    <nuxt-link
      to="/about"
      class="button--grey">About</nuxt-link>
    <nuxt-link
      to="/bitcoin"
      class="button--grey">Bitcoin</nuxt-link>
  </div>
</template>

<style>
.navbar {
  background-color: #eee;
  padding: 10px;
  margin-bottom: 20px;
}

.nav-title {
  color: #35495e;
  font-weight: bold;
}
</style>
