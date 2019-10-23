<template>
  <div class="container">
    <div class="header">
      <my-header/>
    </div>
    <div class="main">
      <nuxt/>
      main
    </div>
    <div class="footer">
      footer
    </div>
  </div>
</template>

<script>
import MyHeader from '@/components/public/header/index.vue'
export default {
  components:{
    MyHeader
  }
}
</script>

<style lang="scss" scoped>
.header{
  // background-color: #f8f8f8;
  font-size: 12px;
  color: #999;
}
.container{
  background-color: #f8f8f8;
}
</style>
