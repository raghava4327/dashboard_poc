<template>
    <div class="chart-container">
      <ApexChart type="area" height="150" :options="chartOptions" :series="series"></ApexChart>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LineChart',
    props: {
    downloadSpeedData: {
      type: Array,
      required: true
    },
    uploadSpeedData: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      series: [
        {
          name: "Download Speed",
          data: this.downloadSpeedData
        },
        {
          name: "Upload Speed",
          data: this.uploadSpeedData
        }
      ],
      chartOptions: {
        chart: {
          type: 'area',
          stacked: true,
          zoom: {
            enabled: false
          },
          toolbar: {
            show: false
          },
        },
        colors: ['#665872', '#cbafe4'],
        dataLabels: {
          enabled: false
        },
        stroke: {
          curve: 'straight'
        },
        grid: {
          show: false
        },
        xaxis: {
          labels: {
            show: false,
          }
        },
        yaxis: {
          opposite: true,
          labels: {
            show: false
          }
        },
        legend: {
          show: false
        },
      }
    };
  },
  };
  </script>
  
  <style scoped>
  .chart-container {
    width: 100%;
    max-width: 1000px; 
    margin: 0 auto;
  }
 
  </style>
  