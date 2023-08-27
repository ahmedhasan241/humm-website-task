<template>
  <div class="mt-3">
    <Head>
      <Title
        >همم | {{ data?.homepage_translations[1].home_about_title }}
      </Title>
    </Head>
    <div
      class="header mb-5"
      data-aos="fade-up"
      data-aos-duration="700"
      data-aos-easing="ease-in-out-cubic"
      :style="`
        background-image: url('https://board.humm.world/assets/${data?.homepage_translations[1].home_intro_cover.id}');
      `"
    >
      <div
        class="intro-body"
        data-aos="fade-up"
        data-aos-duration="1400"
        data-aos-easing="ease-in-out-cubic"
      >
        <h1 class="w-100 fw-bolder fs-1">
          {{ data?.homepage_translations[1].home_about_title }}
        </h1>
        <p class="text-black"></p>
        <NuxtLink
          class="appBtn d-inline-flex text-decoration-none"
          to="/about"
          title=" اعرف المزيد"
        >
          اعرف المزيد
        </NuxtLink>
      </div>
    </div>
    <HomeFood />
    <br />
    <div class="container mt-5">
      <PostersWideOne
        data-aos="fade-up"
        data-aos-duration="800"
        data-aos-easing="ease-in-out-cubic"
      />
    </div>
    <br />
    <HomeRead />
    <br />
    <HomeShow
      data-aos="fade-up"
      data-aos-duration="800"
      data-aos-easing="ease-in-out-cubic"
    />
    <br />
    <div
      class="container justify-content-between d-flex flex-sm-row flex-column mt-5"
    >
      <PostersNormalOne
        class="advetis-noraml my-2"
        data-aos="fade-up"
        data-aos-duration="700"
        data-aos-easing="ease-in-out-cubic"
      />
      <PostersNormalTwo
        class="advetis-noraml my-2"
        data-aos="fade-up"
        data-aos-duration="700"
        data-aos-easing="ease-in-out-cubic"
      />
    </div>
    <br />
    <AboutHome />
    <br />
    <HomeSubscribe />
    <br />
    <HomePress />
    <br />
    <Brands />
    <br />
    <div class="container mt-5">
      <PostersWideTwo
        data-aos="fade-up"
        data-aos-duration="800"
        data-aos-easing="ease-in-out-cubic"
      />
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql("GetHeader");
console.log(data.value);
</script>

<style scoped>
.header {
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
  height: 100vm;
  width: auto;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.intro-body {
  background: #fff;
  padding: calc(1.7625rem + 1.34031vw);
  display: inline-block;
}
@media (max-width: 500px) {
  .intro-body {
    padding: calc(0.7625rem + 0.34031vw);
  }
  .appBtn {
    margin: 3px 0;
  }
}

.intro-body {
  margin: calc(2.2875rem + 12.97194vw) 7.5% calc(1.2875rem + 3.78827vw);
}
.appBtn {
  background-color: transparent;
  border: 1px solid #000;
  color: #000;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  font-size: 1em;
  font-weight: 600;
  height: fit-content;
  margin: 10px 0;
  padding: 0.4em 1.5em;
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
.advetis-noraml {
  width: 48.5%;
}
@media (max-width: 575px) {
  .advetis-noraml {
    width: 95%;
    margin-inline: auto;
  }
}
</style>
