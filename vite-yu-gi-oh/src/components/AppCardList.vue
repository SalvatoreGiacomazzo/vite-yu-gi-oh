<script>
import AppCardListItem from "./AppCardListItem.vue";
import axios from "axios";

export default {
  components: {
    AppCardListItem
  },
  data() {
    return {
        cardList: [],
        apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=16"
    }
  }, methods:{
    getCardList() {
      axios.get(this.apiUrl)
        .then((response) => {
          // cose da fare se la chiamata ha successo
         // this.card = response.data; // Salva i dati della carta
          console.log(response.data.data);
        })
        .catch((error) => {
          // error
          console.log(error);
        })
    }
  }, mounted(){
    this.getCardList();
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