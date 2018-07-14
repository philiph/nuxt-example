<template>
  <div>
    <h1>About me</h1>
    <p>This page is being rendered as <strong>{{ name }}</strong>.</p>
    <nuxt-link
      to="/"
      class="button--grey">Home</nuxt-link>
  </div>
</template>

<script>
export default {
  asyncData() {
    return {
      name: process.static ? 'static' : (process.server ? 'server' : 'client')
    }
  },
  head: {
    title: 'About page'
  }
}
</script>
