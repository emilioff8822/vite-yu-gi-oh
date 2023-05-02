<script>
export default {
  props: ['card']
}
</script>

<template>
  <div class="card">
    <img :src="card.card_images[0].image_url" alt="Card Image">
    <div class="card-body">
      <h5 class="card-title">{{ card.name }}</h5>
      <p class="card-text">{{ card.type }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: 25%;
  text-align: center;
  margin-bottom: 20px;
  border: 1px solid black;
}
</style>
