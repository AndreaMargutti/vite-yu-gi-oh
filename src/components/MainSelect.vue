<!--Creo il componente-->
<script>
import axios from 'axios';

export default {
  data() {
    return {
      //Aggiunto URL dell'API riguardante gli archetipi
      archetypesApiUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
      //Creata la lista di archetipo "libera"
      archetypesList: [],
    }
  },
  
  methods: {
    getArchetypes(){
      axios.get(this.archetypesApiUrl)
        .then((response) => {
          // handle success
          console.log(response);
          this.archetypesList = response.data
          console.log(this.archetypesList)
          })
          .catch(function (error) {
            // handle error
            console.log(error);
          });
    }
  },

  created() {
    this.getArchetypes();
  }
}
</script>

<template>
  <section>
    <!--Creo la select con le options-->
    <select class="my-3">
      <option value="alien" selected>Alien</option>
      <option value="spell">Spell</option>
      <option value="trap">Trap</option>
      <option value="fusion">Fusion</option>
    </select>
  </section>
</template>

<style scoped>
</style>