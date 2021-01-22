<template>
  <view>
    <status-bar :backgroundColor="'#6190E8'"></status-bar>
    <high-nav>
      <time-nav class="highNav-timeNav"></time-nav>
    </high-nav>
    <view>{{ content }}</view>
  </view>
</template>

<script>
import HighNav from "../../components/HighNav/HighNav.vue";
import StatusBar from "../../components/StatusBar/StatusBar.vue";
import TimeNav from "../../components/TimeNav/TimeNav.vue";

export default {
  components: { StatusBar, HighNav, TimeNav },

  data() {
    return {
      content: "Hello World!"
    };
  }
};
</script>
<style scoped>
@import url(./account.css);
</style>
