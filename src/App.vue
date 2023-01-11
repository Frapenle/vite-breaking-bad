<script>
// importo il component
import HeaderVue from './components/HeaderVue.vue';
import MainApp from './components/MainApp.vue'

// esporto il component
export default {
  components: {
    HeaderVue,
    MainApp,
  }
}
</script>

<template>
  <!-- aggiungo i components al template -->
  <HeaderVue />
  <MainApp />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
