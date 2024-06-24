<template>
  <div class="line-chart">
    <div v-if="series.length === 0"></div>
    <div v-else>
      <ApexChart
        
        height="300"
        class="line-apex"
        type="line"
        :options="chartOptions"
        :series="series"
      ></ApexChart>
    </div>
  </div>
</template>

<script>
export default {
  name: "LineChart",
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      series: [],
      chartOptions: {
        chart: {
          parentHeightOffset: 0,
          background: "#fff",
          type: "line",
          width: "100%",
          dropShadow: {
            enabled: true,
            color: "#000",
            top: 18,
            left: 7,
            blur: 10,
            opacity: 0.2
          },
          zoom: {
            enabled: false
          },
          toolbar: {
            show: false
          }
        },
        colors: ["#7bc044", "#e0e0e0"],
        dataLabels: {
          enabled: false
        },
        stroke: {
          curve: "straight"
        },
        grid: {
          position: "back",
          borderColor: "#e7e7e9",
          xaxis: {
            lines: {
              show: false
            }
          },
          yaxis: {
            lines: {
              show: false
            }
          }
        },
        title: {
          text: "14.85%",
          align: "left",
          style: {
            fontSize: "16px",
            color: "#72b828"
          }
        },
        subtitle: {
          text: "More visitors",
          align: "left",
          style: {
            fontSize: "14px",
            color: "#c6b7c7"
          }
        },
        markers: {
          size: 4,
          colors: ["#68b828", "#e0e0e0"]
        },
        xaxis: {
          labels: {
            show: false
          }
        },
        yaxis: {
          labels: {
            show: false
          },
          min: 0,
          max: 80
        },
        legend: {
          position: "top",
          horizontalAlign: "center",
          floating: false,
          markers: {
            width: 12,
            height: 12,
            radius: 0,
            fillColors: ["#68b828", "#e0e0e0"]
          },
          itemMargin: {
            horizontal: 10,
            vertical: 5
          }
        }
      }
    };
  },
  watch: {
    data: {
      handler(newData) {
        this.updateChart(newData);
      },
      deep: true,
      immediate: true
    }
  },
  methods: {
    updateChart(data) {
      this.series = data.map(item => ({
        name: item.category,
        data: item.data
      }));
    }
  }
};
</script>

<style scoped>
.line-chart {
  display: flex;
  /* flex-grow: 1; */
  align-items: center;
  width: 100%;
}
.line-chart div {
  width: 100%;
}
</style>
