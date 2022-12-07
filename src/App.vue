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
