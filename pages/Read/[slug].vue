<template>
  <div class="container my-4">
    <Head>
      <Title> {{ data?.Article[0].translations[0].title }} - همم | همم</Title>
    </Head>
    <div class="img-contain">
      <img
        :src="`https://board.humm.world/assets/${data?.Article[0].translations[0].cover.id}`"
        alt=""
        class="w-100"
      />
    </div>
    <div class="slug-contain mt-5">
      <div class="row">
        <div class="col-12 col-sm-8">
          <h1 class="mt-3 mb-4">
            {{ data?.Article[0].translations[0].title }}
          </h1>
          <div
            class="mb-5 content-contain"
            v-html="data?.Article[0].translations[0].content"
          ></div>

          <div class="d-flex justify-content-between flex-sm-row flex-column">
            <div class="d-flex">
              <div class="user-created d-flex align-items-center">
                <Icon
                  name="material-symbols:person-2-outline"
                  class="my-auto fs-4"
                />
                <p class="my-auto mx-1" style="font-size: 15px">
                  {{ data?.Article[0].user_created.first_name }}
                  {{ data?.Article[0].user_created.last_name }}
                </p>
              </div>
              <div class="d-flex align-items-center my-1">
                <Icon
                  name="material-symbols:alarm-on-outline"
                  class="mx-1 my-auto fs-4"
                />
                <p class="my-auto mx-1" style="font-size: 15px">
                  {{ formatDate(data?.Article[0].date_created) }}
                </p>
              </div>
            </div>
            <div class="social-icon d-flex my-3 my-sm-5">
              <NuxtLink
                to="https://www.facebook.com/HummNetwork/"
                class="mx-2 text-decoration-none"
              >
                <Icon class="soc-icon fs-2" name="mingcute:facebook-line" />
              </NuxtLink>
              <NuxtLink
                to="https://www.instagram.com/hummnetwork/"
                class="mx-2 text-decoration-none"
              >
                <Icon class="soc-icon fs-2" name="ri:instagram-line" />
              </NuxtLink>
              <NuxtLink
                to="https://twitter.com/home"
                class="mx-2 text-decoration-none"
              >
                <Icon class="soc-icon fs-2" name="ph:twitter-logo" />
              </NuxtLink>
              <NuxtLink
                to="https://www.youtube.com/c/HummNetwork"
                class="mx-2 text-decoration-none"
              >
                <Icon
                  class="soc-icon fs-2"
                  name="ant-design:youtube-outlined"
                />
              </NuxtLink>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-4">
          <PostersNormalOne
            class="mb-3"
            data-aos="fade-up"
            data-aos-duration="800"
            data-aos-easing="ease-in-out-cubic"
          />
          <PostersNormalTwo
            data-aos="fade-up"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out-cubic"
          />
        </div>
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
  operation: "GetSingleArticle",
  variables: { slug: route.params.slug, type: "read" },
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

<style>
.img-contain {
  overflow: hidden;
}
.img-contain img {
  transition: all 0.5s ease-in-out;
}
.img-contain:hover img {
  transform: scale(1.1);
}
.soc-icon {
  color: black;
  cursor: pointer;
}
.soc-icon:hover {
  color: red;
}
.content-contain {
  width: 100%;
}
.content-contain img {
  width: 100%;
}
</style>
