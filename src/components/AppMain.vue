<script>
// Importo i componenti necessari
import MainCardsList from './MainCardsList.vue';
import MainSelect from './MainSelect.vue';

export default {
  data() {
    return {
      
    }
  },
  //Importo i componenti necessari pt.2
  components: {
    MainSelect,
    MainCardsList
  }
}
</script>

<template>
  <!--Inserisco i due componenti all'interno di un container-->
    <main class="container">
        <MainSelect />
        <MainCardsList />
    </main>
</template>

<style scoped>
</style>