<template>
  <div class="panel-right line">
    <h2>用户性别</h2>
    <dv-active-ring-chart
      :config="config"
      class="circle-chart"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {
        data: [
          {
            name: "男",
            value: 55,
          },
          {
            name: "女",
            value: 45,
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
  margin-bottom: -0.2rem;
  height: 2.5rem;
}
</style>