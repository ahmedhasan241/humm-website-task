<template>
  <div>
    <Head>
      <Title>من نحن - همم | همم</Title>
    </Head>
    <div class="card text-white mb-5">
      <div class="image-contain w-100">
        <div class="overlay-image"></div>
        <img
          src="@/assets/images/about-header.png"
          class="image-back"
          alt="..."
        />
      </div>
      <div
        class="card-img-overlay text-lg-center text-end d-flex align-items-center justify-content-center flex-column flex-lg-row"
      >
        <h1 class="card-title mx-5 mt-5">أهلًا بيكم في همم!</h1>
        <p
          class="card-text position-relative text-end bg-light text-dark mx-5 mt-4 mt-lg-5 p-4 p-lg-5"
        >
          <span class="position-absolute top-0 start-0 translate-middle">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="75.564"
              height="75.564"
              class="svg-contain"
              viewBox="0 0 148.564 148.564"
            >
              <path
                id="Path_35127"
                data-name="Path 35127"
                d="M926.374,464.009a74.282,74.282,0,1,0-74.282,74.282,74.282,74.282,0,0,0,74.282-74.282"
                transform="translate(-777.81 -389.727)"
                fill="#00c6c0"
              />
              <path
                id="Path_35128"
                data-name="Path 35128"
                d="M904.911,464.009a52.944,52.944,0,0,1-52.943-52.943,52.944,52.944,0,0,1-52.943,52.943,52.944,52.944,0,0,1,52.943,52.943,52.944,52.944,0,0,1,52.943-52.943"
                transform="translate(-777.81 -389.727)"
                fill="#ff3200"
              /></svg
          ></span>
          إحنا شركة عصرية متخصصة في الأكل باللغة العربية، في ظل اقتصاد
          التكنولوجيا والتجارة الالكترونية وصناعة المحتوى. بنوصل لملايين
          المتابعين والمشتركين من خلال الفيديوهات والمحتوى الإبداعي عن الأكل كل
          يوم. إحنا ملتزمين بتقديم مغامرة غذائية لمصر والشرق الأوسط من خلال
          برامجنا الترفيهية والمقالات والنصائح والتكّات وآلاف الوصفات والأفكار
          اللي هتجوّعك.
        </p>
      </div>
    </div>
    <AboutMotivate />

    <Brands class="mt-5" />
    <div class="mt-5 container">
      <PostersWideOne
        data-aos="fade-up"
        data-aos-duration="800"
        data-aos-easing="ease-in-out-cubic"
      />
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
@media (max-width: 992px) {
  .svg-contain {
    width: 35px;
    height: 65px;
  }
}
.card-title {
  width: 43%;
  font-size: 3rem;
}
.card-text {
  width: 43%;
  height: 50vmin;
  font-size: 1.4rem;
}
@media (max-width: 436px) {
  .card-title {
    font-size: 2rem;
  }
}
@media (max-width: 992px) {
  .card-title {
    width: 90%;
  }
  .card-text {
    width: 100%;
    font-size: medium;
    height: fit-content;
  }
}
.card-img-overlay {
  z-index: 2;
}
.card {
  height: 600px;
}
.image-back {
  width: 100%;
  height: 600px;
  object-fit: cover;
  z-index: -2;
}
.overlay-image {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
  background-image: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8));
}
.image-contain {
  position: relative;
}
</style>
