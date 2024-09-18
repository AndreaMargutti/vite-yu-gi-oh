<script>
import MainCards from './MainCards.vue';

export default {
  data() {
    return {
      
    }
  },
  components: {
    MainCards
  }
}
</script>

<template>
    <section class="row">
      <div id="card-counter">
        <span class="fw-bold d-inline align-middle">Ho trovato 40 carte</span>
      </div>
      <MainCards />
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