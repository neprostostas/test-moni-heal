<template>
  <div class="custom-main">
    <div class="main-wrapper">
      <div class="content-wrapper">
        <TopPart />
        <DoctorsPart />
      </div>
    </div>
  </div>
</template>

<script>
import TopPart from "@/components/TopPart.vue";
import DoctorsPart from "@/components/DoctorsPart.vue";

export default {
  name: 'CustomMain',
  components: {TopPart, DoctorsPart},

  setup() {

    return {}
  }
}
</script>

<style scoped>

.custom-main {
  background: #f6f4fc;
}

.main-wrapper {
  max-width: 1200px;
  margin-top: 80px;
  margin-left: auto;
  margin-right: auto;
  padding: 20px 100px;
}

</style>
