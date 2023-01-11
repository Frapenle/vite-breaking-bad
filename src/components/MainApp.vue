<script >
import axios from 'axios';
import CardApp from './CardApp.vue';

export default {
  name: 'MainApp',
  components: {
    CardApp,
  },
  data() {
    return {
      cardsList: [],
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0'
    }
  },
  //aggiungo le funzioni
  methods: {
    getCards() {
      axios.get(this.apiUrl, {
        params: {

        }
      })
        .then((response) => {
          console.log(response.data);
          this.cardsList = response.data.data;
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
      <div class="cards">
        <CardApp v-for="card in cardsList" :title="card.name" :imgurl="card.card_images[0].image_url" />
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  padding: 0 1rem;
}
</style>
