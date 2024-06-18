<template>
    <div class="radial-chart">
      
        <ApexChart type="radialBar" height="300" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>

<script>
export default {
    name: 'RadialChart',
    data() {
        return{ 
            series: [17, 11, 54, 72],
          chartOptions: {
            chart: {
              height: 390,
              type: 'radialBar',
            },
            plotOptions: {
              radialBar: {
                offsetY: 0,
                startAngle:-135,
                endAngle: 135,
                hollow: {
                  margin: 5,
                  size: '30%',
                  background: 'transparent',
                  image: undefined,
                },
                dataLabels: {
                  name: {
                    show: false,
                  },
                  value: {
                    show: false,
                  }
                },
                // barLabels: {
                //   enabled: true,
                //   useSeriesColors: true,
                //   margin: 8,
                //   fontSize: '16px',
                //   formatter: function(seriesName, opts) {
                //     return seriesName + ":  " + opts.w.globals.series[opts.seriesIndex]
                //   },
                // },
              }
            },
            colors: ['#68b828', '#7c38bc', '#0e62c7', '#fcd036'],
            // labels: ['Vimeo', 'Messenger', 'Facebook', 'LinkedIn'],
            responsive: [{
              breakpoint: 480,
              options: {
                legend: {
                    show: false
                }
              }
            }]
          },
          
          
        

        }




    }
}
</script>

<style scoped>
.radial-chart {
    grid-column: 2 / 3;
    /* Span the second column */
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
</style>