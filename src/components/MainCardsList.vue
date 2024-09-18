<script>
import MainCards from './MainCards.vue';
import axios from 'axios';

export default {
  components: {
    MainCards
  },

  data() {
    return {
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
    }
  },

  methods:{
    getCards(){
      // Make a request for a user with a given ID
      axios.get(this.apiUrl)
        .then((response) => {
          // handle success
          console.log(response);
        })
        .catch((error) => {
          // handle error
          console.log(error);
        })
    } 
  },

  created(){
    this.getCards();
  }
  }

</script>

<template>
  <section class="row">
      <div id="card-counter" class="mb-3">
        <span class="fw-bold d-inline align-middle">Ho trovato 40 carte</span>
      </div>
      <div class="col-3">
        <MainCards />
      </div>
    </section>
</template>

<style lang="scss" scoped>
  section {
    background-color: white;
    padding: 2rem;
      #card-counter {
        background-color: #212429;
        min-height: 30px;
          span {
            color: white;
          }
      }
  }
</style>