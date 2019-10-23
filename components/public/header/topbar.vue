<template>
  <div class="m-topbar">
    <div class="m-topbar-leftbar">
      <geo />
      <user />
    </div>
    <div class="m-topbar-nav">
      <navbar />
    </div>
  </div>
</template>

<script>
import Geo from './geo.vue'
import User from './user.vue'
import Navbar from './nav.vue'
export default {
  components: {
    Geo,
    User,
    Navbar
  }
}
</script>

<style lang="scss" scoped>
.m-topbar {
  height: 40px;
  width: 1190px;
  margin: 0 auto;
}
.m-topbar-leftbar {
  height: 40px;
  float: left;
  display: flex;
  align-items: center;
}
.m-topbar-nav {
  height: 40px;
  float: right;
}
</style>
