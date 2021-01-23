<template>
  <view>
    <status-bar :backgroundColor="'#6190E8'"></status-bar>
    <high-nav>
      <time-nav class="highNav-timeNav"></time-nav>
      <view class="account-downNav-box">
        <view class="account-downNav-expense-box">
          <view>
            <view class="account-downNav-expense-title">支出</view>
            <view class="account-downNav-expense-content">{{ expense }}</view>
          </view>
        </view>
        <view class="account-downNav-income-box">
          <view class="account-downNav-income-title">收入</view>
          <view class="account-downNav-income-content">{{ income }}</view>
        </view>
        <view class="account-downNav-surplus-box">
          <view>
            <view class="account-downNav-surplus-title">结余</view>
            <view class="account-downNav-surplus-content">{{ surplus }}</view>
          </view>
        </view>
      </view>
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
      content: "Hello World!",
      expense: 99999.99,
      income: 999999.99,
      surplus: 99999.99
    };
  }
};
</script>
<style scoped>
@import url(./account.css);
</style>
