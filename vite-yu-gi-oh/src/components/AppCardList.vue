<script>
import AppCardListItem from "./AppCardListItem.vue";
import AppSelect from "./AppSelect.vue"
import axios from "axios";

export default {
  components: {
    AppCardListItem,
    AppSelect
  },
  data() {
    return {
      cardList: [], 
      apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=16"
    };
  },
  methods: {
    getCardList() {
      axios.get(this.apiUrl)
        .then((response) => {
          // cose da fare se la chiamata ha successo
          console.log(response.data.data);
          this.cardList = response.data.data; 
        })
        .catch((error) => {
          // gestisci l'errore
          console.log(error);
        });
    },
    archName(){
        
    }
  },
  mounted() {
    this.getCardList();
  }
}
</script>
<template>
<!--Selettore di archetipi-->

<div class="container">
 <div class="row h-100 g-4"> 
 
    <AppCardListItem v-for="cardItem in cardList" 
    :key="cardItem.index"
    :cardObject="cardItem"
    :v-bind="cardItem"/>
    
 </div>
</div>


</template>

<style lang="scss"></style>