<template>
  <div class="container mt-5">
    <div
      class="my-4 d-flex justify-content-between"
      data-aos="fade-up"
      data-aos-duration="700"
      data-aos-easing="ease-in-out-cubic"
    >
      <h1 class="my-3 fw-bolder">مقالات</h1>
      <NuxtLink
        to="/read"
        class="appBtn d-flex align-items-center text-decoration-none"
        title=" 	عرض المزيد "
      >
        عرض المزيد
        <Icon class="fs-5 mt-1 mx-1" name="ic:baseline-arrow-back" />
      </NuxtLink>
    </div>
    <div
      class="row row-cols-1 row-cols-md-2 g-4"
      data-aos="fade-up"
      data-aos-duration="700"
      data-aos-easing="ease-in-out-cubic"
    >
      <NuxtLink
        class="col text-decoration-none text-black"
        :to="`/read/${read.slug}`"
        v-for="read of data?.Article"
        :key="read.id"
      >
        <div class="card read-card p-3 border border-dark rounded-0">
          <div>
            <img
              :src="`https://board.humm.world/assets/${read.translations[0].cover.id}`"
              class="card-img-top"
              alt="..."
            />
          </div>

          <div class="card-body">
            <h5 class="card-title">{{ read.translations[0].title }}</h5>
            <div class="d-flex mx-2">
              <div class="user-created d-flex align-items-center">
                <Icon
                  name="material-symbols:person-2-outline"
                  class="my-auto fs-4"
                />
                <p class="my-auto mx-1" style="font-size: 15px">
                  {{ read.user_created.first_name }}
                  {{ read.user_created.last_name }}
                </p>
              </div>
              <div class="d-flex align-items-center my-1">
                <Icon
                  name="material-symbols:alarm-on-outline"
                  class="mx-1 my-auto fs-4"
                />
                <p class="my-auto mx-1" style="font-size: 15px">
                  {{ formatDate(read.date_created) }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql({
  operation: "GetArticle",
  variables: { type: "read", limit: 2 },
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
.read-card {
  transition: box-shadow 0.25s ease-in-out;
  height: 100%;
}
.read-card:hover {
  box-shadow: 4px 4px black;
}
.col {
  height: 100vm;
}

.card-img-top {
  max-width: 100%;
  max-height: 300px;
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
