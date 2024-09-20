<script>
import AppHeader from "./components/AppHeader.vue"
import AppCardList from "./components/AppCardList.vue"
import AppCardListItem from "./components/AppCardListItem.vue"
import AppSelect from "./components/AppSelect.vue"
import axios from "axios";

export default {
  components: {
    AppHeader,
    AppCardList,
    AppCardListItem,
    AppSelect
  },
  data() {
    return {
     selectedArchetypeList: [],
    
    }
  }, methods:{
    showInfo(archetype){
      console.log(`parent ${archetype}`)
      this.getCardArchetypeList(archetype)
    },
    getCardArchetypeList(archetype){
    const apiBigList = `https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${archetype}&num=1000&offset=0`;
      axios.get(apiBigList)
        .then((response) => {
          console.log(response.data.data);  
          this.selectedArchetypeList = response.data.data;
        })
        .catch((error) => {
          console.error(error); 
        });
    }
  }
}
</script>

<template>
<!--Header-->
<AppHeader />
  <!--Select-->
<AppSelect @archetype-search="showInfo" />
  <!--Card List-->
<AppCardList :cardList="selectedArchetypeList"/>

</template>


<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
