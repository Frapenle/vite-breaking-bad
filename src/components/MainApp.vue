<script >
import axios from 'axios'

export default {
  name: 'MainApp',
  data() {
    return {

    }
  },
  //aggiungo le funzioni
  methods: {
    getCards() {

    }
  },
  //aggiungo hook created per chiamare la funzione ad ogni caricamento della pagina
  created() {
    this.getCards();
  }
}
</script>

<template>
  <main>
    <div class="card-container">
      <div class="cards">
        <card />
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  padding: 0 1rem;
}
</style>
