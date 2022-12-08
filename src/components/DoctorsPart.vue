<template>
  <div class="doctors-part">
    <h2 class="text-doctor">Лікарі</h2>

      <Carousel :items-to-show="doctors.length">
        <Slide v-for="doctor in doctors" :key="doctor">
          <DoctorCard :doctor="doctor" />
        </Slide>
        <template #addons>
          <Navigation />
          <Pagination />
        </template>
      </Carousel>

  </div>
</template>

<script>

import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';
import DoctorCard from "@/components/DoctorCard.vue";

export default {
  name: 'DoctorsPart',
  components: {Carousel, Slide, Pagination, Navigation, DoctorCard},
  setup() {

    const doctors = [
      {rate: 4.9, name: "Лозовий Юрій Володимирович"},
      {rate: 5.9, name: "Москаленко Дмитро  Миколайович"},
    ]

    return {doctors}
  }
}
</script>

<style scoped>

p {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.doctors-part {
  margin-top: -50px;
}

.text-doctor {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  color: #16395b;
  font-weight: 700;
  font-size: 22px;
}

</style>
