<template>
  <div class="panel line">
    <h2>平台关联度</h2>
    <dv-charts
      :option="option"
      style="width:200px;height:200px"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      option: {
        radar: {
          indicator: [
            { name: "西峡", max: 300 },
            { name: "周口", max: 300 },
            { name: "南阳", max: 300 },
            { name: "驻马店", max: 300 },
            { name: "郑州", max: 300 },
            { name: "洛阳", max: 300 },
          ],
          polygon: true,
          axisLine: {
            style: {
              stroke: "rgba(251, 114, 147, .3)",
            },
          },
          splitLine: {
            style: {
              stroke: "rgba(251, 114, 147, .5)",
              fill: "rgba(251, 114, 147, .2)",
            },
          },
        },
        series: [
          {
            type: "radar",
            data: [111, 256, 178, 152, 266, 132],
          },
        ],
      },
    };
  },
};
</script>

<style>
</style>