<template>
  <div class="panel line">
    <h2>美誉度</h2>
    <dv-charts :option="option1" class="circle-chart"/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      option1: {
        series: [
          {
            type: "gauge",
            data: [{ name: "itemA", value: 55 }],
            axisLabel: {
              formatter: "{value}%",
            },
            details: {
              show: true,
              offset: [0, 40],
              formatter: "{value}%",
            },
            animationCurve: "easeOutBack",
          },
        ],
      },
    };
  },

};
</script>

<style scoped>
.circle-chart {
  margin-top: -0.25rem;
  margin-bottom: -0.35rem;
  height: 2.5rem;
}
</style>