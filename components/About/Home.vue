<template>
  <div class="container">
    <div class="row row-cols-1 row-cols-lg-2 mt-5">
      <div class="col align-self-center">
        <h1
          class="fw-bolder mb-3"
          data-aos="fade-up"
          data-aos-duration="700"
          data-aos-easing="ease-in-out-cubic"
        >
          {{ data?.homepage.translations[0].home_about_title }}
        </h1>
        <p>
          {{ data?.homepage.translations[0].home_about_description }}
        </p>
        <NuxtLink
          to="/about"
          class="appBtn d-flex align-items-center text-decoration-none"
          title="عن همم"
        >
          عن همم
          <Icon class="fs-5 mt-1 mx-1" name="ic:baseline-arrow-back" />
        </NuxtLink>
      </div>
      <div class="col mt-4">
        <img
          data-aos="fade-up"
          data-aos-duration="700"
          data-aos-easing="ease-in-out-cubic"
          src="https://humm.world/wp-content/uploads/2023/05/9.png"
          class="img-fluid h-100"
          alt=""
        />
      </div>
    </div>
  </div>
</template>

<script setup>
const { data } = await useAsyncGql("GetHome");
</script>

<style scoped>
.appBtn {
  width: 30%;
  background-color: transparent;
  border: 1px solid #000;
  color: #000;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  padding: 5px 15px;
  font-weight: 700;
  margin: 10px 0;
  box-shadow: 4px 4px black;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
    -webkit-box-shadow 0.15s ease-in-out;
  text-align: center;
}
@media (max-width: 402px) {
  .appBtn {
    width: 40%;
  }
}

.appBtn:hover {
  color: white;
  background-color: black;
  border-color: white;
  box-shadow: 4px 4px black;
}
</style>
