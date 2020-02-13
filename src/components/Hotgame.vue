<template>
  <div>
    <div class="part-title flex">
      <span>热门游戏</span>
    </div>
    <div>
      <van-pull-refresh v-model="refreshing"
                        @refresh="onRefresh">
        <van-list v-model="loading"
                  :finished="finished"
                  finished-text="没有更多了"
                  @load="onLoad">

          <van-card v-for="(item, index) in list"
                    :key="index"
                    tag="-14%"
                    price="299.00"
                    desc="Romance Of Three Kingdom 14"
                    title="三国志14"
                    thumb="https://img.fhyx.com/uploads/2019/12/30/2019123011282886.jpg"
                    origin-price="349.00" />
        </van-list>
      </van-pull-refresh>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [],
      loading: false,
      finished: false,
      refreshing: false
    };
  },
  methods: {
    onLoad() {
      setTimeout(() => {
        if (this.refreshing) {
          this.list = [];
          this.refreshing = false;
        }

        for (let i = 0; i < 10; i++) {
          this.list.push(this.list.length + 1);
        }
        this.loading = false;

        if (this.list.length >= 40) {
          this.finished = true;
        }
      }, 1000);
    },
    onRefresh() {
      // 清空列表数据
      this.finished = false;

      // 重新加载数据
      // 将 loading 设置为 true，表示处于加载状态
      this.loading = true;
      this.onLoad();
    }
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
.van-card {
  margin: 1rem 1rem;
  border-radius: 1rem;
}
</style>