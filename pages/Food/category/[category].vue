<template>
  <div class="container">
    <Head>
      <Title> {{ data?.category[0].translations[0].title }} - همم | همم</Title>
    </Head>
    <div class="img-contain mt-3">
      <img
        :src="`https://board.humm.world/assets/${data?.category[0].translations[0].cover.id}`"
        alt=""
        class="w-100"
      />
    </div>
    <div class="category-title text-center my-5">
      <h1>{{ data?.category[0].translations[0].title }}</h1>
    </div>

    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4 mt-5">
      <div
        class="col food-contain"
        data-aos="fade-up"
        data-aos-duration="700"
        data-aos-easing="ease-in-out-cubic"
        v-for="article of data?.category[0].translations[0].category_id
          .articles"
        :key="article.id"
      >
        <NuxtLink
          :to="`/food/${article.slug}`"
          class="card food-card rounded-0 border-1 border-dark text-decoration-none text-dark"
        >
          <div class="px-3" style="height: 50%">
            <img
              :src="`https://board.humm.world/assets/${article.translations[0].cover.id}`"
              class="placeholder-glow mt-3"
              style="width: 100%; height: 90%"
              alt="..."
            />
          </div>
          <div class="card-body" style="height: 50vm">
            <NuxtLink
              :to="`/food/category/${route.params.slug}`"
              class="category-link"
            >
              {{ data?.category[0].translations[0].title }}
            </NuxtLink>
            <h6
              class="card-title fw-bold mt-2"
              style="font-size: calc(0.9rem + 0.22959vw)"
            >
              {{ article.translations[0].title }}
            </h6>

            <div class="user-created d-flex align-items-center">
              <Icon
                name="material-symbols:person-2-outline"
                class="mx-1 my-aut fs-4"
              />
              <p class="my-auto" style="font-size: 15px">
                {{ article.user_created.first_name }}
                {{ article.user_created.last_name }}
              </p>
            </div>
            <div class="user-created d-flex align-items-center my-1">
              <Icon
                name="material-symbols:alarm-on-outline"
                class="mx-1 my-auto fs-4"
              />
              <p class="my-auto" style="font-size: 15px">
                {{ formatDate(article.date_created) }}
              </p>
            </div>
          </div>
        </NuxtLink>
      </div>
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
const { data } = await useAsyncGql({
  operation: "GetCategory",
  variables: { slug: route.params.category },
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
.img-contain {
  overflow: hidden;
}
.img-contain img {
  transition: all 0.5s ease-in-out;
}
.img-contain:hover img {
  transform: scale(1.1);
}
.food-card {
  transition: box-shadow 0.25s ease-in-out;
  height: 100%;
}
.food-card:hover {
  box-shadow: 4px 4px black;
}
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
}
.category-link:hover {
  color: white;
  background-color: black;
  transition: all 0.3s ease-in-out;
}
</style>
