<script>
import AppCardListItem from "./AppCardListItem.vue"


export default {
  components: {
  
    AppCardListItem
  },
  data() {
    return {

    }
  }
}



</script>

<template>

<div class="container mt-4 px-4">
 <div class="row h-100 g-4"> 
 
    <AppCardListItem v-for="index in 20" />

 </div>
</div>


</template>

<style lang="scss"></style>