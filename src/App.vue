<template>
  <MainLayout>
    <Main/>
  </MainLayout>
</template>

<script>
import MainLayout from './components/MainLayout.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    MainLayout,
    Main
  },

  setup() {

    return {
      
    }
  }
}
</script>

<style>

/* overwriting carousel library code */
.carousel__slide {
  align-items: flex-start!important;
}

.carousel__prev, .carousel__next {
  position: relative!important;
}

.carousel__prev {
  width: 35px;
  height: 35px;
  background-color: #00d7a8;
  border-radius: 50%;

  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 2;
}

.carousel__prev svg, .carousel__next svg {
  fill: #ffffff;
  transform: scale(.8);
}

.carousel__pagination {
  grid-column-start: 2;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 2;
  margin-top: 0;
}

.carousel__next {
  width: 35px;
  height: 35px;
  background-color: #00d7a8;
  border-radius: 50%;

  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
}

.carousel__pagination-button::after {
  background-color: #00d7a8;
  width: 6px;
  height: 6px;
  border-radius: 15px;
}

.carousel__pagination-button--active::after {
  width: 15px;
  height: 6px;
  background-color: #0b8d72!important;
}
/* ==================================*/

@font-face {
  font-family: "AvenirNextCyr-Regular";
  src: local("AvenirNextCyr-Regular"),
  url("./../src/fonts/AvenirNextCyr-Regular.ttf") format("truetype");
}

@font-face {
  font-family: "AvenirNextCyr-Medium";
  src: local("AvenirNextCyr-Medium"),
  url("./../src/fonts/AvenirNextCyr-Medium.ttf") format("truetype");
}

html, body, * {
  font-family: "AvenirNextCyr-Regular", sans-serif;
}

body {
  background: #f6f4fc;
}

body, h1, h2, h3, h4, h5, p {
  margin: 0;
}

ul {
  list-style-type: none;
}

button {
  cursor: pointer;
}

*:focus {
  outline: none!important;
}

img {
  -webkit-user-drag: none;
  -khtml-user-drag: none;
  -moz-user-drag: none;
  -o-user-drag: none;
  user-drag: none;
}

</style>
