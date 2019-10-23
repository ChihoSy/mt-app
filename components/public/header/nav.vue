<template>
  <!-- <div class="m-nav"> -->
  <ul class="nav-first">
    <li class="has-child">
      <nuxt-link to="/my">我的美团</nuxt-link>
      <ul class="nav-second">
        <li>
          <nuxt-link to="order">我的订单</nuxt-link>
        </li>
        <li>
          <nuxt-link to="order">我的收藏</nuxt-link>
        </li>
        <li>
          <nuxt-link to="order">抵用券</nuxt-link>
        </li>
        <li>
          <nuxt-link to="order">账户设置</nuxt-link>
        </li>
      </ul>
    </li>
    <li>
      <nuxt-link to="/mobileApp">手机APP</nuxt-link>
    </li>
    <li class="has-child">
      商家中心
      <ul class="nav-second firmCenter">
        <li>
          <nuxt-link to="firmCenter">登录商家中心</nuxt-link>
        </li>
        <li>
          <nuxt-link to="mtznsy">美团智能收银</nuxt-link>
        </li>
        <li>
          <nuxt-link to="coop">我想合作</nuxt-link>
        </li>
        <li>
          <nuxt-link to="kaidian">手机免费开店</nuxt-link>
        </li>
        <li>
          <nuxt-link to="zhaomu">餐饮代理商招募</nuxt-link>
        </li>
        <li>
          <nuxt-link to="kaipiao">商家申请开票</nuxt-link>
        </li>
        <li>
          <nuxt-link to="paidui">免费合作美团排队</nuxt-link>
        </li>
      </ul>
    </li>
    <li class="has-child">
      美团规则
      <ul class="nav-second">
        <li>
          <nuxt-link to="gzzx">规则中心</nuxt-link>
        </li>
        <li>
          <nuxt-link to="gzml">规则目录</nuxt-link>
        </li>
        <li>
          <nuxt-link to="gzpyy">规则评议院</nuxt-link>
        </li>
      </ul>
    </li>
    <li class="has-child">
      网站导航
      <div class="subContainer">
        <dl class="hotel">
          <dt>酒店旅游</dt>
          <dd>
            <nuxt-link to="guojijipiao">国际机票</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="huochepiao">火车票</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="zhenguominsu">榛果民宿</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="jingjijiudian">经济型酒店</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="zhutijiudian">主题酒店</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="shangwujiudian">商务酒店</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="gongyu">公寓</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="haohuajiudian">豪华酒店</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="kezhan">客栈</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="qingnianlvshe">青年旅社</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="dujiajiudian">度假酒店</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="bieshu">别墅</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="nongjiayuan">农家院</nuxt-link>
          </dd>
        </dl>
        <dl class="food">
          <dt>吃美食</dt>
          <dd>
            <nuxt-link to="kaoyu">烤鱼</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="tesexiaochi">特色小吃</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="shaokao">烧烤</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="zizhucan">自助餐</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="huoguo">火锅</nuxt-link>
          </dd>
          <dd>
            <nuxt-link to="daijinquan">代金券</nuxt-link>
          </dd>
        </dl>
        <dl class="movie">
          <dt>看电影</dt>
          <dd>
            <a href>热映电影</a>
          </dd>
          <dd>
            <a href>热门电影</a>
          </dd>
          <dd>
            <a href>热映电影口碑榜</a>
          </dd>
          <dd>
            <a href>最受期待电影</a>
          </dd>
          <dd>
            <a href>国内票房榜</a>
          </dd>
          <dd>
            <a href>北美票房榜</a>
          </dd>
          <dd>
            <a href>电影排行榜</a>
          </dd>
        </dl>
        <dl class="mobileApp">
          <dt>手机应用</dt>
          <dd>
            <a href>
              <img src="../../../assets/img/meituan.png" alt="美团app" />
            </a>
          </dd>
          <dd>
            <a href>
              <img src="../../../assets/img/waimai.png" alt="美团外卖app" />
            </a>
          </dd>
          <dd>
            <a href>
              <img src="../../../assets/img/zhenguo.png" alt="榛果app" />
            </a>
          </dd>
          <dd>
            <a href>
              <img src="../../../assets/img/dianping.png" alt="点评app" />
            </a>
          </dd>
          <dd>
            <a href>
              <img src="../../../assets/img/maoyan.png" alt="猫眼app" />
            </a>
          </dd>
        </dl>
      </div>
    </li>
  </ul>

  <!-- <ul class="nav-first">
      <li v-for="(item,index1) in items" :key="index1" :class="{'has-child': item.hasChild}">
        <nuxt-link :to="item.linkTo" @click.prevent="">{{item.name}}</nuxt-link>
        <ul class="nav-second">
          <li v-for="(itemChild,index2) in item.children" :key="index2">
            <nuxt-link :to="itemChild.linkTo">{{itemChild.name}}</nuxt-link>
          </li>
        </ul>
      </li>
  </ul>-->
  <!-- </div> -->
