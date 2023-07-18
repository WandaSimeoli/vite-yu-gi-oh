<script>
// my-component.js
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import axios from 'axios';

export default {
  components :{
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },

  data() {
    return { 
      cards : [],
      searchArchetype : ""
     }
     
  },
  methods: {
    getResults () {
       axios 
    .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0', {
      params: {
        archetype: this.searchArchetype || null
      }
    })
    .then (response => {
      console.log(response.data.data);
      this.cards = response.data.data;

    });
    },
    performSearch () {
      console.log ('intercettato evento');
      this.getResults;
    }
  },
  created () {
    this.getResults();
  }
};
</script>

<template>
  <HeaderComponent />
  <MainComponent 
  :cards = "cards"
  :cards-number="cards.length"
  @search ="getResults"/>
  <FooterComponent />
</template>

<style lang="scss">
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box; 
  font-family: 'Roboto', sans-serif;
}

.container {
    margin: 0 auto;
    max-width: 1200px;
}
</style>
