<template>

  <div class="image-container">

    <div class="info-card-wrapper">
      <InfoCardMain />
    </div>

    <img class="main-image" src="../assets/image.png" alt="image">
    <img class="shadow-image" src="../assets/shadow.png" alt="shadow">
  </div>

  <div class="main-info-container">

    <div class="left-info-part">
      <div class="clinic-logo-wrapper">
        <div @click="openLogo = false" v-if="openLogo === true" class="overlay"></div>
        <img @click="openLogo = !openLogo" :class="{ open: openLogo }" class="clinic-logo-img" src="../assets/clinic-logo.png" alt="clinic-logo">
      </div>

      <div class="block-text">
        <div class="text-info-container">
          <h3 class="h3-text">Медичний, оздоровчий центр «Благомед»</h3>
          <p class="info-clinic">Медичний центр</p>
        </div>

        <div class="statistic-part">
          <div class="mini-image-block">
            <p>5,0</p>
            <img class="star" src="../assets/star.png" alt="star">
          </div>
          <div class="mini-image-block">
            <p>120 Лікарів</p>
            <img class="doctor" src="../assets/doctor.png" alt="doctor">
          </div>
          <div class="mini-image-block">
            <p>340 Послуг</p>
            <img class="letter" src="../assets/letter.png" alt="letter">
          </div>
        </div>
      </div>

    </div>

    <div class="right-info-part">
      <button class="button-text">Про клініку</button>
      <button class="button-text">Фото</button>
      <button class="button-location">
        <img src="../assets/location.png" alt="location">
      </button>
    </div>

  </div>

</template>

<script>

import {ref} from "vue";
import InfoCardMain from "@/components/InfoCardMain.vue";

export default {
  name: 'TopPart',
  components: {InfoCardMain},

  setup() {

    const openLogo = ref(false)

    return {
      openLogo
    }
  }
}
</script>

<style scoped>

@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.css);

p {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.info-card-wrapper {
  position: absolute;
  right: 20px;
  bottom: 0;
  z-index: 99;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.03);
  border-radius: 16px;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.clinic-logo-img {
  transition: 1s ease all;
  cursor: pointer;
  width: 160px;
  height: 160px;
}

.clinic-logo-img.open {
  transition: 1s ease all;
  position: absolute;
  z-index: 1001;
  bottom: 100%;
  width: 400px;
  height: 400px;
  image-rendering: pixelated;
}

.right-info-part {
  display: grid;
  grid-template-columns: repeat(3, auto);
  gap: 10px;
}

.button-text:hover, .button-location:hover {
  position: relative;
  top: 1px;
  background: #c0d3fe;
}

.button-text, .button-location {
  border: 1px solid #c0d3fe;
  border-radius: 25px;
  background: #ffffff;
  padding: 10px 20px;
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-size: 14px;
  font-weight: 700;
}

.button-location {
  width: 40px;
  height: 40px;
  padding: 8px 5px 5px;
  border-radius: 50%;
}

.main-info-container {
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 20px;
  align-items: end;
  position: relative;
  bottom: 105px;
  left: 45px;
}

.left-info-part {
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 20px;
  align-items: center;
  justify-content: start;
}

.block-text {
  margin-top: 20px;
  display: grid;
  gap: 60px;
}

.statistic-part {
  display: grid;
  grid-template-columns: repeat(3, auto);
  align-items: center;
  justify-content: start;
  gap: 10px;
  font-weight: 600;
}

.mini-image-block {
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 5px;
}

.h3-text {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-size: 24px;
  color: #ffffff;
  font-weight: 700;
}

.info-clinic {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-size: 14px;
  color: #ffffff;
  font-weight: 700;
}

.image-container {
  position: relative;
}

.main-image, .shadow-image {
  width: 100%;
  border-radius: 15px;
}

.main-image {
  position: relative;
}

.shadow-image {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 5px;
}

.clinic-logo-img {
  animation: bounce 4s infinite;
  -webkit-animation: bounce 4s infinite;
  -moz-animation: bounce 4s infinite;
  -o-animation: bounce 4s infinite;
}

@-webkit-keyframes bounce { 0% {-webkit-transform: translateY(0);} 50% {-webkit-transform: translateY(-10px);} 100% {-webkit-transform: translateY(0px);} }
@-moz-keyframes bounce { 0% {-moz-transform: translateY(0);} 50% {-moz-transform: translateY(-10px);} 100% {-moz-transform: translateY(0px);} }
@-o-keyframes bounce { 0% {-o-transform: translateY(0);} 50% {-o-transform: translateY(-10px);} 100% {-o-transform: translateY(0px);} }
@keyframes bounce { 0% {transform: translateY(0);} 50% {transform: translateY(-10px);} 100% {transform: translateY(0px);} }

</style>
