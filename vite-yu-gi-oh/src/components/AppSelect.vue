<script>


export default {
  data() {
    return {

    }
  }, 
  }

</script>

<template>
<div class="container d-flex align-items-center">
 <select class="form-select bg-primary" aria-label="Default select example">
    <option selected>Select an Archetype</option>
  <!--Aggiungere opzioni dinamicamente-->
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
 </select>
</div>

</template>

<style lang="scss">
.container{
    height:80px;
    
}

</style>