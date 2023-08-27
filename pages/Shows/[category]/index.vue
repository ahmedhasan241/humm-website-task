<template>
  <div class="container my-4">
    <Head>
      <Title> {{ loadShow.shows[0].translations[0].title }} - همم | همم</Title>
    </Head>
    <div class="img-contain">
      <img
        :src="`https://board.humm.world/assets/${loadShow.shows[0].translations[0].cover.id}`"
        alt=""
        class="w-100 h-100"
      />
    </div>
    <div class="show-header text-center mt-5">
      <h1 class="fw-bolder my-3">
        {{ loadShow.shows[0].translations[0].title }}
      </h1>
      <p class="my-3">{{ loadShow.shows[0].translations[0].description }}</p>
      <div class="my-3">
        <p class="my-auto mx-1" style="font-size: 15px">
          <Icon
            name="material-symbols:alarm-on-outline"
            class="mx-1 my-auto fs-4"
          />
          {{ loadShow.shows[0].all_episodes_func.count }}
        </p>
      </div>
    </div>
    <div
      class="row"
      data-aos="fade-up"
      data-aos-duration="800"
      data-aos-easing="ease-in-out-cubic"
    >
      <NuxtLink
        :to="`/shows/${route.params.category}/${show.slug}`"
        class="show-card text-decoration-none text-black d-flex justify-content-between my-3 mx-auto"
        v-for="show of loadShow.shows[0].all_episodes"
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

        <div class="card-body mt-3">
          <NuxtLink class="category-link my-2" type="button">
            {{ loadShow.shows[0].translations[0].title }}
          </NuxtLink>
          <h5 class="card-title mt-2 mb-2">{{ show.translations[0].title }}</h5>

          <div class="user-created d-flex align-items-center my-2">
            <Icon
              name="material-symbols:alarm-on-outline"
              class="mx-1 my-auto fs-4"
            />
            <p class="my-auto" style="font-size: 15px">
              {{ formatDate(show.date_created) }}
            </p>
          </div>
        </div>
      </NuxtLink>
    </div>
    <div
      class="text-center"
      v-if="limitNumber <= loadShow.shows[0].all_episodes_func.count"
    >
      <button
        class="appBtn d-inline-flex"
        title=" 	عرض المزيد "
        @click="loadMore()"
      >
        عرض المزيد
      </button>
    </div>

    <div class="mt-5">
      <PostersWideOne
        data-aos="fade-up"
        data-aos-duration="800"
        data-aos-easing="ease-in-out-cubic"
      />
    </div>
  </div>
</template>

<script setup>
const route = useRoute();

const limitNumber = ref(4);
const loadShow = ref([]);

async function fetchData() {
  const { data } = await useAsyncGql({
    operation: "GetSingleShows",
    variables: { slug: route.params.category, limit: limitNumber.value },
  });
  loadShow.value = data?.value;
}
fetchData();

async function loadMore() {
  limitNumber.value = limitNumber.value + 4;
  await fetchData();
}

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
.category-link {
  --bs-btn-padding-y: 0.25rem;
  --bs-btn-padding-x: 0.5rem;
  --bs-btn-font-size: 0.75rem;
  border: 1px solid black;
  font-size: 15px;
  text-decoration: none;
  padding: 4px 8px;
  border-radius: 50px;
  color: black;
  width: fit-content;
}
.category-link:hover {
  color: white;
  background-color: black;
  transition: all 0.3s ease-in-out;
}
.img-contain {
  height: 50vmin;
}
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
