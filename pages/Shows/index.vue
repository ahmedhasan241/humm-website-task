<template>
  <div class="container mt-5">
    <Head>
      <Title>برامج - همم | همم</Title>
    </Head>
    <h1 class="my-4">برامج</h1>
    <div
      class="row"
      data-aos="fade-up"
      data-aos-duration="800"
      data-aos-easing="ease-in-out-cubic"
    >
      <NuxtLink
        :to="`/shows/${show.slug}`"
        class="show-card text-decoration-none text-black d-flex justify-content-between my-3 mx-auto"
        v-for="show of data?.shows"
        style="height: 250px"
        :key="show.id"
      >
        <div class="card-image">
          <img
            :src="`https://board.humm.world/assets/${show.translations[0].cover.id}`"
            class="img-fluid img-thumbnail"
            alt="..."
          />
        </div>

        <div class="card-body">
          <h5 class="card-title mt-2 mb-2">{{ show.translations[0].title }}</h5>
          <p class="card-text">
            {{ show.translations[0].description }}
          </p>
          <div class="d-flex align-items-center my-1">
            <Icon name="ic:baseline-video-library" class="mx-1 my-auto fs-4" />
            <p class="my-auto mx-1" style="font-size: 15px">
              {{ show.all_episodes_func.count }}
            </p>
          </div>
        </div>
      </NuxtLink>
    </div>
    <div class="mt-5">
      <PostersWideTwo
        data-aos="fade-up"
        data-aos-duration="800"
        data-aos-easing="ease-in-out-cubic"
      />
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql("GetShows");
console.log(data?.value);
</script>

<style scoped>
.show-card {
  padding: calc(0.975rem + 0.91837vw);
  border: 1px solid #000;
  transition: box-shadow 0.25s ease-in-out;
  height: 100%;
  box-sizing: border-box;
  width: 49%;
}
@media (max-width: 767px) {
  .show-card {
    width: 100%;
  }
}
.show-card:hover {
  box-shadow: 4px 4px black;
}
.card-image {
  position: relative;
  overflow: hidden;
  width: 40%;
}

.card-image img {
  position: absolute;
  top: 0;
  right: 0;
  object-fit: cover;
  width: 100%;
  height: 100%;
  border: none;
  margin: auto auto;
}
@media (max-width: 993px) {
  .show-card {
    padding: calc(0.975rem + 0.91837vw) 10px;
  }
}
@media (max-width: 500px) {
  .card-image img {
    height: 60%;
    margin: 50px 0;
  }
}

.card-body {
  width: 60%;
  margin-inline: 5px;
}
</style>
