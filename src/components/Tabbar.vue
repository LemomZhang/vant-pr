<template>
  <div>
    <van-tabbar v-model="active"
                active-color="#fb5a24"
                inactive-color="#000">
      <van-tabbar-item icon="home-o"
                       to="/">首页</van-tabbar-item>
      <van-tabbar-item icon="apps-o"
                       to="/category">分类</van-tabbar-item>

      <van-tabbar-item icon="user-o"
                       to="/my">我的</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
export default {
  name: 'Tabbar',
  data() {
    return {
      active: 0
    };
  }
};
</script>

<style>
</style>