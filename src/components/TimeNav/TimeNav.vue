<template>
  <view>
    <view class="timeNav-ico"></view>
    <view class="timeNav-timeChoose">
      <date-choose @func='getChildrenDate' />
    </view>
  </view>
</template>
<script>
import DateChoose from "../DateChoose/DateChoose.vue";
export default {
  components: { DateChoose },

  methods: {
    getChildrenDate: function(data) {
      // TODO: 将数据保存，顺便更改选择器的样式，建议对日期选择增加更多的if
      console.log(data)
    }
  }
};
</script>
DateChoose
