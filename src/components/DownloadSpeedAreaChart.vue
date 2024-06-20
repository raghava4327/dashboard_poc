<template>
    <div class="chart-container">
      <ApexChart type="area" height="150" :options="chartOptions" :series="series"></ApexChart>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LineChart',
    data() {
      return {
        series: [
          {
            name: "STOCK ABC",
            data: [20, 35, 40, 32, 38, 45, 50, 55, 30, 32, 20, 25, 30, 28, 26, 32, 38, 45, 50, 55]
          },
          {
            name: "STOCK XYZ",
            data: [20, 25, 30, 28, 26, 32, 38, 45, 50, 55, 20, 25, 30, 28, 26, 32, 38, 45, 50, 55]
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
          colors: ['#cbafe4', '#665872'],
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
    }
  };
  </script>
  
  <style scoped>
  .chart-container {
    width: 100%;
    max-width: 1000px; 
    margin: 0 auto;
  }
 
  </style>
  