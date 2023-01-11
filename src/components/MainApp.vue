<script >
import axios from 'axios'

export default {
  name: 'MainApp',
  data() {
    return {
      cardsList: [],

    }
  },
  //aggiungo le funzioni
  methods: {
    getCards() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0', {
        params: {

        }
      })
        .then((response) => {
          console.log(response.data);
          this.cardsList = response.data;
        })
        .catch(function (error) {
          console.log(error);
        });
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
      <div class="cards" v-for="card in cardsList">
        {{ card }}
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
