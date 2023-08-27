<template>
  <div class="container mt-5">
    <Head>
      <Title>اتصل بنا</Title>
    </Head>
    <div class="row">
      <div
        class="position-relative col-12 col-lg-5 card border-0 align-self-center"
        data-aos="fade-zoom-in"
        data-aos-duration="900"
        data-aos-easing="ease-in-out-cubic"
        data-aos-offset="0"
      >
        <img
          class="contact-info-icon position-absolute img-fluid h-25 w-25 z-3 bottom-0 start-0 mb-2"
          src="https://humm.world/wp-content/themes/humm/public/static/img/6.svg"
          title="img"
        />

        <div class="w-100 h-100">
          <svg
            class="card-img w-100 h-100"
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            width="6360.593"
            height="6780.664"
            viewBox="0 0 636.593 678.664"
          >
            <defs>
              <clipPath id="clip-path">
                <path
                  id="Path_35330"
                  data-name="Path 35330"
                  d="M636.593,678.664H0V0H636.593Z"
                  fill="none"
                />
              </clipPath>
            </defs>
            <g
              id="Group_21781"
              data-name="Group 21781"
              transform="translate(0 0)"
            >
              <g
                id="Mask_Group_3"
                data-name="Mask Group 3"
                transform="translate(0 0)"
                clip-path="url(#clip-path)"
              >
                <path
                  id="Path_35329"
                  data-name="Path 35329"
                  d="M513.96,779.386,659.315,924.9v-.051a54.953,54.953,0,0,0,39.334,16.565h134.12a55.214,55.214,0,0,0,52.4-38.061l21.58,21.522A55.079,55.079,0,0,0,946.1,941.411h40.141v-.03h.006l.419-21.826a43.851,43.851,0,0,1,.469-5.444A43.315,43.315,0,0,1,1011,881.774a42.319,42.319,0,0,1,18.523-4.287l20.454.418v-.015h.032l2.931-19.309a91.084,91.084,0,0,1,66.043-74.349l15.566-4.255.826-.225V502.638a54.563,54.563,0,0,0-15.184-37.9L974.84,319.282a55.094,55.094,0,0,0-39.359-16.535L553.9,302.8a55.189,55.189,0,0,0-55.114,55.119V741.492a54.6,54.6,0,0,0,15.179,37.893"
                  transform="translate(-498.779 -262.746)"
                />
              </g>
            </g>
          </svg>
        </div>

        <div
          class="card-img-overlay text-white mx-3 mx-sm-5 mt-5 mt-lg-0 mt-xl-5"
        >
          <h1 class="card-title mx-3 mt-3 mt-lg-5">
            شاركونا استفساراتكم واقتراحاتكم
          </h1>

          <a
            class="contact-link d-flex align-items-center fw-bold text-decoration-none text-white mt-1 mt-xl-5"
            href="mailto:Hi@humm.world"
            target="_blank"
            title="Hi@humm.world"
          >
            <Icon name="material-symbols:mail" class="fs-1" />
            <span class="fs-2"> Hi@humm.world </span>
          </a>
          <a
            class="contact-link d-flex align-items-center fw-bold text-decoration-none text-white mt-1 mt-xl-3"
            href="tel: +20 101 987 0053"
            target="_blank"
            title="+20 101 987 0053"
          >
            <Icon class="fs-1" name="material-symbols:call" />
            <span class="fs-3" style="direction: ltr"> +20 101 987 0053 </span>
          </a>
        </div>
      </div>
      <div class="col-12 col-lg-7">
        <div class="contact-form p-5">
          <form action="" class="mt-5 w-100" @submit.prevent="onSubmit">
            <div class="row row-cols-1 row-cols-md-2">
              <div class="col mb-3">
                <label for="fullNameInput" class="form-label"
                  >الاسم الكامل</label
                >
                <input
                  type="text"
                  v-model="fullName"
                  class="form-control bg-transparent"
                  id="fullNameInput"
                  required="required"
                />
              </div>
              <div class="col mb-3">
                <label for="numberInput" class="form-label">رقم الهاتف</label>
                <input
                  type="text"
                  v-model="phone"
                  class="form-control bg-transparent"
                  id="numberInput"
                  required="required"
                />
              </div>
            </div>
            <div class="row row-cols-1 row-cols-md-2">
              <div class="col mb-3">
                <label for="emailInput" class="form-label"
                  >البريد الإلكتروني</label
                >
                <input
                  type="email"
                  v-model="email"
                  class="form-control bg-transparent"
                  id="emailInput"
                  aria-describedby="emailHelp"
                  required="required"
                />
              </div>
              <div class="col mb-3">
                <label for="recognizeUsInput" class="form-label"
                  >كيف سمعت عنا</label
                >
                <input
                  type="text"
                  v-model="source"
                  class="form-control bg-transparent"
                  id="recognizeUsInput"
                  required="required"
                />
              </div>
            </div>
            <div class="mb-3">
              <label for="textareaInput" class="form-label">الرسالة</label>
              <textarea
                class="form-control bg-transparent"
                id="textareaInput"
                rows="5"
                v-model="message"
                required="required"
              ></textarea>
            </div>
            <button
              class="appBtn d-flex align-items-center text-decoration-none"
              title="إرسال"
              type="submit"
            >
              إرسال
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const phone = ref();
const source = ref();
const message = ref();
const email = ref();
const fullName = ref();
async function onSubmit() {
  const { data } = await useAsyncGql({
    operation: "CreateContactItem",
    variables: {
      name: fullName.value,
      email: email.value,
      phone: phone.value,
      message: message.value,
      source: source.value,
      type: "contact",
    },
  });
  console.log(data?.value);
  const response = data?.value?.create_Contact_item;
  console.log(response);
  if (response) {
    navigateTo("/contact/message");
  } else {
    navigateTo("/contact");
  }
}
</script>

<style scoped>
.contact-link {
  color: white;
}
.contact-link:hover span {
  color: red;
}
.card-img {
  rotate: 90deg;
}
.appBtn {
  background-color: transparent;
  border: 1px solid #000000;
  color: #000000;
  cursor: pointer;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  padding: 7px 40px;
  font-weight: 700;
  margin: 20px 10px;
  box-shadow: -4px 4px rgb(0, 0, 0);
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
    -webkit-box-shadow 0.15s ease-in-out;
  text-align: center;
}

.appBtn:hover {
  color: rgb(255, 255, 255);
  background-color: rgb(0, 0, 0);
  border-color: rgb(255, 255, 255);
  box-shadow: 4px 4px rgb(0, 0, 0);
}
</style>
