<script >
import axios from 'axios';
import CardApp from './CardApp.vue';

export default {
  name: 'MainApp',
  props: ['selection'],
  components: {
    CardApp,
  },
  data() {
    return {
      cardsList: [],
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
      cardsNumber: 0,
      // archetypes: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
    }
  },
  //aggiungo le funzioni
  methods: {
    getCards() {
      axios.get(this.apiUrl, {
        params: {
          num: 20,
          offset: 0,
          archetype: this.selection
        }
      })
        .then((response) => {
          console.log(response.data);
          this.cardsList = response.data.data;
          this.cardsNumber = this.cardsList.length;
          console.log(this.cardsNumber)
        })
        .catch(function (error) {
          console.log(error);
        });
    }
  },
  //aggiungo hook created per chiamare la funzione ad ogni caricamento della pagina
  computed: {
    getCards()
  }
}
</script>

<template>
  <main>
    <h2 class="cards-number">Found {{ cardsNumber }} cards</h2>
    <div class="card-container">
      <div class="cards">
        <CardApp v-for="card in cardsList" :title="card.name" :imgUrl="card.card_images[0].image_url"
          :archetype="card.archetype" />
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
@use '../styles/general.scss' as *;

main {
  padding: 2rem;
  background-color: $main-bg;
}

.cards-number {
  margin: 1rem;
}

.card-container {
  margin: 1rem;
  background-color: white;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  width: 100%;
  padding: 1rem 2rem;
}
</style>
