<script>
export default {
  data() {
    return {

    }
  }, props:{
    cardObject:{
    type: Object,
    required: true
    }
  }
}
</script>

<template>

<div class="card bg-dark" style="width: 16rem;">
    <h4 class="card-title text-warning text center">{{cardObject.name}}</h4>
  <img class="card-img-top" :src="cardObject.card_images[0].image_url_cropped" alt="">
  <div class="card-body bg-dark">
    <h5 class="card-title text-warning text center">{{ cardObject.type }}</h5>
    <p class="card-tite text center">{{ cardObject.archetype }}</p>
  </div>
</div>


</template>

<style lang="scss">

p{
    font-size:14px;
    color:brown;
}
</style>