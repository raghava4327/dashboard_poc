<template>
    <div class="donut-chart">
    <div>
   <p class="val">320,45</p>
   <p class="val-title">AVG OF SALES</p>
</div>
        <ApexChart width=150 type="donut" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>

<script>
export default {
 name: 'donutChart',
 data: function () {
  return {
   chartOptions: {
    legend: {
          show: false // Hide legend
        },
        dataLabels: {
          enabled: false // Disable data labels (percentage labels)
        },
        colors: ['#9edb8b', '#2c691a', '#3a7727', '#94cf83', '#5e9b4c']
   },
   series: [44, 55, 41, 17, 15]

}}}
</script>

<style scoped>
.donut-chart {
    grid-column: 3 / 3;
    display: flex;
    justify-content: space-between;
    padding-top:20px;
    padding-left:20px;
    padding-right:20px;
    letter-spacing: 0.5px;
    gap: 20px;
    flex-grow:1;
    background-color: white;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px
    
}
 .val{
    color:#77bc2d;
    font-weight: bolder;
    font-size:18px;
    text-align: left;
    
}
.val-title{
    color:#b9adbf;
    font-size:8px;
}
</style>