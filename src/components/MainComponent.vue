<script>
export default {
  components :{
  },

  data() {
    return { 
     }
  },
  methods: {},
  props : {
    cards : {
      type: Array,
      default: [],
    },
    cardsNumber : {
      type: Number,
      default : 0,
    }
  }
}
</script>

<template>
  <main>
    <form action=""  @submit.prevent ="$emit('search')">
      <select name="Select Archetype" id="" placeholder="Select Archetype">
        <option value="">Select Archetype</option>
        <option value="alien">Alien</option>
        <option value="unchained">Unchained</option>
        <option value="nobleKnight">Noble Knight</option>
      </select>
    </form>
    <div class="container">
      <div class="cardsNumber"> Found {{ cardsNumber }} cards</div>
    <div class="row">
    <div class="col" v-for="(card, i) in cards" :key="i">
        <img :src="card.card_images[0].image_url" alt="">
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
.cardsNumber {
  background-color: black;
  color: white;
  padding: 10px;
  height: 50px;
}
.row {
  display: flex;
  flex-wrap: wrap;
  background-color: white;
  margin: 0 auto;
  .col {
    margin: 10px;
    width: calc((100% / 5) - 20px) ;
    background-color: #D48F38;
    text-align: center;

    h2 {
      color: white;
      text-transform: uppercase;
    }
    img {
      width: 100%;
    }
  }
}

</style>