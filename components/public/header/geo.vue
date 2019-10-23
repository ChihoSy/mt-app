<template>
  <div class="m-geo">
    <i class="iconfont icon-zuobiao">
      <span class="current-city">北京</span>
    </i>
    <nuxt-link to="/changeCity" class="change-city">切换城市</nuxt-link>
    <!-- <span>[门头沟区 大厂回族自治县 廊坊]</span> -->
    <div class="near-citys">[门头沟区 大厂回族自治县 廊坊]</div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.m-geo {
  float: left;
  i.icon-zuobiao {
    font-size: 12px;
  }
  span.current-city {
    color: #666;
  }
  .change-city {
    color: #666;
    background-color: #f4f4f4;
    border: 1px solid #e5e5e5;
    border-radius: 2px;
    padding: 1.5px 2px 0;
    margin: 0 2px;
  }
  .near-citys {
    display: inline-block;
  }
  a:hover {
    color: #fe8c00;
  }
}
</style>