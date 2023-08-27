<template>
  <div class="container">
    <div
      class="my-4 d-flex justify-content-between"
      data-aos="fade-up"
      data-aos-duration="700"
      data-aos-easing="ease-in-out-cubic"
    >
      <h1 class="my-3 fw-bolder">علامات تجارية تعلن معنا</h1>
      <NuxtLink
        to="/advertise"
        class="appBtn d-flex align-items-center text-decoration-none"
        title="أعلن معنا"
      >
        أعلن معنا
        <Icon class="fs-5 mt-1 mx-1" name="ic:baseline-arrow-back" />
      </NuxtLink>
    </div>
    <div class="row row-col-1">
      <div
        v-for="brand of data?.homepage_translations[0].brands_list"
        :key="brand.id"
        style="height: 100px"
        class="col-6 col-md-3 col-lg-2 border border-1 border-dark text-center d-flex justify-content-center align-items-center"
        data-aos="fade-up"
        data-aos-duration="700"
        data-aos-easing="ease-in-out-cubic"
      >
        <img
          :src="`https://board.humm.world/assets/${brand.directus_files_id.id}`"
          class="placeholder-glow"
          style="width: 50%; height: 50%"
          alt="..."
        />
      </div>
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql({
  operation: "GetBrands",
  variables: { limit: 6 },
});
</script>

<style scoped>
.appBtn {
  background-color: transparent;
  border: 1px solid #000;
  color: #000;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  padding: 5px 15px;
  font-weight: 700;
  margin: 20px 0;
  box-shadow: 4px 4px black;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
    -webkit-box-shadow 0.15s ease-in-out;
  text-align: center;
}

.appBtn:hover {
  color: white;
  background-color: black;
  border-color: white;
  box-shadow: 4px 4px black;
}
</style>
