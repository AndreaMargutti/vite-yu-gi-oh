<script>
export default {
  data() {
    return {
      
    }
  },
  
  props: {
    cardObj : {
      type: Object,
      required: true
    }
  },
}
</script>

<template>
  <div class="card">
  <img :src="cardObj.card_images[0].image_url" class="card-img-top" alt="...">
  <div class="card-body">
    <p class="card-text">
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