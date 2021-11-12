<template>

  <div class="panel-right line">
    <h2>用户年龄</h2>
    <dv-active-ring-chart
      :config="config"
      class="circle-chart"
    ></dv-active-ring-chart>
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {
        data: [
          {
            name: "18岁-20岁",
            value: 55,
          },
          {
            name: "20岁-25岁",
            value: 120,
          },
          {
            name: "25岁-30岁",
            value: 78,
          },
          {
            name: "30岁-35岁",
            value: 66,
          },
          {
            name: "35岁-40岁",
            value: 80,
          },
        ],
        digitalFlopStyle: {
          fontSize: 15,
        },
        showOriginValue: true,
      },
    };
  },
};
</script>

<style scoped>
.circle-chart {
  margin-top: -0.425rem;
  height: 2.5rem;
  margin-bottom: -0.2rem;
}
</style>