<template>
  <div class="custom-footer">
    <footer class="footer-wrapper">

    footer

    </footer>
  </div>
</template>

<script>

export default {
  name: 'CustomFooter',

  setup() {

    return { }
  }
}
</script>

<style scoped>

.custom-footer {
  background: #f6f4fc;
}

.footer-wrapper {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px 60px;
  display: grid;
  grid-template-columns: repeat(3, auto);
  justify-items: center;
  align-items: center;
  justify-content: space-between;
}

</style>
