<template>
  <div>
    <h1>About me</h1>
    <p>This page is being rendered as <strong>{{ name }}</strong>.</p>

    <p class="message">{{ message }}</p>
    <button
      class="button--grey"
      @click="reverseMessage">Reverse Message</button>

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
  data() {
    return {
      message: "Hello world!",
    };
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  },
  head: {
    title: 'About page'
  }
}
</script>

<style>
.message {
  margin: 20px;
  padding: 10px;
  font-size: 1.5em;
  background-color: #eee;
  font: consolas;
}
</style>
