<script>
export default {
  data() {
    return {
      
    }
  },

  //Rendo disponibili le props create in "MainCardsList.vue"
  props: {
    cardObj : {
      //Specifico il tipo del props
      type: Object,
      //Specifico se è richiesta
      required: true
    }
  },
}
</script>

<template>
  <!--Creo la singola card-->
  <div class="card">
  <!--Do l'indirizzo in maniera dinamica recuperandolo dall'oggetto ricevuto dall'API-->
  <img :src="cardObj.card_images[0].image_url" class="card-img-top" alt="...">
  <div class="card-body">
    <p class="card-text">
      <!--Inseriso nome e archetipo della carta recuperandoli dall'oggetto ricevuto dall'API-->
      <span>{{ cardObj.name }}</span> <br>
      <span>{{ cardObj.archetype }}</span>
    </p>
  </div>
</div>
</template>

<style lang="scss" scoped>
  .card-body {
    background-color: #d38e3a;
    span:first-child {
      color: white;
    }
  }
</style>