<script >

import { store } from '../store.js';
import CardApp from './CardApp.vue';

export default {
  name: 'MainApp',
  components: {
    CardApp,
  },
  data() {
    return {
      store,
      archetypes: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
      archetypeSelected: 'alien',
    }
  },
}
</script>

<template>
  <main>
    <h2 class="cards-number">Found {{ store.cardsNumber }} cards</h2>
    <select v-model="archetypeSelected" id="archetypes" @change="$emit('selection', archetypeSelected)">
      <option :value="item.toLowerCase()" v-for="item in archetypes">{{ item }}</option>
    </select>
    <div class="card-container">
      <div class="cards">
        <CardApp v-for="card in store.cardsList" :title="card.name" :imgUrl="card.card_images[0].image_url"
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
