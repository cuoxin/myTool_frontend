<template>
  <view
    class="timeNav-box"
    :style="{ height: timeNavBoxStyle.height, top: timeNavBoxStyle.top }"
  >
    <view class="timeNav-box-" :style="{ height: timeNavBoxStyle.height }">
      <view class="timeNav-ico">图</view>
      <date-choose
        class="timeNav-dateChoose-box"
        @func="getChildrenDate"
        end_type="month"
      />
    </view>
  </view>
</template>
<script>
import DateChoose from "../DateChoose/DateChoose.vue";

let getCapsuleData = () => {
  let state = uni.getMenuButtonBoundingClientRect();
  let style = {
    height: state.height + "px",
    top: state.top + "px"
  };

  return style;
};

export default {
  components: { DateChoose },

  data() {
    let timeNavBox = getCapsuleData();

    return {
      timeNavBoxStyle: timeNavBox
    };
  },

  methods: {
    getChildrenDate: function(data) {
      console.log(data);
    }
  }
};
</script>
<style scoped>
@import url(./TimeNav.css);
</style>
