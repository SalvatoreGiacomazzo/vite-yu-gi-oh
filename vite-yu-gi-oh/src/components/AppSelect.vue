<script>
import axios from "axios";

export default {
  data() {
    return {
     archList: [],
     archUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php"
    }
  }, methods:{
  getArchList(){
    axios.get(this.archUrl)
        .then((response) => {
          // cose da fare se la chiamata ha successo
          console.log(response);
          this.archList = response.data.map((archetype) => archetype.archetype_name )
         
        })
        .catch((error) => {
          // gestisci l'errore
          console.log(error);
        });
  },
  logMessage(message){
    const selectedArchetype = event.target.value; 
      console.log(`figlio ${selectedArchetype}`);
      this.$emit("archetype-search", selectedArchetype);
  }
  },
   mounted(){
      this.getArchList();
     }
  }

</script>

<template>
<div class="container d-flex align-items-center">
 <select class="form-select bg-primary" aria-label="Default select example"  @change="logMessage(selectedItem)">
    <option selected>Select an Archetype</option>
  <!--Aggiungere opzioni dinamicamente-->
  <option v-for="archetype in archList" :key="archetype" :value="archetype">{{ archetype }}</option>
  
 </select>
</div>

</template>

<style lang="scss">
.container{
    height:80px;
    
}

</style>