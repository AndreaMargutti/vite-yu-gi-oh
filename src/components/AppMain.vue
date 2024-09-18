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
    <main>
        <h1>Main</h1>
        <MainSelect />
        <MainCardsList />
    </main>
</template>

<style scoped>
</style>