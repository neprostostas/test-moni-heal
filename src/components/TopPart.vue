<template>

  <div class="image-container">

    <div class="info-card-wrapper">
      <InfoCardMain />
    </div>

    <div class="clinic-logo-wrapper-mb">
      <img class="clinic-logo-img" src="../assets/img/clinic-logo.png" alt="clinic-logo">
    </div>

    <img class="main-image" src="../assets/img/image.png" alt="image">
    <img class="shadow-image" src="../assets/img/shadow.png" alt="shadow">
  </div>

  <div class="main-info-container">

    <div class="left-info-part">
      <div class="clinic-logo-wrapper">
        <img class="clinic-logo-img" src="../assets/img/clinic-logo.png" alt="clinic-logo">
      </div>

      <div class="block-text">
        <div class="text-info-container">
          <h3 class="h3-text">Медичний, оздоровчий центр <br class="br-mb"> «Благомед»</h3>
          <p class="info-clinic">Медичний центр</p>
        </div>

        <div class="statistic-part">
          <div class="mini-image-block star">
            <p>5,0</p>
            <img class="star" src="../assets/star.png" alt="star">
            <p class="add-text-review">(953 Відгуків)</p>
          </div>
          <div class="mini-image-block doctor">
            <p>120 Лікарів</p>
            <img class="doctor" src="../assets/doctor.png" alt="doctor">
          </div>
          <div class="mini-image-block letter">
            <p>340 Послуг</p>
            <img class="letter" src="../assets/letter.png" alt="letter">
          </div>
          <div class="mini-image-block department">
            <img class="department" src="../assets/department.png" alt="department">
            <p>50 Філіалів</p>
          </div>
        </div>
      </div>

    </div>

    <div class="right-info-part">
      <button class="button-text clinic">Про клініку</button>
      <button @click="photoOpen = !photoOpen" class="button-text mobile">Фото</button>
      <button class="button-text">Фото</button>
      <button class="button-location">
        <img class="location-img" src="../assets/location.png" alt="location">
        <img class="map-mb" src="../assets/map-mb.png" alt="map-mb">
      </button>
    </div>
  </div>

  <div v-if="photoOpen" class="gallery-container">
    <img src="../assets/img/photo-1.png" alt="photo-1">
    <img class="photo-2" src="../assets/img/photo-2.png" alt="photo-2">
    <div class="photo-special-wrapper">
      <p>+50 фото</p>
      <img class="photo-3" src="../assets/img/photo-3.png" alt="photo-3">
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
    const photoOpen = ref(true)
    return {photoOpen}
  }
}
</script>

<style scoped>

p {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.gallery-container {
  display: none;
  margin-top: -80px;
  height: 120px;
  margin-bottom: 80px;
  grid-template-columns: repeat(3, auto);
  justify-content: start;
  gap: 10px;
}

.info-card-wrapper {
  position: absolute;
  right: 20px;
  bottom: 0;
  z-index: 99;
}

.clinic-logo-img {
  width: 160px;
  height: 160px;
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
  align-items: center;
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

.photo-special-wrapper {
  position: relative;
}

.photo-3 {
  position: relative;
  filter: brightness(60%)
}

.photo-special-wrapper p {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%);
  z-index: 9;
  color: #ffffff;
  font-size: 12px;
  width: 55px;
}

.clinic-logo-wrapper-mb, .br-mb, .add-text-review, .mini-image-block.department, .map-mb, .button-text.mobile {
  display: none;
}

@media (max-width: 1285px) {
  .left-info-part {
    grid-template-columns: auto;
    gap: 0;
  }
  .clinic-logo-wrapper {
    display: none;
  }
  .clinic-logo-wrapper-mb {
    display: unset;
    position: absolute;
    top: 30px;
    left: 40px;
    z-index: 2;
  }
  .clinic-logo-wrapper-mb img {
    width: 162px;
    height: 162px;
  }
}

@media (max-width: 1180px) {
  .clinic-logo-wrapper-mb {
    top: -60px;
    left: 20px;
  }
  .clinic-logo-wrapper-mb img {
    width: 122px;
    height: 122px;
  }
}

@media (max-width: 1110px) {
  .br-mb {
    display: unset;
  }
  .info-clinic {
    padding-top: 10px;
  }
  .block-text {
    margin-top: 0;
  }
}

@media (max-width: 988px) {
  .main-info-container {
    grid-template-columns: auto;
  }
  .add-text-review {
    display: unset;
  }
  .mini-image-block.star {
    grid-template-columns: repeat(3, auto);
  }
  .mini-image-block.department {
    display: grid;
  }
  .mini-image-block.doctor img, .mini-image-block.letter img {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 2;
  }
  .mini-image-block.doctor p, .mini-image-block.letter p {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
  }
  .statistic-part {
    grid-template-columns: repeat(2, auto);
    justify-items: start;
  }
  .text-info-container {
    position: relative;
    left: -28px;
  }
  .statistic-part, .right-info-part {
    position: relative;
    left: -40px;
  }
  .block-text {
    gap: 40px;
  }
  .location-img {
    display: none;
  }
  .map-mb {
    display: unset;
  }
}

@media (max-width: 935px) {
  .clinic-logo-wrapper-mb img {
    width: 82px;
    height: 82px;
  }
  .clinic-logo-wrapper-mb {
    top: -40px;
    left: 20px;
  }
}

@media (max-width: 820px) {
  .block-text {
    margin-top: 10px;
  }
  .statistic-part {
    font-size: 12px;
  }
  .button-text, .button-location {
    font-size: 12px;
    padding: 10px;
  }
  .h3-text {
    font-size: 18px;
  }
  .info-clinic {
    font-size: 11px;
  }
}

@media (max-width: 700px) {
  .gallery-container {
    display: grid;
  }
  .button-text {
    display: none;
  }
  .button-text.mobile, .button-text.clinic {
    display: unset;
  }
}

@media (max-width: 600px) {
  .block-text {
    gap: 20px;
    margin-top: 35px;
  }
  .statistic-part {
    font-size: 10px;
  }
  .button-text, .button-location {
    font-size: 10px;
    padding: 10px;
  }
  .h3-text {
    font-size: 14px;
  }
  .info-clinic {
    font-size: 9px;
  }
  .main-info-container {
    width: 300px;
  }
}

@media (max-width: 500px) {
  .gallery-container {
    position: relative;
    left: -20px;
  }
}

@media (max-width: 450px) {
  .main-info-container {
    width: 250px;
  }
  .photo-2, .photo-3 {
    width: 100px;
    height: -webkit-fill-available;
    object-fit: cover;
    border-radius: 5px;
  }
}

@media (max-width: 440px) {
  .h3-text {
    font-size: 12px;
  }
}

</style>
