<template>
  <div :class="{'card-active': cardActive}" class="doctor-card" @click="cardActive = !cardActive">

    <div class="hot-top-block">
      <div class="top-part">
        <div class="left-info-part">
          <div class="info-child">
            <div class="wrapper-icon">
              <img src="../assets/star-rate.png" alt="star-rate">
            </div>
            <div class="text-container">
              <h3 class="number-statistic">{{doctor.rate.toFixed(1)}}</h3>
              <p>Рейтинг</p>
            </div>
          </div>
          <div class="info-child">
            <div class="wrapper-icon">
              <img src="../assets/review.png" alt="review">
            </div>
            <div class="text-container">
              <h3 class="number-statistic">{{doctor.reviews}}</h3>
              <p>Відгуків</p>
            </div>
          </div>
          <div class="info-child">
            <div class="wrapper-icon">
              <img src="../assets/services.png" alt="services">
            </div>
            <div class="text-container">
              <h3 class="number-statistic">{{doctor.services}}</h3>
              <p>Послуг</p>
            </div>
          </div>
        </div>

        <div class="right-ava-part">
          <img class="doctor-ava" :src="getImgUrl(doctor.img)" :alt="doctor.img">
          <div class="wrapper-indicator">
            <div :class="{ online: online }" class="online-indicator"></div>
          </div>
          <h2 class="text-online">{{online ? "Доступний" : "Не доступний"}}</h2>
        </div>

      </div>

      <div class="main-part">
        <h3 class="name-text">{{doctor.name}}</h3>

        <div class="position-container">
          <h2 :class="{'card-active': cardActive}" class="position-text">{{doctor.position}}</h2>
          <img :class="{'card-active': cardActive}" class="shadow-text-img" src="../assets/img/shadow-text.png" alt="shadow-text">
        </div>
      </div>
    </div>

    <div class="location-block">
      <img src="../assets/location-doctor.png" alt="location-doctor">
      <div class="location-text-block">
        <p class="location-text">{{doctor.location}}</p>
        <p v-if="cardActive" class="location-detail-text">{{doctor['location-detail']}}</p>
      </div>
    </div>

    <div v-if="cardActive" class="addition-info-block">
      <hr class="divide-line">
      <h2 class="price-text">Послуги та ціни:</h2>
      <p class="consult-text">Консультація<span> - від {{doctor.price1}} грн</span></p>
      <p class="consult-text">Сеанс терапії<span> - від {{doctor.price2}} грн</span></p>

      <div class="button-group">
        <button class="button active">Написати</button>
        <button class="button">Детальніше</button>
      </div>
    </div>

  </div>
</template>

<script>
import {ref, watchEffect} from "vue";

export default {
  name: 'DoctorCard',
  components: {},
  props: {
    doctor: {
      active: Boolean,
      rate: Number,
      preview: Number,
      services: Number,
      name: String,
      img: String,
      position: String,
      location: String,
      'location-detail': String,
      price1: Number,
      price2: Number,
    }
  },

  setup(props) {

    const online = ref(false)
    const cardActive = ref(false)

    watchEffect(()=>{
      online.value = props.doctor.active
    })

    function getImgUrl(pic) {
      return require('../assets/img/' + pic + '.png')
    }

    return {getImgUrl, online, cardActive}
  }
}
</script>

<style scoped>

.price-text {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-weight: 700;
  font-size: 18px;
  color: #000000;
  padding-bottom: 5px;
}

.consult-text {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-weight: 700;
  color: #575757;
  font-size: 12px;
}

.consult-text span {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
  font-weight: 800;
  color: #000000;
  font-size: 13px;
}

.addition-info-block {
  text-align: left;
}

.button-group {
  padding-top: 20px;
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 10px;
}

.button {
  padding: 10px 5px;
  background-color: #ffffff;
  border-radius: 25px;
  border: 1px solid #d2e1f5;
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-weight: 700;
  font-size: 12px;
  color: #000000;
}

.button:hover {
  background-color: #d2e1f5;
}

.button.active {
  border: 1px solid #00d7a8;
}

.button.active:hover {
  background-color: #00d7a8;
}

.doctor-card {
  display: grid;
  gap: 30px;
  align-content: space-between;
  margin: 20px;
  background-color: #ffffff;
  padding: 20px;
  border-radius: 25px;
  height: 385px;
}

.doctor-card.card-active {
  height: -webkit-fill-available;
  filter: drop-shadow(0px 0px 5px rgba(101, 101, 101, 0.71));
  border: 2px solid #00d7a8;
  padding: 16px;
  gap: 10px;
}

.divide-line {
  height: 1px;
  border: none;
  border-top: 1px solid #d2e1f5;
  width: calc(100% + 32px);
  margin: 10px 0 20px -16px;
}

.position-container {
  position: relative;
}

.name-text, .position-text {
  text-align: left;
  font-family: "AvenirNextCyr-Medium", sans-serif;
}

.position-text {
  position: relative;
  height: 58px;
  overflow-y: scroll;
  margin-top: 10px;
  padding-bottom: 35px;
  color: #0943bf;
  font-weight: 800;
  font-size: 16px;
  transition: none;
}

.position-text.card-active {
  transition: opacity .5s ease-in;
  position: unset;
  height: unset;
  overflow-y: unset;
  padding-bottom: 0;
}

.shadow-text-img {
  pointer-events: none;
  position: absolute;
  left: 0;
  right: 0;
  bottom: -5px;
  height: 100%;
  width: 100%;
}

.shadow-text-img.card-active {
  display: none;
}

.location-text, .location-detail-text {
  text-align: left;
  font-weight: 600;
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.location-text {
  font-size: 12px;
  color: #000000;
}

.location-detail-text {
  color: #707070;
  opacity: .7;
  font-size: 12px;
}

.location-block {
  display: grid;
  align-items: center;
  justify-content: start;
  grid-template-columns: repeat(2, auto);
  gap: 5px;
}

.name-text {
  padding-top: 20px;
  color: #000000;
  font-weight: 800;
  font-size: 20px;
}

.text-online {
  color: #16395b;
  font-size: 12px;
  margin-top: -10px;
}

.wrapper-indicator {
  position: relative;
  top: -27px;
  left: 5px;
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background-color: #ffffff;
}

.online-indicator {
  position: absolute;
  top: 1px;
  left: 1px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #d2e0f5;
}

.online-indicator.online {
  background-color: #00d7a8;
}

.top-part {
  display: grid;
  grid-template-columns: repeat(2, auto);
  justify-content: space-between;
}

.doctor-ava {
  width: 92px;
  height: 92px;
  object-fit: cover;
  border-radius: 50%;
}

.left-info-part {
  display: grid;
  gap: 10px;
}

.wrapper-icon {
  display: grid;
  justify-content: center;
  align-items: center;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #e3ecff;
}

.text-container {
  text-align: left;
}

.info-child {
  display: grid;
  align-items: center;
  justify-content: start;
  grid-template-columns: repeat(2, auto);
  gap: 10px;
}

.number-statistic {
  color: #0943bf;
  font-size: 16px;
  font-weight: 600;
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.text-container p {
  color: #707070;
  font-size: 12px;
}

</style>
