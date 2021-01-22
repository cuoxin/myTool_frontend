<template>
  <view>
    <picker
      mode="date"
      :fields="date_type"
      @change="chooseCallBack"
      :value="choose_date"
      :end="now_date"
    >
      <view class="dateChose-showText">
        {{ choose_date }}
      </view>
    </picker>
  </view>
</template>
<script>
// 处理日期数据
/**
 * @param { String } date_type 精确的位数
 */
let dealDate = date_type => {
  let now = new Date();
  let now_month = now.getMonth();
  let now_date = now.getDate();

  if (now_month < 10) {
    now_month = "0" + (now.getMonth() + 1);
  }
  if (now_date < 10) {
    now_date = "0" + now.getDate();
  }

  if (date_type === "month") {
    now = now.getFullYear() + "-" + now_month;
  } else if (date_type === "day") {
    now = now.getFullYear() + "-" + now_month + "-" + now_date;
  }

  return now;
};

export default {
  props: {
    end_type: String
  },

  data() {
    let now_date = dealDate(this.end_type);

    return {
      date_type: this.end_type,
      now_date: now_date,
      choose_date: now_date
    };
  },

  methods: {
    // 时间选择后回调
    chooseCallBack: function(event) {
      this.choose_date = event.detail.value;

      // 把数据传递出去
      this.$emit("func", event.detail.value);
    }
  }
};
</script>
