<script>
//Importo i componenti necessari pt.1
import MainLoader from './MainLoader.vue';
import MainCards from './MainCards.vue';
//Importo Axios
import axios from 'axios';
//Importo la store dal file store.js
import { store } from "../store.js"

export default {
  //Importo i componenti necessari pt.2
  components: {
    MainLoader,  
    MainCards
  },

  props: {
    selectedValue: {
      type: String,
      require: false
    }
  },

  data() {
    return {
      //Creo array vuoto per l'array di oggetti contente le info delle carte
      cardsList: [],
      //Creo variabile per url dell'API
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
      //Inserisco la store nei data per poterla utilizzare all'interno di "MainCardsList.vue"
      store,
    }
  },

  methods:{
    //Creo la chiamata API
    getCards(){
      // Make a request for a user with a given ID
      axios.get(this.apiUrl)
        .then((response) => {
          // handle success
          console.log(response.data.data);
          //Inserisco l'array di oggetti ricevuto nella lista delle carte presente nel file store
          store.cardsList = response.data.data
        })
        .catch((error) => {
          // handle error
          console.log(error);
        })
    } 
  },

  //Una volta creata la pagina...
  created(){
    //..imposto un timer di due secondi...
    setTimeout(
      this.getCards(),
      1000); //..eseguo il metodo che chiama l'API
  }
  }

</script>

<template>
  <!--Creo il layout con bootstrap-->
  <section class="row">
    <!--Creo la card-->
      <div id="card-counter" class="mb-3">
        <!--Inserisco il numero di carte trovato in maniera dinamica-->
        <span class="fw-bold d-inline align-middle">Ho trovato {{ store.cardsList.length }} </span>
      </div>
      <!--Inserisco il loader solo finchè la chiamata non mi risponde-->
      <MainLoader v-if="store.cardsList.length === 0" />
      <!--Creo tante card quanti gli elementi in cards.list-->
      <div class="col-3 mb-2 d-flex" v-for="cardItem in store.cardsList" :key="cardItem.id" v-else>
        <!--Inserisco nella singola carta un singolo oggetto-->
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