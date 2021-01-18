<template>
  <view class="top" :style="{ height: height }"></view>
</template>
<script>
let statusBarHeight;
uni.getSystemInfo({
  success: res => {
    statusBarHeight = res.statusBarHeight
  }
})

export default {
  data() {
    return {
      height: statusBarHeight + 'px'
    };
  }
};
</script>
<style>
.top {
  width: 100%;
}
</style>
