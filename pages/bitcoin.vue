<template>
  <div>
    <h1>Bitcoin</h1>

    <li
      v-for="currency in currencies"
      :key="currency.code">
      1 BTC = {{ currency.code }} {{ currency.rate }}
    </li>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Bitcoin Price'
  },
  async asyncData({ app }) {
    const data = await app.$axios.$get("https://api.coindesk.com/v1/bpi/currentprice.json")
    const currencies = Object.entries(data.bpi)
      .map(data => data[1])
    return { currencies }
  }
}
</script>
