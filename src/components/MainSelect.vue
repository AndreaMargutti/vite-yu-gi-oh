<!--Creo il componente-->
<script>
//Importato axios
import axios from 'axios';
import MainCardsList from './MainCardsList.vue';

export default {
  components: {
    MainCardsList
  },
  data() {
    return {
      //Aggiunto URL dell'API riguardante gli archetipi
      archetypesApiUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
      //Creata la lista di archetipo "libera"
      archetypesList: [],
      selectedArchetype: "",
    }
  },
  
  methods: {
    //Funzione per chiamare l'API
    getArchetypes(){
      axios.get(this.archetypesApiUrl)
        .then((response) => {
          // handle success
          console.log(response);
          this.archetypesList = response.data // Aggiungi gli archetipi all'array precedentemente creato
          console.log(this.archetypesList) //Loggami l'array aggiornato
          })
          .catch(function (error) {
            // handle error
            console.log(error);
          });
    },
  },

  mounted() {
    this.getArchetypes()
  },

  updated(){
    console.log(this.selectedArchetype) // Il valore della variabile viene aggiornata (guarda in console)
  }
  
}
</script>

<template>
  <section>
    <!--Creo la select con le options-->
    <select class="my-3" v-model="selectedArchetype">
      <!--Aggiunto opzione "titolo"-->
      <option value="" disabled selected>Select Archetypes</option>
      <!--Generate opzioni tanti quanti gli archetipi presenti nell'array ricavato dall'API-->
      <option :value="archetype.archetype_name" v-for="(archetype, index) in this.archetypesList" :key="index"> 
        {{ archetype.archetype_name }}
      </option>
    </select>
  </section>
  <section>
    <MainCardsList/>
  </section>
</template>

<style scoped>
</style>