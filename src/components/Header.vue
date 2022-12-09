<template>
  <div class="custom-header">
    <header class="header-wrapper">

      <div class="logo-wrapper">
        <img class="logo-img" src="../assets/img/logo-bg.png" alt="logo-bg">
        <img class="logo-sm" src="../assets/img/logo-sm.png" alt="logo-sm">
      </div>

      <div class="input-container">
        <input type="search" id="site-search" :placeholder="mobile ? 'Знайти фахівця' : 'Шукати фахівця, клініку, послугу...'">
        <img class="search-icon" src="../assets/search.png" alt="search">
      </div>

      <nav id="nav-custom">
        <select id="select">
          <option value="value1" selected>Українська</option>
          <option value="value2">English</option>
          <option value="value3">Polish</option>
        </select>

        <button class="button-login">
          <img class="lock-icon" src="../assets/lock.png" alt="lock">
          <p>Увійти</p>
        </button>

        <div class="wrapper-icon email">
          <div class="count-wrap-ico">{{emailCount}}</div>
          <img class="ico-img-header" src="../assets/email-mb.png" alt="email-mb">
        </div>

        <div class="wrapper-icon notifications">
          <div class="count-wrap-ico">{{emailNotifications}}</div>
          <img class="ico-img-header" src="../assets/notifications-mb.png" alt="notifications-mb">
        </div>

        <img class="cabinet-mb-img" src="../assets/img/doctor-3.png" alt="cabinet-mb-img">

        <button class="button-menu">
          <p style="text-transform: uppercase">МЕНЮ</p>
          <img class="menu-icon" src="../assets/menu.png" alt="menu">
        </button>

      </nav>

    </header>
  </div>
</template>

<script>

import {ref, onMounted} from "vue";

export default {
  name: 'CustomHeader',

  setup() {

    const mobile = ref(false)
    const emailCount = ref(12)
    const emailNotifications = ref(126)

    // on mounted component in DOM-tree check whether device is mobile and change placeholder in input if positive
    onMounted(()=>{
      if(window.screen.width > 700) {
        mobile.value = true;
      }
      console.log("mobile? -", !mobile.value);
    })

    return {mobile, emailCount, emailNotifications}
  }
}
</script>

<style scoped>

#nav-custom {
  display: grid;
  grid-template-columns: repeat(3, auto);
  gap: 10px;
  align-items: center;
}

#site-search::placeholder {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  color: #16395b;
  font-weight: 700;
  opacity: 0.7;
}

p {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.button-login {
  color: #16395b;
  font-weight: 700;
  padding: 10px 30px;
  border: none;
  background-color: #ffffff;
  border-radius: 5px;
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 15px;
  align-items: center;
  -webkit-box-shadow: 6px 8px 10px -7px rgba(166,166,166,1);
  -moz-box-shadow: 6px 8px 10px -7px rgba(166,166,166,1);
  box-shadow: 6px 8px 10px -7px rgba(166,166,166,1);
}

.button-login:hover {
  -webkit-box-shadow: -1px 9px 48px -4px rgba(161,161,161,1);
  -moz-box-shadow: -1px 9px 48px -4px rgba(161,161,161,1);
  box-shadow: -1px 9px 48px -4px rgba(161,161,161,1);
  position: relative;
  top: 1px;
}

.button-menu {
  border: none;
  background-color: #f6f4fc;
  display: grid;
  grid-template-columns: repeat(2, auto);
  gap: 5px;
  align-items: center;
}

.button-menu p {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  color: #16395b;
  font-weight: 700;
}

#select {
  opacity: 1;
  color: #16395b;
  font-weight: 600;
  font-size: 16px;
  padding: 15px;
  border: none;
  background-color: #f6f4fc;
}

.input-container {
  cursor: pointer;
  position: relative;
}

.search-icon {
  background: #f6f4fc;
  position: absolute;
  right: 15px;
  top: 15px;
}

#site-search {
  width: 570px;
  padding: 15px;
  border-radius: 5px;
  border: 1px solid #6d86ad;
  background-color: #f6f4fc;
}

.logo-img {
  width: 110px;
}

.custom-header {
  background: #f6f4fc;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;
}

.header-wrapper {
  z-index: 999;
  max-width: 1200px;
  margin: 0 auto;
  background: #f6f4fc;
  padding: 20px 60px;
  display: grid;
  gap: 40px;
  grid-template-columns: repeat(3, auto);
  justify-content: space-between;
  align-items: center;
}

.cabinet-mb-img, .logo-sm, .wrapper-icon {
  display: none;
}

@media (max-width: 1265px) {
  #site-search {
    width: 400px;
  }
}

@media (max-width: 1080px) {
  #site-search {
    width: 300px;
  }
}

@media (max-width: 980px) {
  #site-search {
    width: 200px;
  }
}

@media (max-width: 880px) {
  #select {
    display: none;
  }
  #nav-custom {
    grid-template-columns: repeat(2, auto);
  }
  #site-search {
    width: 300px;
  }
}

@media (max-width: 810px) {
  .button-login {
    display: none;
  }
  #nav-custom {
    grid-template-columns: auto;
  }
}

@media (max-width: 700px) {
  .button-menu {
    display: grid;
    grid-template-columns: auto;
    gap: 0;
  }
  .button-menu p {
    display: none;
  }
  .cabinet-mb-img {
    display: unset;
    width: 60px;
    height: 60px;
    border-radius: 50%;
  }
  .header-wrapper {
    grid-template-columns: repeat(2, auto);
    gap: 20px;
  }
  .wrapper-icon {
    display: unset;
  }
  #nav-custom {
    grid-template-columns: repeat(4, auto);
    gap: 25px;
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
  }
  .input-container {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: 3;
  }
  #site-search {
    width: 100%;
  }
  .logo-img {
    display: none;
  }
  .logo-sm {
    display: unset;
  }
  .count-wrap-ico {
    position: absolute;
    top: -15px;
    left: 5px;
    font-size: 10px;
    color: #ffffff;
    border-radius: 15px;
    padding: 5px;
    background-color: #16395b;
  }
  .wrapper-icon:hover {
    cursor: pointer;
    position: relative;
    top: 1px;
  }
  .wrapper-icon:hover .count-wrap-ico {
    color: #16395b;
    background-color: #ffffff;
  }
  .wrapper-icon {
    position: relative;
  }
}

@media (max-width: 550px) {
  .header-wrapper {
    padding: 20px;
  }
}

</style>