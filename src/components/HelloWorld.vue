<template>
  <div>
    <div id="chart">
      <h4>Bar Chart</h4>
      <canvas id="planet-chart"></canvas>
    </div>
  </div>
</template>

<script>
import Chart from "chart.js";
import chartData from "@/charts/chart-data.js";
export default {
  name: "HelloWorld",
  data() {
    return {
      barchart: chartData.barChart,
      name: "Moses"
    };
  },
  computed: {
    // barchart() {
    //   return chartData.barChart;
    // }
  },
  methods: {
    createChart(chartId, barchart) {
      const ctx = document.getElementById(chartId);
      // initializing the chart
      new Chart(ctx, {
        type: barchart.type,
        data: barchart.data,
        options: barchart.options
      });
    }
  },
  mounted() {
    this.createChart("planet-chart", this.barchart);
  }
};
</script>

<style scoped lang="scss">
#chart {
  width: 750px;
  margin: 0 auto;
}
</style>
