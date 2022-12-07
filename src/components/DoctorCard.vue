<template>
  <div class="doctor-card">

    Doctor: {{doctor.rate}}
    <p>{{doctor.name}}</p>

  </div>
</template>

<script>

export default {
  name: 'DoctorCard',
  components: {},

  props: {
    doctor: {
      rate: Number,
      name: String
    }
  },

  setup() {

    return {}
  }
}
</script>

<style scoped>

</style>
