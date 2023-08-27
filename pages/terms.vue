<template>
  <div>
    <Head>
      <Title> {{ data?.pages_translations[4].title }} - همم | همم</Title>
    </Head>
    <div class="container p-5 text-center bg-black text-white mb-5">
      <h1 class="page-title p-5 text-center bg-black text-white">
        {{ data?.pages_translations[4].title }}
      </h1>
    </div>
    <div
      class="container mt-5"
      v-html="data?.pages_translations[4].content"
    ></div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql("GetHeader");
</script>

<style scoped>
.page-title {
  padding: 150px auto;
}
</style>
