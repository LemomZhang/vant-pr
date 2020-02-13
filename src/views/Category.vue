<template>
  <div>
    <van-search v-model="value"
                shape="round"
                placeholder="请输入搜索关键词" />
    <div>
      <van-tabs v-model="active">
        <div>
          <van-dropdown-menu>
            <van-dropdown-item v-model="value1"
                               :options="option1" />
            <van-dropdown-item v-model="value2"
                               :options="option2" />
          </van-dropdown-menu>
        </div>
        <van-tab title="游戏">
          <van-pull-refresh v-model="refreshing"
                            @refresh="onRefresh">
            <van-list v-model="loading"
                      :finished="finished"
                      finished-text="没有更多了"
                      @load="onLoad">

              <van-card v-for="(item, index) in list"
                        :key="index"
                        :price="item.price"
                        :desc="item.desc"
                        :title="item.title"
                        :thumb="item.imgUrl">
                <div slot="tags">
                  <van-tag v-for="(tag, index) in item.tag"
                           :key="index"
                           plain
                           type="danger">{{tag}}</van-tag>
                </div>

              </van-card>
            </van-list>
          </van-pull-refresh>
        </van-tab>
        <van-tab title="主机">
          <van-pull-refresh v-model="refreshing"
                            @refresh="onRefresh">
            <van-list v-model="loading"
                      :finished="finished"
                      finished-text="没有更多了"
                      @load="onLoad">

              <van-card v-for="(item, index) in zhuji"
                        :key="index"
                        :price="item.price"
                        :desc="item.desc"
                        :title="item.title"
                        :thumb="item.imgUrl">
                <div slot="tags">
                  <van-tag v-for="(tag, index) in item.tag"
                           :key="index"
                           plain
                           type="danger">{{tag}}</van-tag>
                </div>

              </van-card>
            </van-list>
          </van-pull-refresh>
        </van-tab>
        <van-tab title="潮流">
          <van-pull-refresh v-model="refreshing"
                            @refresh="onRefresh">
            <van-list v-model="loading"
                      :finished="finished"
                      finished-text="没有更多了"
                      @load="onLoad">

              <van-card v-for="(item, index) in pop"
                        :key="index"
                        :price="item.price"
                        :desc="item.desc"
                        :title="item.title"
                        :thumb="item.imgUrl">
                <div slot="tags">
                  <van-tag v-for="(tag, index) in item.tag"
                           :key="index"
                           plain
                           type="danger">{{tag}}</van-tag>
                </div>

              </van-card>
            </van-list>
          </van-pull-refresh>
        </van-tab>
        <van-tab title="周边">
          <van-pull-refresh v-model="refreshing"
                            @refresh="onRefresh">
            <van-list v-model="loading"
                      :finished="finished"
                      finished-text="没有更多了"
                      @load="onLoad">

              <van-card v-for="(item, index) in rim"
                        :key="index"
                        :price="item.price"
                        :desc="item.desc"
                        :title="item.title"
                        :thumb="item.imgUrl">
                <div slot="tags">
                  <van-tag v-for="(tag, index) in item.tag"
                           :key="index"
                           plain
                           type="danger">{{tag}}</van-tag>
                </div>

              </van-card>
            </van-list>
          </van-pull-refresh>
        </van-tab>
      </van-tabs>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      active: 0,
      value: '',
      value1: 0,
      value2: 'a',
      option1: [
        { text: '全部', value: 0 },
        { text: '即将上市', value: 1 },
        { text: '热销', value: 2 }
      ],
      option2: [
        { text: '默认排序', value: 'a' },
        { text: '好评排序', value: 'b' },
        { text: '销量排序', value: 'c' }
      ],
      list: [],
      zhuji: [],
      pop: [],
      rim: [],
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
          this.zhuji.push({
            title: `國行NS遊戲主機${this.list.length + 1} 全國聯保 紅藍`,
            imgUrl:
              'http://img.fhyx.com/uploads/2019/12/04/2019120482441347.jpg',
            price: `${1988 + this.list.length}.00`,
            tag: ['SWITCH'],
            desc: '國行 Nintendo Switch NS 任天堂家用遊戲機續航增強版'
          });
          this.list.push({
            title: `侠客风云传${this.list.length + 1} PC版 數字版`,
            imgUrl:
              'http://img.fhyx.com/uploads/2019/02/27/201902273081351.jpg',
            price: `${55 + this.list.length}.00`,
            tag: ['中文', '动作'],
            desc: 'Tale of Wuxia' + this.list.length + 1
          });
          this.pop.push({
            title: `俠客Q版 主題T恤（合作款）`,
            imgUrl:
              'http://img.fhyx.com/uploads/2018/11/22/2018112254848657.jpg',
            price: `${79 + this.pop.length}.00`,
            tag: ['中文'],
            desc: '俠客Q版 主題T恤（合作款） 180/XL'
          });
          this.rim.push({
            title: `軒轅劍6 鳳天淩Q版手辦`,
            imgUrl:
              'http://img.fhyx.com/uploads/2019/10/22/2019102255819330.jpg',
            price: `${9 + this.rim.length}.00`,
            tag: ['周边'],
            desc: '軒轅劍6 遊戲周邊 鳳天淩Q版手辦'
          });
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
</style>