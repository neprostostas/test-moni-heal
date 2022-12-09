<template>
  <div class="custom-footer">
    <footer class="footer-wrapper">
      <div class="footer-content">
        <div class="footer-top-part">
          <div class="footer-block one">
            <h3>Компанія</h3>
            <div class="detail-block company">
              <p>Про нас</p>
              <p>Новини</p>
              <p>Довідковий центр</p>
            </div>
          </div>
          <div class="footer-block two">
            <h3>Контакти</h3>
            <a class="mail-link" href="mailto:moehealthmapsapi@gmail.com">moehealthmapsapi@gmail.com</a>
            <div class="social-network-block">
              <div @click="[fb = !fb, inst = false, tg = false]" :class="{'active': fb}" class="wrap-net">
                <img src="../assets/fb.png" alt="fb">
              </div>
              <div @click="[fb = false, inst = !inst, tg = false]" :class="{'active': inst}" class="wrap-net">
                <img src="../assets/inst.png" alt="inst">
              </div>
              <div @click="[fb = false, inst = false, tg = !tg]" :class="{'active': tg}" class="wrap-net">
                <img src="../assets/tg.png" alt="tg">
              </div>
            </div>
          </div>
          <div class="footer-block three">
            <h3>Підписатися на розсилку</h3>
            <button class="email-input-button">
              Введіть вашу пошту
              <img src="../assets/right-arrow.png" alt="right-arrow">
            </button>
          </div>
          <div class="footer-block four">
            <select id="select">
              <option value="value1" selected>Українська</option>
              <option value="value2">English</option>
              <option value="value3">Polish</option>
            </select>
          </div>
        </div>
        <div class="footer-bottom">
          <div class="left-bottom-part">
            <img src="../assets/img/logo-sm.png" alt="logo-sm">
            <h3 class="info-line-text">2019 <span>MoniHeal. </span>Medical Online Information System</h3>
          </div>
          <div class="right-bottom-part">
            <a href="#">Захист даних</a>
            <a href="#">Політика приватності</a>
            <a href="#">Правила користувача</a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>

import {ref} from "vue";

export default {
  name: 'CustomFooter',

  setup() {

    const fb = ref(true)
    const inst = ref(false)
    const tg = ref(false)

    return {fb, inst, tg}
  }
}
</script>

<style scoped>

h3 {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  color: #16395b;
  font-weight: 700;
  font-size: 18px;
}

.info-line-text {
  font-family: "AvenirNextCyr-Regular", sans-serif;
  font-size: 14px;
}

.info-line-text span {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-size: 14px;
  color: #16395b;
  font-weight: 700;
}

.footer-bottom {
  margin-top: 40px;
  display: grid;
  grid-template-columns: repeat(2, auto);
  align-items: center;
  justify-content: space-between;
}

.left-bottom-part {
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 5px;
  align-items: center;
}

.right-bottom-part {
  display: grid;
  grid-template-columns: repeat(3, auto);
  gap: 20px;
  align-items: center;
}

.right-bottom-part a {
  color: #16395b;
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-size: 14px;
  font-weight: 700;
  text-decoration: underline;
}

.email-input-button {
  position: relative;
  text-align: left;
  width: -webkit-fill-available;
  margin-top: 10px;
  padding: 10px 0;
  background-color: transparent;
  border: none;
  border-bottom: 1px solid #00d7a8;
  color: #16395b;
  font-size: 12px;
}

.email-input-button img {
  transform: scale(.8);
  position: absolute;
  right: 0;
  top: 10px;
}

.social-network-block {
  display: grid;
  grid-template-columns: repeat(3, auto);
  gap: 15px;
  margin-top: 20px;
}

.wrap-net {
  cursor: pointer;
  display: grid;
  justify-content: center;
  align-items: center;
  background-color: #ffffff;
  border-radius: 50%;
  width: 40px;
  height: 40px;
}

.wrap-net:hover {
  background-color: #00ffc8;
}

.wrap-net.active {
  background-color: #00ffc8;
}

.mail-link {
  display: block;
  margin-top: 20px;
  text-decoration: unset;
  color: #00d7a8;
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-weight: 700;
  font-size: 12px;
}

.mail-link:hover {
  text-decoration: underline;
}

.detail-block.company {
  margin-top: 20px;
  display: grid;
  gap: 10px;
}

.detail-block.company p {
  font-size: 14px;
}

.footer-top-part {
  display: grid;
  grid-template-columns: repeat(4, auto);
  justify-items: center;
  align-items: start;
  justify-content: space-between;
}

.custom-footer {
  background: #f6f4fc;
}

.footer-wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px 120px;
}

#select {
  width: 240px;
  color: #16395b;
  font-weight: 600;
  font-size: 16px;
  padding: 10px;
  border: 1px solid #545784;
  border-radius: 5px;
  background-color: #f6f4fc;
}

@media (max-width: 1095px) {
  .footer-top-part {
    grid-template-columns: repeat(2, auto);
    gap: 50px;
    justify-content: space-evenly;
    align-items: center;
  }
}

@media (max-width: 1045px) {
  .footer-bottom {
    grid-template-columns: auto;
    gap: 20px;
    justify-content: space-evenly;
    align-items: center;
  }
}

@media (max-width: 750px) {
  .footer-block.three {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: 3;
  }
  .footer-block.four {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 3;
    grid-row-end: 4;
  }
}

@media (max-width: 675px) {
  .footer-wrapper {
    padding: 20px 60px;
  }
}

@media (max-width: 550px) {
  .footer-wrapper {
    padding: 20px;
    background-image: url('@/assets/img/footer-bg-mb.png');
    background-repeat: no-repeat;
    background-size: cover;
  }
  .footer-top-part {
    gap: 20px;
  }
  .footer-bottom {
    margin-top: 20px;
  }
  .footer-content {
    display: grid;
    padding-top: 100px;
    align-items: baseline;
  }
  #select {
    background-color: #244c83;
    border-color: #ffffff;
    color: #ffffff;
  }
  .info-line-text span, .footer-block h3, .email-input-button {
    color: #ffffff;
  }
  h3:not(.footer-block h3), .detail-block.company, .right-bottom-part a {
    color: #cecece;
  }
}

@media (max-width: 475px) {
  .mail-link, .social-network-block, .detail-block.company {
    margin-top: 10px;
  }
  .footer-top-part {
    justify-items: start;
    justify-content: space-between;
  }
  .footer-bottom {
    justify-content: space-between;
  }
  .email-input-button {
    width: calc(100vw - 100px);
  }
  #select {
    font-size: 12px;
  }
  .left-bottom-part {
    justify-content: start;
  }
}

@media (max-width: 465px) {
  .info-line-text, .info-line-text span, .right-bottom-part a {
    font-size: 12px;
  }
}

@media (max-width: 410px) {
  .info-line-text, .info-line-text span, .right-bottom-part a {
    font-size: 10px;
  }
}

</style>
