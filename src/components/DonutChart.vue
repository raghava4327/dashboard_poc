<template>
    <div class="donut-chart">
      <div>
        <p class="val">{{ avgSales }}</p>
        <p class="val-title">AVG OF SALES</p>
      </div>
      <ApexChart width="150" type="donut" :options="chartOptions" :series="series"></ApexChart>
    </div>
  </template>
  
  <script>
  export default {
    name: 'DonutChart',
    props: {
      data: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        chartOptions: {
          legend: {
            show: false // Hide legend
          },
          dataLabels: {
            enabled: false // Disable data labels (percentage labels)
          },
          colors: [] // This will be updated based on the values
        },
        series: [], // Initialize with an empty array
        avgSales: 0 // Initialize average sales
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
        const salesData = data.map(item => item.no_of_sales);
        const totalSales = salesData.reduce((acc, val) => acc + val, 0);
        const avgSales = (totalSales / salesData.length).toFixed(2); // Calculate the average
  
        this.series = salesData;
        this.avgSales = avgSales;
        this.chartOptions.colors = this.getColorsBasedOnValues(salesData)
        
      },
      getColorsBasedOnValues(values) {
        // Define your color logic here
        return values.map(value => {
          if (value >=350) {
            return '#2c691a'; // Dark green for high values
          } else if (value > 300) {
            return '#77bc2d'; // Light green for medium values
          } else {
            return '#94cf83'; // Lighter green for low values
          }
        });
      }
    }
  };
  </script>
  
  <style scoped>
  .donut-chart {
    display: flex;
    justify-content: space-between;
    padding-top: 20px;
    padding-left: 20px;
    padding-right: 20px;
    letter-spacing: 0.5px;
    gap: 20px;
    flex-grow: 1;
    background-color: white;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
  }
  .val {
    color: #77bc2d;
    font-weight: bolder;
    font-size: 18px;
    text-align: left;
  }
  .val-title {
    color: #b9adbf;
    font-size: 8px;
  }
  </style>
  