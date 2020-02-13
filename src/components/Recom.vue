<template>
  <div>
    <div class="part-title flex">
      <span>小游推荐</span>
      <a href="#">更多</a>
    </div>
    <div class="container flex">
      <van-card tag="标签"
                price="2.00"
                desc="Azur Lane: Crosswave"
                title="碧藍航線CrossWave"
                thumb="http://img.fhyx.com/uploads/p/2020/02/07/20200207101548916.jpg"
                origin-price="10.00" />
      <van-card tag="标签"
                price="2.00"
                desc="Panzer Corps 2"
                title="裝甲軍團2"
                thumb="http://img.fhyx.com/uploads/p/2020/02/09/20200209134522170.jpg"
                origin-price="10.00" />
      <van-card tag="标签"
                price="2.00"
                desc="One Piece: Pirate Warriors 4"
                title="海賊王無雙4"
                thumb="http://img.fhyx.com/uploads/p/2020/02/03/20200203120916469.jpg"
                origin-price="10.00" />
      <van-card tag="标签"
                price="2.00"
                desc="DRAGON BALL Z KAKAROT"
                title="龍珠Z：卡卡羅特"
                thumb="http://img.fhyx.com/uploads/p/2019/10/06/20191006175731648.jpg"
                origin-price="10.00" />
    </div>
    <div>
      <img style="width: 100%;padding:10px;"
           src="http://img.fhyx.com/uploads/2019/06/24/2019062462147269.png?11"
           alt="">
    </div>
    <!-- 值得买 -->
    <div class="part-title flex">
      <span>值得买</span>
    </div>
    <div class="worth-buy-container">
      <van-swipe class="my-swipe"
                 indicator-color="#fe653b">
        <van-swipe-item>
          <van-grid :border="true"
                    :column-num="2"
                    :gutter="10">
            <van-grid-item v-for="(item, index) in gameLists"
                           :key="index"
                           text="13">

              <van-image :src="item.imgUrl" />
              <van-cell :value="item.title" />
              <van-cell :value="item.price" />
            </van-grid-item>
          </van-grid>
        </van-swipe-item>
        <van-swipe-item>
          <van-grid :border="true"
                    :column-num="2"
                    :gutter="10">
            <van-grid-item v-for="(item, index) in gameLists"
                           :key="index">
              <van-image :src="item.imgUrl" />
              <van-cell :value="item.title" />
              <van-cell :value="item.price" />
            </van-grid-item>

          </van-grid>
        </van-swipe-item>

      </van-swipe>
    </div>

  </div>
</template>

<script>
export default {
  name: 'Recom',
  data() {
    return {
      gameLists: [
        {
          imgUrl: 'http://img.fhyx.com/uploads/2017/06/20/2017062022744870.jpg',
          title: '海岛大亨4',
          price: '￥12.00'
        },
        {
          imgUrl:
            'http://img.fhyx.com/uploads/2017/07/12/20170712113645423.jpg',
          title: '最终幻想7',
          price: '￥12.00'
        },
        {
          imgUrl: 'http://img.fhyx.com/uploads/2019/06/12/2019061294624105.jpg',
          title: '美国卡车模拟',
          price: '￥12.00'
        },
        {
          imgUrl: 'http://img.fhyx.com/uploads/2017/06/07/2017060742001591.jpg',
          title: '街头霸王5',
          price: '￥12.00'
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
@import '@/assets/common.scss';
.part-title {
  margin: 0 10px;
  border-bottom: 0.01rem solid #e2e2e2;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  clear: both;
  height: 2rem;
  line-height: 2rem;
  justify-content: space-between;
  position: relative;
  span {
    position: relative;
    font-size: 1rem;
    letter-spacing: 0.2rem;
    color: #2e2e2e;
    font-weight: bold;
    cursor: pointer;

    &::after {
      content: '';
      width: 100%;
      height: 0.2rem;
      background-color: #fe653b;
      border-radius: 0.04rem;
      bottom: -0.04rem;
      left: 0;
      position: absolute;
    }
  }
}
.container {
  overflow-x: scroll;
  padding-top: 1rem;
  .van-card {
    background-color: #ffffff;
    box-shadow: 0 0 4px 0 rgba(188, 188, 188, 0.5);
    border-radius: 0.1rem;
    margin: 0.45rem 0.24rem 0.4rem 0;
  }
}

.worth-buy-container {
  margin: 1rem;
  box-shadow: 0px 4px 16px 0px rgba(188, 188, 188, 0.35);
  border-radius: 20px;
}
.my-swipe {
  height: 22rem;
  padding-top: 1rem;
}
.van-cell {
  padding: 0;
}
</style>