<template>
  <div class="search-panel">
    <div class="header-title">
      <nuxt-link to="/">
        <img src="../../../assets/img/logo.png" alt="美团logo" />
      </nuxt-link>
    </div>
    <div class="search-module">
      <div class="search-block">
        <input
          type="text"
          class="search-input"
          placeholder="搜索商家或地点"
          v-model="searchText"
          @focus="myFocus"
          @blur="myBlur"
          @input="myInput"
        />
        <button class="search-btn" @click="postSearch">
          <!-- <button class="search-btn"> -->
          <i class="iconfont icon-fangdajing"></i>
        </button>
      </div>
      <div class="search-suggest" v-if="isFocus">
        <div class="search-noinput" v-if="isHotPlace">
          <div class="search-history" v-if="searchHistory.length!==0">
            <h6>最近搜索</h6>
            <span class="search-history-clean" @click="delSearchHistory">删除搜索历史</span>
            <ul class="search-history-ul">
              <li v-for="(item,idx) in searchHistory" :key="idx">
                <a href="#">{{item}}</a>
              </li>
            </ul>
          </div>
          <h6>热门搜索</h6>
          <ul class="search-hotword">
            <li v-for="(item,idx) in hotWord" :key="idx">
              <a :href="item[1]">{{item[0]}}</a>
            </li>
          </ul>
        </div>

        <div class="search-hasinput" v-if="isSearchList">
          <ul>
            <li v-for="(item,idx) in searchList" :key="idx">
              <a :href="item[1]">{{item[0]}}</a>
            </li>
          </ul>
        </div>
      </div>
      <ul class="search-hotword">
        <li v-for="(item,idx) in hotWord" :key="idx">
          <a :href="item[1]">{{item[0]}}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchText: '',
      isFocus: false,
      searchHistory: [],
      hotWord: [
        ['古北水镇', 'lianjie'],
        ['北京欢乐谷', 'lianjie'],
        ['八达岭长城', 'lianjie'],
        ['中国国家博物馆', 'lianjie'],
        ['北京动物园', 'lianjie'],
        ['圆明园', 'lianjie'],
        ['恭王府', 'lianjie'],
        ['国瑞百捷酒店', 'lianjie']
      ],
      searchList: [
        ['古北水镇', 'lianjie'],
        ['古北水镇一日游', 'lianjie'],
        ['古北水镇住宿', 'lianjie'],
        ['古北水镇', 'lianjie'],
        ['古北水镇一日游', 'lianjie'],
        ['古北水镇住宿', 'lianjie']
      ]
    }
  },
  methods: {
    myFocus() {
      this.isFocus = true
    },
    myBlur() {
      setTimeout(() => {
        this.isFocus = false
      }, 200)
    },
    myInput() {
      console.log('这是用来拿搜索数据的地方')
    },
    // 记载搜索记录
    loadSearchHistory() {
      var list = JSON.parse(localStorage.getItem('searchHistory') || '[]')
      this.searchHistory = list
    },
    // 提交搜索，写入搜索记录
    postSearch() {
      var list = JSON.parse(localStorage.getItem('searchHistory') || '[]')
      console.log(list)
      list.unshift(this.searchText)
      localStorage.setItem('searchHistory', JSON.stringify(list))
      this.loadSearchHistory()
    },
    // 删除搜索记录
    delSearchHistory() {
      localStorage.setItem('searchHistory', '[]')
      this.searchHistory = []
    }
  },
  mounted() {
    //从缓存中加载搜索记录
    this.loadSearchHistory()
  },
  computed: {
    // 是否是最近搜索和热门搜索页面，需要同时有focus以及输入框无内容
    isHotPlace() {
      return this.isFocus && !this.searchText
    },
    //否则就是输入联想界面
    isSearchList() {
      return this.isFocus && this.searchText
    }
  }
}
</script>
<style lang="scss" scoped>
.search-panel {
  position: relative;
  width: 1190px;
  margin: 0 auto;
  height: 157px;
  .header-title {
    float: left;
    margin-top: 28px;
    height: 46px;
    a {
      display: inline-block;
      height: 46px;
      img {
        width: 126px;
        height: 46px;
        border: 0;
      }
    }
  }
  .search-module {
    width: 550px;
    height: 90px;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    margin-top: 28px;
    .search-block {
      height: 40px;
      .search-input {
        width: 85%;
        border: 1px solid #e5e5e5;
        border-right: none;
        height: 100%;
        border-radius: 4px 0 0 4px;
        outline: none;
        padding: 15px;
        box-sizing: border-box;
        font-size: 14px;
      }

      .search-btn {
        width: 15%;
        box-sizing: border-box;
        height: 100%;
        float: right;
        background-color: #ffc300;
        outline: none;
        border: none;
        cursor: pointer;
        border-bottom-right-radius: 4px;
        border-top-right-radius: 4px;
        i {
          font-size: 22px;
        }
      }
    }
    .search-suggest {
      position: relative;
      width: 85%;
      box-sizing: border-box;
      background-color: #fff;
      border: 1px solid #e5e5e5;
      border-top: none;
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
      z-index: 999;

      .search-noinput {
        h6 {
          margin: 0;
          color: #999;
          font-weight: bold;
          // clear: both;
        }
        padding: 10px;
        .search-history {
          width: 100%;
          overflow: hidden;
          ul.search-history-ul {
            overflow: hidden;
            height: 19px;
            margin: 10px 0 10px;
            padding: 0 3px;
          }
        }
        .search-history-clean {
          position: absolute;
          top: 10px;
          right: 10px;
          cursor: pointer;
        }
        ul.search-hotword {
          height: 19px;
          box-sizing: border-box;
          overflow: hidden;
          margin: 10px 0 5px;
        }
      }
      .search-hasinput {
        ul {
          li {
            display: block;
            margin: 0;
            a {
              display: block;
              padding: 3px 10px;
              height: 20px;
              line-height: 20px;
              color: #333;

              overflow: hidden;
              text-overflow: ellipsis;
              white-space: nowrap;

              &:hover {
                background-color: #f8f8f8;
                color: #fe8c00;
              }
            }
          }
        }
      }
    }
    > ul.search-hotword {
      height: 19px;
      overflow: hidden;
      position: absolute;
      top: 48px;
      padding-left: 12px;
      a {
        color: #999;
      }
    }
    ul {
      list-style-type: none;
      padding: 0;
      margin: 0;
      li {
        display: inline-block;
        margin-right: 8px;
        a {
          display: inline-block;
          height: 19px;
          line-height: 19px;
          color: #666;
          &:hover {
            color: #fe8c00;
          }
        }
      }
    }
  }
}
//修改placeholder颜色
::-webkit-input-placeholder {
  /* WebKit browsers */
  color: #999;
}

::-moz-placeholder {
  /* Mozilla Firefox 19+ */
  color: #999;
}

:-ms-input-placeholder {
  /* Internet Explorer 10+ */
  color: #999;
}
</style>
