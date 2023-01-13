<script>
// importo il component
import { store } from "./store.js";
import HeaderVue from './components/HeaderVue.vue';
import MainApp from './components/MainApp.vue';
import axios from 'axios';


// esporto il component
export default {
  components: {
    HeaderVue,
    MainApp,
  },

  data() {
    return {
      store,
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php',
      archetypeDefault: 'alien',
    }
  },

  //aggiungo le funzioni
  methods: {
    getCards(archetypeSelection) {
      axios.get(this.apiUrl, {
        params: {
          num: 20,
          offset: 0,
          archetype: archetypeSelection
        }
      })
        .then((response) => {
          console.log(response.data.data);
          this.store.cardsList = response.data.data;
          this.store.cardsNumber = this.store.cardsList.length;
          console.log(this.store.cardsNumber)
        })
        .catch(function (error) {
          console.log(error);
        });
    },
    // getSelection(params) {
    //   this.selection = params;
    //   console.log(params)
    // }
  },
  //aggiungo hook created per chiamare la funzione ad ogni caricamento della pagina
  created() {
    this.getCards(this.archetypeDefault);
  },


}

</script>

<template>
  <!-- aggiungo i components al template -->
  <HeaderVue />
  <MainApp @selection="getCards" />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables" as *;
</style>
