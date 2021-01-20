<template>
  <view>
    <picker
      mode="date"
      fields="month"
      @change="chooseCallBack"
      :value="choose_date"
    >
      <view class="dateChose-showText">
        {{ choose_date }}
      </view>
    </picker>
  </view>
</template>
<script>
let now_date = new Date();

export default {
  data() {
    return {
      choose_date: now_date.getFullYear() + "-" + (now_date.getMonth() + 1)
    };
  },
  methods: {
    // 时间选择后回调
    chooseCallBack: function(event) {
      this.choose_date = event.detail.value;
      this.$emit("func", event.detail.value);
    }
  }
};
</script>
