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
    return {  }
  },
  methods: {},
  created () {
    axios .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
    .then (response => {
      console.log(response);

    });
  }
};
</script>

<template>
  <HeaderComponent />
  <MainComponent />
  <FooterComponent />
</template>

<style lang="scss">
@use "assets/scss/main.scss" as *;
</style>
