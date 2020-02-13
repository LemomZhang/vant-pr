<template>
  <div class="home">
    <div class="head-search-bar flex">
      <div class="fh-logo"></div>
      <van-search v-model="value"
                  shape="round"
                  placeholder="请输入搜索关键词"
                  input-align="center" />
    </div>
    <van-swipe class="my-swipe"
               :autoplay="3000"
               indicator-color="white">
      <van-swipe-item>
        <van-image width="100%"
                   height="100%"
                   src="http://img.fhyx.com/uploads/2020/02/10/2020021075242868.jpg" />
      </van-swipe-item>
      <van-swipe-item>
        <van-image width="100%"
                   height="100%"
                   src="http://img.fhyx.com/uploads/2020/01/16/2020011693120394.jpg" />
      </van-swipe-item>
      <van-swipe-item>
        <van-image width="100%"
                   height="100%"
                   src="http://img.fhyx.com/uploads/2020/01/15/2020011552203456.jpg" />
      </van-swipe-item>
      <van-swipe-item>
        <van-image width="100%"
                   height="100%"
                   src="http:////img.fhyx.com/uploads/2020/01/10/20200110112218564.jpg" />
      </van-swipe-item>
    </van-swipe>

    <div class="head-img-link flex">
      <div class="max-img">
        <img src="http://img.fhyx.com/uploads/2020/02/10/2020021025216579.jpg"
             alt="">
      </div>
      <div class="small-img">
        <img src="http://img.fhyx.com/uploads/2020/01/21/2020012145620545.jpg"
             alt="">
        <img src="http://img.fhyx.com/uploads/2020/01/10/20200110100900816.png"
             alt="">
      </div>
    </div>
    <!-- 小游推荐 -->
    <Recom />
    <Hotgame />
    <div style="margin-top:6rem"></div>
    <Tabbar />
  </div>
</template>

<script>
// @ is an alias to /src
import Recom from '@/components/Recom.vue';
import Tabbar from '@/components/Tabbar.vue';
import Hotgame from '@/components/Hotgame.vue';
export default {
  name: 'Home',
  data() {
    return {
      value: ''
    };
  },
  components: { Recom, Tabbar, Hotgame }
};
</script>
<style lang="scss">
@import url(../assets/common.scss);
.home {
  .head-search-bar {
    align-items: center;
    > .van-search {
      flex: 1;
    }
  }
  .fh-logo {
    width: 2rem;
    height: 2rem;
    background: url(../assets/logo.jpg);
    background-size: 100% 100%;
    border-radius: 50%;
    margin-left: 10px;
  }
  .head-img-link {
    padding: 10px;
    .max-img {
      img {
        width: 12rem;
      }
    }
    .small-img {
      img {
        width: 100%;
      }
    }
  }
}
</style>