<script>
// importo il component
import HeaderVue from './components/HeaderVue.vue';
import MainApp from './components/MainApp.vue'

// esporto il component
export default {
  components: {
    HeaderVue,
    MainApp,
  },
  data() {
    return {
      selection: '',
    }
  },
  methods: {
    getSelection(params) {
      this.selection = params;
    }
  },
}

</script>

<template>
  <!-- aggiungo i components al template -->
  <HeaderVue @selection="getSelection" />
  <MainApp :selection="selection" />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
