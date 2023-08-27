<template>
  <div class="bg-black">
    <div class="container mt-5 text-white py-5">
      <div
        class="my-4 d-flex justify-content-between"
        data-aos="fade-up"
        data-aos-duration="700"
        data-aos-easing="ease-in-out-cubic"
      >
        <h1 class="my-3 fw-bolder">برامج</h1>
        <NuxtLink
          to="/shows"
          class="appBtn d-flex align-items-center text-decoration-none"
          title=" 	عرض المزيد "
        >
          عرض المزيد
          <Icon class="fs-5 mt-1 mx-1" name="ic:baseline-arrow-back" />
        </NuxtLink>
      </div>
      <div class="row">
        <NuxtLink
          data-aos="fade-up"
          data-aos-duration="700"
          data-aos-easing="ease-in-out-cubic"
          :to="`/shows/${show.slug}`"
          class="show-card text-white text-decoration-none text-black d-flex my-3 mx-auto"
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
            <h5 class="card-title mt-2 mb-2">
              {{ show.translations[0].title }}
            </h5>
            <p class="card-text">
              {{ show.translations[0].description }}
            </p>
            <div class="d-flex align-items-center my-1">
              <Icon
                name="ic:baseline-video-library"
                class="mx-1 my-auto fs-4"
              />
              <p class="my-auto mx-1" style="font-size: 15px">
                {{ show.all_episodes_func.count }}
              </p>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql({
  operation: "GetShows",
  variables: { limit: 4 },
});
function formatDate(value) {
  const d = new Date(value);
  const formattedDate = d.toLocaleDateString("ar-EG", {
    day: "2-digit",
    month: "2-digit",
    year: "numeric",
  });
  return formattedDate;
}
</script>

<style scoped>
.show-card {
  padding: calc(0.975rem + 0.91837vw);
  border: 1px solid #ffffff;
  transition: box-shadow 1s ease-in-out;
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
  box-shadow: 4px 4px rgb(255, 255, 255);
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

.appBtn {
  background-color: transparent;
  border: 1px solid #ffffff;
  color: #ffffff;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  padding: 5px 15px;
  font-weight: 700;
  margin: 20px 0;
  box-shadow: 4px 4px rgb(255, 255, 255);
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
    -webkit-box-shadow 0.15s ease-in-out;
  text-align: center;
}

.appBtn:hover {
  color: black;
  background-color: rgb(255, 255, 255);
  border-color: rgb(0, 0, 0);
  box-shadow: 4px 4px rgb(255, 255, 255);
}
</style>
