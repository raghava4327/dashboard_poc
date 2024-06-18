<template>
    <div class="line-chart">
        <ApexChart type="area" height="350" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>

<script>
export default {
    name: 'LineChart',
    data() {
        return {
            series: [{
      name: "STOCK ABC",
      data: [30, 40, 45, 50, 49, 60, 70, 91, 125]
    }],
    chartOptions: {
      chart: {
        type: 'area',
        height: 350,
        zoom: {
          enabled: false
        }
      },
      dataLabels: {
        enabled: false
      },
      stroke: {
        curve: 'straight'
      },
      title: {
        text: 'Fundamental Analysis of Stocks',
        align: 'left'
      },
      subtitle: {
        text: 'Price Movements',
        align: 'left'
      },
      xaxis: {
        type: 'datetime',
        categories: ['2023-06-01', '2023-06-02', '2023-06-03', '2023-06-04', '2023-06-05', '2023-06-06', '2023-06-07', '2023-06-08', '2023-06-09']
      },
      yaxis: {
        opposite: true
      },
      legend: {
        horizontalAlign: 'left'
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