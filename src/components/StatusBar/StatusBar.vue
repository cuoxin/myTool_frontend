<template>
<!-- 防止内容被覆盖在top下面 -->
  <view class="top-box" :style="{ height: height }">
    <view
      class="top"
      :style="{ height: height, backgroundColor: backgroundColor }"
    ></view>
  </view>
</template>
<script>
let statusBarHeight;
uni.getSystemInfo({
  success: res => {
    statusBarHeight = res.statusBarHeight;
  }
});

export default {
  props: {
    backgroundColor: String
  },

  data() {
    return {
      height: statusBarHeight + "px"
    };
  }
};
</script>
<style>
.top {
  width: 100%;

  position: fixed;
  top: 0;
  right: 0;
  left: 0;
}
</style>
