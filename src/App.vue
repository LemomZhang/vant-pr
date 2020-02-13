<template>
  <div id="app">

    <router-view />
    <Tabbar />
  </div>
</template>
<script>
import Tabbar from '@/components/Tabbar.vue';
export default {
  components: {
    Tabbar
  }
};
</script>
<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
a {
  color: inherit;
}
</style>
