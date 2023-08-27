<template>
  <div class="container mt-5">
    <div class="my-4 d-flex justify-content-between">
      <h1 class="my-3 fw-bolder">وصفات</h1>
      <NuxtLink
        to="/food"
        class="appBtn d-flex align-items-center text-decoration-none"
        title=" 	عرض المزيد "
      >
        عرض المزيد
        <Icon class="fs-5 mt-1 mx-1" name="ic:baseline-arrow-back" />
      </NuxtLink>
    </div>
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4">
      <div
        class="col food-contain"
        data-aos="fade-up"
        data-aos-duration="700"
        data-aos-easing="ease-in-out-cubic"
        v-for="article of data?.Article"
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
              :to="`/food/category/${article.category.slug}`"
              class="category-link"
            >
              {{ article.category.translations[0].title }}
            </NuxtLink>
            <h6
              class="card-title fw-bold mt-1"
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
  </div>
</template>

<script setup>
const { data } = await useAsyncGql({
  operation: "GetArticle",
  variables: { type: "food", limit: 8 },
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
  margin: 0px 0 2px 0;
}
.category-link:hover {
  color: white;
  background-color: black;
  transition: all 0.3s ease-in-out;
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
