<template>
  <div
    class="container py-4 d-flex justify-content-between border-bottom border-1 border-dark"
  >
    <NuxtLink to="/" title="همم">
      <img src="../assets/images/logo.png" alt="" />
    </NuxtLink>

    <NuxtLink
      type="button"
      class="sub-btn text-decoration-none text-dark d-flex mt-3"
      to="/subscribe"
      title="الإشتراك"
    >
      <Icon
        name="material-symbols:mail"
        class="sub-icon border border-1 border-dark fs-2 p-1 rounded-circle"
      ></Icon>
      <span class="sub-title d-lg-inline-flex d-none mx-2 mt-1 fw-bold"
        >الإشتراك</span
      >
    </NuxtLink>

    <NuxtLink
      class="appBtn d-lg-inline-flex d-none text-decoration-none"
      to="/contact"
      title=" 	اتصل بنا   "
    >
      اتصل بنا
    </NuxtLink>
  </div>

  <div class="container py-2 border-bottom border-1 border-dark d-flex">
    <NuxtLink
      class="menu-btn text-decoration-none d-flex align-items-center"
      type="button"
      data-bs-toggle="offcanvas"
      data-bs-target="#offcanvasRight"
      aria-controls="offcanvasRight"
    >
      <Icon name="material-symbols:menu" class="fs-1"></Icon>
      <span class="fw-bold fs-5">القائمة</span>
    </NuxtLink>
    <ul class="my-auto d-lg-flex d-none ms-auto">
      <NuxtLink to="/food" class="nav-link" title="وصفات">
        <Icon name="mingcute:fork-knife-fill" class="fs-4" />
        <span class="fw-bolder fs-5 mx-2">وصفات</span></NuxtLink
      >
      <NuxtLink to="/shows" class="nav-link" title="برامج">
        <Icon name="octicon:sparkle-fill-16" class="fs-4" />
        <span class="fw-bolder fs-5 mx-2">برامج</span>
      </NuxtLink>
      <NuxtLink to="/read" class="nav-link" title="المقالات">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="19.61"
          height="22.968"
          viewBox="0 0 24.61 27.968"
        >
          <path
            id="Path_35235"
            data-name="Path 35235"
            d="M955.579,533.909a1.481,1.481,0,0,0-.238-.109l-10.7-4.9,10.7-4.9a1.451,1.451,0,1,0-1.214-2.623,1.422,1.422,0,0,0-.214.152l-9.594,6.818,1.108-11.718a1.428,1.428,0,0,0,.025-.261,1.452,1.452,0,0,0-2.9,0,1.428,1.428,0,0,0,.025.261l1.107,11.718-9.594-6.818a1.357,1.357,0,0,0-.213-.152,1.452,1.452,0,1,0-1.452,2.514,1.468,1.468,0,0,0,.238.109l10.7,4.9-10.7,4.9a1.506,1.506,0,0,0-.238.109,1.452,1.452,0,0,0,1.452,2.515,1.368,1.368,0,0,0,.213-.152l9.594-6.817-1.107,11.717a1.427,1.427,0,0,0-.025.261,1.452,1.452,0,0,0,2.9,0,1.427,1.427,0,0,0-.025-.261l-1.108-11.717,9.594,6.817a1.434,1.434,0,0,0,.214.152,1.452,1.452,0,1,0,1.452-2.515"
            transform="translate(-931.696 -514.916)"
          />
        </svg>

        <span class="fw-bolder fs-5 mx-2">المقالات</span>
      </NuxtLink>

      <NuxtLink class="nav-link" title="أكاديمية همم">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="19.691"
          height="19.71"
          viewBox="0 0 25.691 25.71"
        >
          <path
            id="Path_35232"
            data-name="Path 35232"
            d="M1217.5,439.478l-7.038-2.346a.806.806,0,0,1-.544-.776v-.012a.806.806,0,0,1,.544-.776l7.038-2.346a4.979,4.979,0,1,0-6.234-6.319L1208.9,434a.807.807,0,0,1-.777.544h-.011a.808.808,0,0,1-.777-.544l-2.346-7.037a4.979,4.979,0,1,0-6.319,6.235l7.1,2.367a.807.807,0,0,1,.544.776.019.019,0,0,0,0,.012.807.807,0,0,1-.544.776l-7.037,2.346a4.98,4.98,0,1,0,6.235,6.319l2.367-7.1a.808.808,0,0,1,.777-.544h.011a.807.807,0,0,1,.777.544l2.367,7.1a4.979,4.979,0,1,0,6.234-6.319"
            transform="translate(-1195.266 -423.495)"
          />
        </svg>
        <span class="fw-bolder fs-5 mx-2">أكاديمية همم</span>
      </NuxtLink>
    </ul>
    <button
      type="button"
      class="btn btn-link text-decoration-none text-dark me-auto"
      data-bs-toggle="modal"
      data-bs-target="#exampleModal"
    >
      ابحث هنا
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="20.763"
        height="20.763"
        class="mx-1 my-auto"
        viewBox="0 0 25.763 25.763"
      >
        <path
          id="Path_35249"
          data-name="Path 35249"
          d="M13.414,2A11.414,11.414,0,1,1,2,13.414,11.418,11.418,0,0,1,13.414,2Zm0,20.292a8.878,8.878,0,1,0-8.878-8.878A8.876,8.876,0,0,0,13.414,22.292Zm10.761.09,3.588,3.587-1.795,1.795-3.587-3.588,1.793-1.793Z"
          transform="translate(-2 -2)"
        />
      </svg>
    </button>
    <div
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content d-flex px-3 py-1">
          <form class="modal-form d-flex" role="search">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20.763"
              height="20.763"
              class="ms-2 my-auto"
              viewBox="0 0 25.763 25.763"
            >
              <path
                id="Path_35249"
                data-name="Path 35249"
                d="M13.414,2A11.414,11.414,0,1,1,2,13.414,11.418,11.418,0,0,1,13.414,2Zm0,20.292a8.878,8.878,0,1,0-8.878-8.878A8.876,8.876,0,0,0,13.414,22.292Zm10.761.09,3.588,3.587-1.795,1.795-3.587-3.588,1.793-1.793Z"
                transform="translate(-2 -2)"
              />
            </svg>

            <input
              class="form-control me-2 h-50 border-0"
              type="search"
              placeholder="ابحث هنا"
              aria-label="Search"
            />
            <button
              type="button"
              class="btn-close me-2 my-auto"
              aria-label="Close"
              data-bs-dismiss="modal"
            ></button>
          </form>
        </div>
      </div>
    </div>
  </div>

  <div
    class="offcanvas offcanvas-end bg-black p-3"
    tabindex="-1"
    id="offcanvasRight"
    aria-labelledby="offcanvasRightLabel"
  >
    <div class="offcanvas-header">
      <button
        type="button"
        class="btn-close bg-white rounded-circle text-black me-auto ms-4 mt-3 mb-5"
        data-bs-dismiss="offcanvas"
        aria-label="Close"
      ></button>
    </div>
    <div class="offcanvas-body text-white">
      <NuxtLink
        to="/"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >الرئيسيه</NuxtLink
      >
      <NuxtLink
        to="/food"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >وصفات</NuxtLink
      >
      <NuxtLink
        to="/shows"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >برامج</NuxtLink
      >
      <NuxtLink
        to="/read"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >مقالات</NuxtLink
      >
      <NuxtLink
        to="/"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >أكاديمية همم</NuxtLink
      >
      <NuxtLink
        to="/press"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >الصحافه</NuxtLink
      >
      <NuxtLink
        to="/about"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >من نحن</NuxtLink
      >
      <NuxtLink
        to="/contact"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >اتصل بنا</NuxtLink
      >
      <NuxtLink
        to="/advertise"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >أعلن معنا</NuxtLink
      >
      <NuxtLink
        to="/subscribe"
        class="offcanvas-link mb-4 d-block fs-1 fw-bold text-decoration-none"
        >الإشتراك</NuxtLink
      >

      <div class="social-icon d-flex mt-5">
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
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.sub-btn:hover .sub-title {
  color: red;
}
.sub-btn:hover .sub-icon {
  background-color: black;
  color: white;
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
.menu-btn {
  color: black;
  cursor: pointer;
}
.menu-btn:hover {
  color: red;
}
.nav-link {
  margin: auto 25px;
}
.nav-link:hover span {
  color: red;
}
.modal-content {
  margin: 55% auto;
  height: fit-content;
}
.modal-dialog {
  height: 150px;
}
.offcanvas-link {
  color: white;
  cursor: pointer;
}
.offcanvas-link:hover {
  color: red;
}
::-webkit-scrollbar {
  width: 12px;
}

::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
}

::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.5);
}

.soc-icon {
  color: white;
  cursor: pointer;
}
.soc-icon:hover {
  color: red;
}
</style>
