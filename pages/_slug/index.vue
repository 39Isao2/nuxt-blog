<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData ({ params }) {
    const { data } = await axios.get(
      `https://mdn-cafe-2.microcms.io/api/v1/infomation/${params.slug}`,
      {
        headers: { 'X-API-KEY': 'b13f9d29-699c-4bf6-a0f0-caa854290c6f' }
      }
    )
    return data
  }
}
</script>

<style scoped>

</style>
