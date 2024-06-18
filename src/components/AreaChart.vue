<template>
    <div class="line-chart">
        <ApexChart type="area" height="100" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>

<script>
export default {
    name: 'LineChart',
    data() {
        return {
            series: [{
      name: "STOCK ABC",
      data: [30, 35]
    }],
    chartOptions: {
      chart: {
        type: 'area',
        height: 350,
        zoom: {
          enabled: false
        },
        toolbar: {
          show: false // Disable the toolbar (menu bar)
        },

      },
      colors: ['#92cb64'], 
      dataLabels: {
        enabled: false
      },
      stroke: {
        curve: 'smooth'
      },
     
      grid: {
        show: false // Disable grid lines
      },
     
      xaxis: {
        type: 'datetime',
        categories: ['2023-06-01', '2023-06-02'],
        labels: {
          show: false
        }

      },
      yaxis: {
        opposite: true,
        labels: {
          show: false
        }
      },
      legend: {
        horizontalAlign: 'left'
      },
      markers: {
        size: 5,
        colors: ['#fff'],
        strokeColors: ['#92cb64'],
        strokeWidth: 2,
        hover: {
          colors: ['#9159c7'],
          size: 3
        }
      }
    }
          
        


        }




    }
}
</script>

<style scoped>
.line-chart {
    grid-column: 2 / 3;
    /* Span the second column */
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
</style>