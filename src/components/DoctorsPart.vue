<template>
  <div class="doctors-part">

    <div class="doctor-text-block">
      <h2 class="text-doctor">Лікарі</h2>
      <button class="text-all-doctor">ВСІ ЛІКАРІ</button>
    </div>

      <Carousel :breakpoints="breakpoints.breakpoints" :itemsToScroll="1">
        <Slide v-for="doctor in doctors" :key="doctor">
          <DoctorCard :doctor="doctor" />
        </Slide>
        <template #addons>
          <div class="nav-pag-custom">
            <Navigation />
            <Pagination />
          </div>
        </template>
      </Carousel>

  </div>
</template>

<script>

import {ref} from "vue";
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';
import DoctorCard from "@/components/DoctorCard.vue";
import {doctors} from "@/storage/doctors";

export default {
  name: 'DoctorsPart',
  components: {Carousel, Slide, Pagination, Navigation, DoctorCard},
  setup() {

    const breakpoints = ref({
      breakpoints: {
        // 100px and up
        100: {
          itemsToShow: 1,
        },
        // 700px and up
        700: {
          itemsToShow: 2,
        },
        // 1024 and up
        1024: {
          itemsToShow: 3,
        },
        // 1250px and up
        1250: {
          itemsToShow: 4,
        },
      },
    })

    return {doctors, breakpoints}
  }
}
</script>

<style scoped>

.nav-pag-custom {
  display: grid;
  grid-template-columns: repeat(3, auto);
  justify-items: center;
  align-items: center;
}

p {
  font-family: "AvenirNextCyr-Medium", sans-serif!important;
}

.text-all-doctor {
  font-family: "AvenirNextCyr-Medium", sans-serif;
  font-weight: 700;
  color: #00d7a8;
  font-size: 12px;
  border: none;
  background-color: transparent;
}

.text-all-doctor:hover {
  text-decoration: underline;
}

.doctor-text-block {
  display: grid;
  grid-template-columns: repeat(2, auto);
  align-items: center;
  justify-content: space-between;
  padding: 0 20px 20px 20px;
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
