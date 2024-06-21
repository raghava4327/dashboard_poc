  <template>
      <div class="column-chart">
          <p class="val">95.8%</p>
    <p class="val-title">CURRENT SERVER UPTIME</p>
          <ApexChart height="100" type="bar" :options="chartOptions" :series="series"></ApexChart>
      </div>
  </template>
      <script>
      export default{
          name:'barChart',
          data:function(){
              return {
                  chartOptions:{
                      chart:{
                          width: '100%',
                          toolbar: {
              show: false, // Hide toolbar
            },
                      },
                      plotOptions: {
                      bar: {
                          colors: {
                              ranges: [{
                                  from: 0,
                                  to: Infinity,
                                  color: '#7c38bc' // Default color for all bars (violet color)
                              }],
                          },
                      },
                  },
                      dataLabels: {
            enabled: false, // Disable data labels (values on bars)
          },xaxis: {
            labels: {
              show: false, // Hide y-axis labels
            },
          },yaxis: {
            labels: {
              show: false, // Hide y-axis labels
            },
            show:false,
          
          },  grid: {
            show: false, // Hide grid lines
          },
                  },
                  
                  series: [{
              name: 'Inflation',
              data: [2.3, 3.1, 4.0, 10.1, 4.0, 3.6, 3.2, 2.3, 1.4, 0.8, 0.5, 0.2]
            }],
              }
          }
      }
      </script>
      <style scoped>
  .column-chart{
      background-color: white;
      padding:20px 20px 0 20px;
      box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
      border-radius: 8px
  }
  .val{
      color: 'violet';
      font-weight: bolder;
      font-size:18px;
      text-align: left;
      
  }
  .val-title{
      color:#b9adbf;
      font-size:8px;
      text-align:left;
  }
      </style>