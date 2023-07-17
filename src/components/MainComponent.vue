<script>

export default {
  components :{
  },

  data() {
    return {  }
  },
  methods: {},
  props : {
    cards : {
      type: Array,
      default: []
    }
  }
}
</script>

<template>
  <main>
    <div class="container">
    <div class="row">
    <div class="col" v-for="(card, i) in cards" :key="i">
        <img src="" alt="">
        <h2> {{ card.name }}</h2>
        <div> {{ card.archetype }}</div>
    </div>
  </div>
  </div>
  </main>
  
 
</template>

<style scoped lang="scss">
main {
  background-color: #D48F38;
  padding: 30px;
}
.row {
  display: flex;
  flex-wrap: wrap;
  background-color: white;
  .col {
    margin: 10px;
    width: calc((100% / 5) - 20px) ;
    background-color: #D48F38;
    text-align: center;

    h2 {
      color: white;
    }
  }
}

</style>