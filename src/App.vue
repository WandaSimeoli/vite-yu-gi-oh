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
      cards : []
     }
  },
  methods: {},
  created () {
    axios 
    .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0')
    .then (response => {
      console.log(response.data.data);
      this.cards = response.data.data;

    });
  }
};
</script>

<template>
  <HeaderComponent />
  <MainComponent 
  :cards = "cards"
  :cards-number="cards.length"/>
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
