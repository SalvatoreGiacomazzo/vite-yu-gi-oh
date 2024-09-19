<script>
import AppCardListItem from "./AppCardListItem.vue";
import axios from "axios";

export default {
  components: {
    AppCardListItem
  },
  data() {
    return {
    }
  }, methods:{
    
  }

}



</script>

<template>

<div class="container">
 <div class="row h-100 g-4"> 
 
    <AppCardListItem v-for="index in 20" />

 </div>
</div>


</template>

<style lang="scss"></style>