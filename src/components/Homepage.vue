<script setup>
import Dialog from "primevue/dialog";
import Button from "primevue/button";
import "primeicons/primeicons.css";
import { ref } from "vue";
const visible = ref(false);
const showHeading = ref(true);

const openDialog = () => {
  visible.value = true;
  showHeading.value = false;
};

const closeDialog = () => {
  visible.value = false;
  showHeading.value = true;
};
</script>
<template>
  <div class="landing-page">
    <div class="main-sec flex">
      <div class="left-side w-30 bg-red-900 h-screen"></div>
      <div class="bg-img w-70">
        <img alt="Background image" src="@/assets/images/bg-image.jpg" />
      </div>
    </div>
    <div class="upper-text absolute bottom-226 left-21" v-show="showHeading">
      <h1 class="text-8xl text-white mb-0 title">Explore</h1>
      <div class="model-btn flex items-center">
        <button
          @click="openDialog"
          class="w-20 h-20 rounded-full border border-white flex items-center justify-center mr-10 cursor-pointer"
        >
          +
        </button>
        <span class="font-sans text-white">More Details</span>
        <Dialog
          v-model:visible="visible"
          @hide="closeDialog"
          modal
          header="Explore"
          class="custom-dialog animated-dialog"
          :closable="false"
          :style="{
            maxWidth: '460px',
            marginRight: '60px',
            boxSizing: 'border-box',
            background: '#fff',
            padding: '55px 50px',
            fontSize: '3em',
            color: '#611818',
            position: 'absolute',
            left: '15%',
          }"
        >
          <p :style="{ fontSize: '16px', color: '#000' }">
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem
            accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
            quae ab illo inventore veritatis et quasi architecto beatae vitae
            dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit
            aspernatur aut odit aut fugit, sed quia consequuntur magni dolores
            eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est,
            qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit,
            sed quia non numquam eius modi tempora incidunt ut labore et dolore
            magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis
            nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut
            aliquid ex ea commodi consequatur?
          </p>
          <Button class="read-more-btn" label="Read More" />
          <Button
            class="custom-close-btn"
            @click="visible = false"
            icon="pi pi-times"
            :style="{ fontSize: '20px' }"
          />
        </Dialog>
      </div>
    </div>
    <div class="social-icons absolute right-30 bottom-100 flex flex-col gap-18">
      <span class="pi pi-facebook text-3xl text-white cursor-pointer"></span>
      <span class="pi pi-instagram text-3xl text-white cursor-pointer"></span>
    </div>
  </div>
</template>

<style>
.animated-dialog, .title {
  animation: dialog-open 1s !important;
}

@keyframes dialog-open {
  0% {
    opacity: 0;
    transform: scale(0.2);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

#pv_id_1_header {
  font-size: 55px;
  font-weight: bold;
}
.landing-page {
  position: relative;
}
.landing-page .main-sec {
  display: flex;
}
.landing-page .main-sec .left-side {
  width: 30%;
  background-color: #611818;
  height: 100vh;
}
.landing-page .main-sec .bg-img {
  width: 70%;
}
.landing-page .main-sec .bg-img img {
  width: 100%;
  height: 100vh;
  vertical-align: bottom;
  object-position: center right;
  object-fit: cover;
}
.landing-page .upper-text {
  position: absolute;
  transform: translateY(-50%);
  top: 50%;
  left: 23.01%;
}
.landing-page .upper-text .model-btn {
  display: flex;
  align-items: center;
}
.landing-page .upper-text h1 {
  font-size: 7vw;
  color: #fff;
  margin-bottom: 15px;
  letter-spacing: 10px;
}
.landing-page .upper-text button {
  width: 20px;
  border-radius: 50%;
  height: 20px;
  border: 1px solid #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 10px;
  cursor: pointer;
}
.landing-page .upper-text span {
  font-family: sans-serif;
  color: #fff;
}
.custom-close-btn {
  position: absolute;
  right: 10px;
  top: 15px;
  border: none;
  background: transparent;
  cursor: pointer;
}
.custom-close-btn .pi {
  font-size: 1.5em;
}
.read-more-btn {
  width: 185px;
  height: 43px;
  cursor: pointer;
  background: linear-gradient(45deg, #611818, #61181880);
  color: #fff;
  font-size: 16px;
  text-transform: uppercase;
  border: none;
}
.social-icons {
  display: flex;
  flex-direction: column;
  gap: 18px;
  position: absolute;
  right: 30px;
  bottom: 100px;
}
.social-icons span {
  font-size: 3vw;
  color: #fff;
  cursor: pointer;
}

@media (max-width: 800px) {
  .landing-page .upper-text h1 {
    font-size: 13vw;
  }
}
</style>
