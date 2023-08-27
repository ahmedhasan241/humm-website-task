<template>
  <div class="container border-top border-1 border-dark mt-5 text-center">
    <div
      class="first-footer d-flex flex-column flex-md-row justify-content-between align-items-center align-items-md-start"
    >
      <div class="social-icon d-flex my-5">
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
          to="https://www.youtube.com/c/HummNetwork"
          class="mx-2 text-decoration-none"
        >
          <Icon class="soc-icon fs-2" name="ant-design:youtube-outlined" />
        </NuxtLink>
        <NuxtLink
          to="https://www.tiktok.com/@hummnetwork"
          class="mx-2 text-decoration-none"
        >
          <Icon class="soc-icon fs-2" name="ph:tiktok-logo-bold" />
        </NuxtLink>
      </div>
      <div class="d-flex mt-2 my-md-auto">
        <NuxtLink
          to="/about"
          class="offcanvas-link d-block fs-6 mx-2 fw-bold text-decoration-none"
          >من نحن</NuxtLink
        >
        <NuxtLink
          to="/press"
          class="offcanvas-link d-block fs-6 mx-2 fw-bold text-decoration-none"
          >الصحافه</NuxtLink
        >
        <NuxtLink
          to="/advertise"
          class="offcanvas-link d-block fs-6 mx-2 fw-bold text-decoration-none"
          >أعلن معنا</NuxtLink
        >
        <NuxtLink
          to="/contact"
          class="offcanvas-link d-block fs-6 mx-2 fw-bold text-decoration-none"
          >اتصل بنا</NuxtLink
        >
      </div>
      <NuxtLink
        class="appBtn d-flex text-decoration-none mt-5"
        to="/subscribe"
        title="الإشتراك"
      >
        <Icon name="material-symbols:mail" class="mx-1 fs-5 my-auto"></Icon>
        الإشتراك
      </NuxtLink>
    </div>
    <img src="../assets/images/logo-2.png" alt="" class="mt-5 mb-3" />
    <div class="second-footer align-items-center mt-3">
      <ul class="d-flex flex-row justify-content-center">
        <NuxtLink
          to="/terms"
          class="offcanvas-link d-block my-1 mx-2 text-decoration-none"
          style="font-size: 13px"
          >الأحكام والشروط</NuxtLink
        >
        <NuxtLink
          to="/privacy"
          class="offcanvas-link d-block my-1 mx-2 text-decoration-none"
          style="font-size: 13px"
          >سياسة الخصوصية</NuxtLink
        >
        <NuxtLink
          to="/refund"
          class="offcanvas-link d-block my-1 mx-2 text-decoration-none"
          style="font-size: 13px"
          >سياسة الاسترجاع
        </NuxtLink>
        <NuxtLink
          to="/shipping"
          class="offcanvas-link d-block my-1 mx-2 text-decoration-none"
          style="font-size: 13px"
          >سياسة الشحن</NuxtLink
        >
      </ul>
      <span class="mt-5"> جميع الحقوق محفوظه بواسطة © 2023 Humm </span>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.soc-icon {
  color: black;
  cursor: pointer;
}
.soc-icon:hover {
  color: red;
}
.offcanvas-link {
  color: black;
  cursor: pointer;
}
.offcanvas-link:hover {
  color: red;
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
  margin: auto 0;
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
</style>
