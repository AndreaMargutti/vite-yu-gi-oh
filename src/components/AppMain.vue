<script>
import MainCardsList from './MainCardsList.vue';
import MainSelect from './MainSelect.vue';

export default {
  data() {
    return {
      
    }
  },
  components: {
    MainSelect,
    MainCardsList
  }
}
</script>

<template>
    <main class="container">
        <MainSelect />
        <MainCardsList />
    </main>
</template>

<style scoped>
</style>