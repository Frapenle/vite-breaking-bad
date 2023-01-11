<script>
// importo il component
import MainApp from './components/MainApp.vue'

// esporto il component
export default {
  components: {
    MainApp
  }
}
</script>

<template>
  <!-- aggiungo il component al template -->
  <MainApp />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
