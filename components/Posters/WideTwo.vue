<template>
  <div>
    <NuxtLink to="/advertise">
      <img
        class="img-fluid"
        alt="Normal "
        lazy="loaded"
        style="width: 100%; height: 100vm"
        :src="`https://board.humm.world/assets/${data?.posters.translations[1].wide2_cover.id}`"
    /></NuxtLink>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql("GetPoster");
console.log(data?.value);
</script>

<style lang="scss" scoped></style>
