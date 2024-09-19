<script>
import AppHeader from "./components/AppHeader.vue"
import AppCardList from "./components/AppCardList.vue"
import AppCardListItem from "./components/AppCardListItem.vue"
import AppSelect from "./components/AppSelect.vue"

export default {
  components: {
    AppHeader,
    AppCardList,
    AppCardListItem,
    AppSelect
  },
  data() {
    return {

    }
  }
}
</script>

<template>
<!--Header-->
<AppHeader />
<!--Select-->
  <AppSelect />
  <!--Card List-->
<AppCardList />

</template>


<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
