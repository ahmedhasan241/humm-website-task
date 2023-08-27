<template>
  <div class="container mt-5">
    <div
      class="my-4 d-flex justify-content-between"
      data-aos="fade-up"
      data-aos-duration="700"
      data-aos-easing="ease-in-out-cubic"
    >
      <h1 class="my-3 fw-bolder">الصحافة</h1>
      <NuxtLink
        to="/press"
        class="appBtn d-flex align-items-center text-decoration-none"
        title=" 	عرض المزيد "
      >
        عرض المزيد
        <Icon class="fs-5 mt-1 mx-1" name="ic:baseline-arrow-back" />
      </NuxtLink>
    </div>
    <div class="row row-cols-1 row-cols-md-3 g-4">
      <div
        class="col"
        data-aos="fade-up"
        data-aos-duration="800"
        data-aos-easing="ease-in-out-cubic"
        v-for="press of data?.Article"
        :key="press.id"
      >
        <NuxtLink :to="`${press.press_link}`" class="card press-card">
          <img
            :src="`https://board.humm.world/assets/${press.translations[0].cover.id}`"
            class=""
            alt="..."
          />
          <div class="card-img-overlay d-flex align-items-end">
            <span class="card-text text-bg-light p-3 fs-6 fw-bold bg-light">
              {{ press.translations[0].title }}

              <div class="d-flex align-items-center my-2 text-secondary">
                <Icon
                  name="material-symbols:alarm-on-outline"
                  class="mx-1 my-auto fs-4"
                />
                <p class="my-auto mx-1" style="font-size: 15px">
                  {{ formatDate(press.date_created) }}
                </p>
              </div>
            </span>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql({
  operation: "GetArticle",
  variables: { type: "press", limit: 3 },
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
.press-card {
  transition: box-shadow 0.25s ease-in-out;
  box-shadow: 4px 4px white;
  height: 100%;
}
.press-card:hover {
  box-shadow: 4px 4px black;
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
