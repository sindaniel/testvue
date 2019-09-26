<template>
  <div>
    <p>hla123</p>
    <apexchart
      @dataPointSelection="clickHandler"
      @markerClick="clickHandler"
      type="donut"
      height="350"
      :options="chartOptions"
      :series="series"
    />
    <p>hla</p>
  </div>
</template>

<script>
import VueApexCharts from "vue-apexcharts";

export default {
  data: function() {
    return {
      series: [44, 55, 41, 17, 15],
      chartOptions: {
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 50
              },
              legend: {
                position: "bottom"
              }
            }
          }
        ]
      }
    };
  },

  methods: {
    clickHandler(event, chartContext, config) {
      console.log(config);
    }
  },

  props: {
    msg: String
  },
  components: {
    apexchart: VueApexCharts
  }
};
</script>
