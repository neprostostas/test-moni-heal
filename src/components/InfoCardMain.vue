<template>
  <div class="info-card-main" :class="{'active': blockActive}">

    <div class="circle-button" @click="blockActive = !blockActive">
      <svg :class="{'active': blockActive}" :style="[blockActive ? {'transform': 'rotate(180deg) scale(.6)', 'padding': '0 0 8px 0'} : {'transform': 'scale(.6)'}]" width="24" height="20" :fill="[blockActive ? '#26d6a8' : '#000000']"><path d="m12 6.586-8.707 8.707 1.414 1.414L12 9.414l7.293 7.293 1.414-1.414L12 6.586z"/></svg>
    </div>

    <div class="bg-part">
      <h2>Адреса:</h2>
      <p class="address-text">пр. Відродження, 13, Луцьк, <br> Волинська область, Україна, 43000</p>

      <h2>Контакти:</h2>
      <div class="block-contact">
        <p class="contact">+38 (099) 999-99-99</p>
        <p class="contact">+38 (0332) 77-08-09</p>
      </div>

      <div class="block-unactive" v-if="!blockActive">
        <h2 class="schedule-text">Графік роботи: <span>ПН-СБ 09:00-20:00</span></h2>
      </div>

      <div class="block-active" :class="{ active: blockActive }">
        <h2 class="schedule-text">Графік роботи: <span>Зараз працює</span></h2>

        <div class="schedule-active">
          <p>понеділок 09:00-20:00</p>
          <p>вівторок 09:00-20:00</p>
          <p class="active-day">середа 09:00-20:00</p>
          <p>четвер 09:00-20:00</p>
          <p>п'ятниця 09:00-20:00</p>
          <p>субота 09:00-20:00</p>
        </div>
      </div>
    </div>

    <div class="mb-part" :class="{ active: blockActive }">
      <h2>Адреса:</h2>
      <p class="address-text">пр. Відродження, 13, Луцьк, <br> Волинська область, Україна, 43000</p>

      <h2>Контакти:</h2>
      <div class="block-contact">
        <p class="contact">+38 (099) 999-99-99</p>
        <p class="contact">+38 (0332) 77-08-09</p>
      </div>

      <h2 class="schedule-text">Графік роботи: <span>Зараз працює</span></h2>
      <div class="schedule-active">
        <p>понеділок 09:00-20:00</p>
        <p>вівторок 09:00-20:00</p>
        <p class="active-day">середа 09:00-20:00</p>
        <p>четвер 09:00-20:00</p>
        <p>п'ятниця 09:00-20:00</p>
        <p>субота 09:00-20:00</p>
      </div>

    </div>

  </div>
</template>

<script>

import {ref} from "vue";

export default {
  name: 'InfoCardMain',
  components: {},

  setup() {

    const blockActive = ref(false)

    return {blockActive}
  }
}
</script>

<style scoped>

h2 {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
  font-size: 16px;
}

.block-active {
  width: 0;
  height: 0;
  opacity: 0;
  transition: none;
}

.block-active.active {
  transition: opacity .5s ease-in;
  width: unset;
  height: unset;
  opacity: 1;
}

.schedule-active {
  padding-top: 10px;
}

.active-day {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
  font-weight: 600;
}

.address-text {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
  font-weight: 600;
  font-size: 14px;
  padding: 10px 0;
}

.schedule-text span {
  font-size: 14px;
}

.block-contact {
  padding: 5px 0 10px;
}

.contact {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
  font-size: 14px;
}

.info-card-main {
  position: relative;
  bottom: 4px;
  padding: 15px 60px 25px 30px;
  background: #ffffff;
  -webkit-border-top-left-radius: 25px;
  -webkit-border-top-right-radius: 25px;
  -moz-border-radius-topleft: 25px;
  -moz-border-radius-topright: 25px;
  border-top-left-radius: 25px;
  border-top-right-radius: 25px;
  width: fit-content;
}

.circle-button {
  position: absolute;
  top: -15px;
  right: 50px;
  cursor: pointer;
  width: 30px;
  height: 28px;
  border-radius: 50%;
  background: #ffffff;
  border: 1px solid #6d86ad;
  display: grid;
  justify-items: center;
  align-items: center;
  padding-bottom: 2px;
}

.mb-part {
  display: none;
}

@media (max-width: 945px) {
  .info-card-main {
    padding: 0;
  }
  .info-card-main.active {
    border: 1px solid #6d86ad;
    border-top: none;
    top: 325px;
    padding: 15px 60px 25px 30px;
    -webkit-border-radius: 0 0 25px 25px;
    -moz-border-radius: 0 0 25px 25px;
    border-radius: 0 0 25px 25px;
  }
  .bg-part, .mb-part {
    display: none;
  }
  .mb-part.active {
    display: unset;
  }
  .circle-button svg {
    padding-bottom: 8px!important;
    transform: rotate(180deg) scale(0.6)!important;
  }
  .circle-button svg.active {
    padding-top: 2px!important;
    transform: rotate(0) scale(0.6)!important;
  }
}

@media (max-width: 820px) {
  h2, .schedule-active, .contact, .address-text {
    font-size: 10px;
  }
  .schedule-text span {
    font-size: 8px;
  }
  .info-card-main.active {
    top: 227px;
    padding: 15px;
  }
}

@media (max-width: 440px) {
  h2, .schedule-active, .contact, .address-text {
    font-size: 8px;
  }
  .schedule-text span {
    font-size: 6px;
  }
  .info-card-main.active {
    top: 191px;
    padding: 10px;
  }
}

</style>
