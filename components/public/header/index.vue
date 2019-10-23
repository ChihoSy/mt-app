<template>
  <div class="">
    <div class="topbar">
      <top-bar/>
    </div>
    <div class="searchbar">
      <search-bar/>
    </div>
  </div>
</template>

<script>
import topBar from './topbar.vue'
import searchBar from './searchbar.vue'
export default {
  components:{
    topBar,
    searchBar
  }
}
</script>

<style lang="scss" scoped>
  .searchbar{
    background-color: #fff;
  }
</style>
