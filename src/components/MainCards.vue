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
  }
}
</script>

<template>
  <div class="card w-100">
  <img :src="cardObj.card_images.image_url" class="card-img-top" alt="...">
  <div class="card-body">
    <p class="card-text">
      {{ cardObj.name }}
      {{ cardObj.archetype }}
    </p>
  </div>
</div>
</template>

<style scoped>
</style>