<template>
  <view>
    <status-bar></status-bar>
    <view>{{ content }}</view>
  </view>
</template>

<script>
import StatusBar from "../../components/StatusBar/StatusBar.vue";

export default {
  components: { StatusBar },

  data() {
    return {
      content: "Hello World!"
    };
  }
};
</script>