</template>

<script>
export default {
  data() {
    return {
      // items: [
      //   {
      //     name: "我的美团",
      //     linkTo: "/my",
      //     hasChild: true,
      //     children: [
      //       { name: "我的订单", linkTo: "/orders" },
      //       { name: "我的收藏", linkTo: "/shoucang" },
      //       { name: "抵用券", linkTo: "/diyongquan" },
      //       { name: "账户设置", linkTo: "/account" }
      //     ]
      //   },
      //   { name: "手机APP", linkTo: "/mobile" },
      //   { name: "商家中心", linkTo: "", hasChild: true },
      //   { name: "美团规则", linkTo: "", hasChild: true },
      //   { name: "网站导航", linkTo: "", hasChild: true }
      // ]
    }
  }
}
</script>

<style lang="scss" scoped>
ul.nav-first {
  list-style-type: none;
  height: 40px;
  margin: 0;
  padding: 0;
  font-size: 0;
  li {
    font-size: 12px;
    display: inline-block;
    box-sizing: border-box;
    height: 40px;
    line-height: normal;
    a {
      color: #999;
      &:hover {
        color: #fe8c00;
      }
    }
  }
  > li {
    border-left: 1px solid transparent;
    border-right: 1px solid transparent;
    padding: 12px 14px;
  }
  > li.has-child {
    position: relative;
    z-index: 1001;
    &:hover {
      color: #fe8c00;
      background-color: #fff;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      border-color: #e5e5e5;
      > ul.nav-second {
        display: block;
      }
      > div.subContainer {
        display: block;
      }
    }
    > ul.nav-second {
      display: none;
      padding: 0;
      position: absolute;
      left: -1px;
      top: 95%;
      z-index: 1000;
      border: 1px solid #e5e5e5;
      border-top: 0;
      box-sizing: border-box;
      width: 78px;
      text-align: center;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
      background-color: #fff;
      > li {
        width: 100%;
        > a {
          display: inline-block;
          width: 100%;
          line-height: 40px;
        }
      }
    }
    > ul.firmCenter {
      width: 110px;
      left: -33px;
      border-top-left-radius: 4px;
      border-top: 1px solid #e5e5e5;
      &::before {
        content: '';
        display: block;
        background-color: #fff;
        height: 3px;
        width: 76px;
        position: absolute;
        top: -1px;
        right: 0;
      }
    }
    > div.subContainer {
      display: none;
      position: absolute;
      width: 1190px;
      right: -1px;
      top: 95%;
      padding: 30px 36px 36px 48px;
      box-sizing: border-box;
      border: 1px solid #e5e5e5;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
      border-top-left-radius: 4px;
      z-index: 1000;
      background-color: #fff;
      &:before {
        content: '';
        display: block;
        width: 76px;
        height: 3px;
        background-color: #fff;
        position: absolute;
        top: -2px;
        right: 0;
      }

      dl {
        float: left;
        margin: 0 47px 0 0;
        dt {
          font-size: 14px;
          color: #222;
          text-align: center;
          margin-bottom: 26px;
        }
        dd {
          float: left;
          margin: 0;
          text-align: center;
          a {
            display: inline-block;
            width: 100%;
            height: 26px;
            line-height: 26px;
          }
          img {
            width: 60px;
            height: 60px;
          }
        }
      }
      dl.hotel {
        width: 235px;
        dd {
          width: 33%;
        }
      }
      dl.food {
        width: 155px;
        dd {
          width: 50%;
        }
      }
      dl.movie {
        width: 100px;
        dd {
          width: 100%;
        }
      }
      dl.mobileApp {
        width: 380px;
        float: right;
        dd {
          width: 20%;
          a {
            width: 60px;
            height: 60px;
          }
        }
      }
    }
  }
}
</style>
