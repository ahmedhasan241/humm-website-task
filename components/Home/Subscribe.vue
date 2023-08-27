<template>
  <section class="mt-2xl">
    <div class="container">
      <div class="newsletters">
        <div class="row justify-content-between">
          <div class="col-lg-5">
            <h1
              class="fs-1 text-dark fw-bolder"
              data-aos="fade-up"
              data-aos-duration="800"
              data-aos-easing="ease-in-out-cubic"
            >
              اشترك في نشرة همم
            </h1>
          </div>
          <div class="col-lg-7 col-xl-6">
            <h3 class="text-dark">نشرة همم البريدية</h3>
            <form
              id="subscribe-form"
              method="post"
              name="subscribe-form"
              target="_self"
              @submit.prevent="onSubmit"
            >
              <div class="row gx-2">
                <div class="col-lg-5 mt-4">
                  <input
                    class="form-control"
                    id="FNAME"
                    type="text"
                    v-model="fullName"
                    placeholder="الاسم بالكامل"
                    name="FNAME"
                  />
                </div>
                <div class="col-lg-5 mt-4">
                  <input
                    class="form-control"
                    id="EMAIL"
                    type="email"
                    v-model="email"
                    placeholder="البريد الالكترونى"
                    name="EMAIL"
                    required="required"
                  />

                  <div
                    style="position: absolute; left: -5000px"
                    aria-hidden="true"
                  >
                    <input
                      type="text"
                      name="b_3f49d1e04dfc49a9c10a99c09_547cad1821"
                      tabindex="-1"
                      value="value"
                    />
                  </div>
                </div>
                <div class="col-lg-2 mt-4">
                  <button
                    class="appBtn appBtn-dark w-100"
                    type="submit"
                    value="Subscribe"
                    name="subscribe"
                  >
                    الإشتراك
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const email = ref();
const fullName = ref();
async function onSubmit() {
  const { data } = await useAsyncGql({
    operation: "CreateContactItem",
    variables: {
      name: fullName.value,
      email: email.value,
      type: "subsribe",
    },
  });
  console.log(data?.value);
  const response = data?.value?.create_Contact_item;
  console.log(response);
  if (response) {
    navigateTo("/subscribe/message");
  } else {
    navigateTo("/subscribe");
  }
}
</script>

<style scoped>
.newsletters {
  border: 1px solid #000;
  color: #000;
  box-shadow: 15px 15px #000;
  padding: calc(1.2875rem + 3.78827vw);
  overflow: hidden;
  position: relative;
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

  box-shadow: 3px 3px black;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
    -webkit-box-shadow 0.15s ease-in-out;
  text-align: center;
}

.appBtn:hover {
  color: white;
  background-color: black;
  border-color: white;
  box-shadow: 3px 3px black;
}
</style>
