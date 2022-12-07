<template>
  <div class="custom-header">
    <header class="header-wrapper">

      <div class="logo-wrapper">
        <img class="logo-img" src="../assets/logo-bg.png" alt="logo-bg">
      </div>

      <div class="input-container">
        <input type="search" id="site-search" placeholder="Знайти фахівця">
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

        <button class="button-menu">
          <p style="text-transform: uppercase">МЕНЮ</p>
          <img class="menu-icon" src="../assets/menu.png" alt="menu">
        </button>

      </nav>

    </header>
  </div>
</template>

<script>

export default {
  name: 'CustomHeader',

  setup() {

    return { }
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

</style>