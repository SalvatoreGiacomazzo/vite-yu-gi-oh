<script>
import AppHeader from "./components/AppHeader.vue"
import AppCardList from "./components/AppCardList.vue"
import AppCardListItem from "./components/AppCardListItem.vue"

export default {
  components: {
    AppHeader,
    AppCardList,
    AppCardListItem
  },
  data() {
    return {

    }
  }
}
</script>

<template>

  <AppHeader />
<AppCardList />

</template>


<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
