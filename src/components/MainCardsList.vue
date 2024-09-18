<script>
import MainCards from './MainCards.vue';
import MainLoader from './MainLoader.vue';
import axios from 'axios';
import { store } from "../store.js"

export default {
  components: {
    MainLoader,  
    MainCards
  },

  data() {
    return {
      cardsList: [],
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
      store,
    }
  },

  methods:{
    getCards(){
      // Make a request for a user with a given ID
      axios.get(this.apiUrl)
        .then((response) => {
          // handle success
          console.log(response.data.data);
          store.cardsList = response.data.data
        })
        .catch((error) => {
          // handle error
          console.log(error);
        })
    } 
  },

  created(){
    setTimeout(this.getCards, 1000);
  }
  }

</script>

<template>
  <section class="row">
      <div id="card-counter" class="mb-3">
        <span class="fw-bold d-inline align-middle">Ho trovato {{ store.cardsList.length }} </span>
      </div>
      <MainLoader v-if="store.cardsList.length === 0" />
      <div class="col-3 mb-2 d-flex" v-for="cardItem in store.cardsList" :key="cardItem.id" v-else>
        <MainCards :cardObj="cardItem"/>
      </div>
    </section>
</template>

<style lang="scss" scoped>
  section {
    background-color: white;
    padding: 2rem;
    position: relative;
      #card-counter {
        background-color: #212429;
        min-height: 30px;
          span {
            color: white;
          }
      }
  }
</style>