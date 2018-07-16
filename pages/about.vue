<template>
  <div>
    <h1>About</h1>
    <p>This page is being rendered as <strong>{{ name }}</strong>.</p>

    <section>
      <p>Message:</p>
      <p class="message">{{ message }}</p>
      <button
        class="button--grey"
        @click="reverseMessage">Reverse Message</button>
    </section>

    <section>
      <p>Counter:</p>
      <p class="message">{{ counter }}</p>
      <button
        class="button--grey"
        @click="incrementCounter">Increment</button>
      <button
        class="button--grey"
        @click="resetCounter">Reset</button>
    </section>
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
      counter: 0,
    };
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    },
    resetCounter: function () {
      this.counter = 0
    },
    incrementCounter: function () {
      this.counter += 1
    },
  },
  head: {
    title: 'About page'
  }
}
</script>

<style>
h1 {
  margin-bottom: 10px;
}

section {
  margin-top: 40px;
  margin-bottom: 40px;
}

.message {
  margin-top: 20px;
  margin-bottom: 20px;
  padding: 10px;
  font-size: 1.5em;
  background-color: #eee;
}

.counter {
  font-weight: bold;
  font-size: 1.5em;
  padding: 10px;
}
</style>
