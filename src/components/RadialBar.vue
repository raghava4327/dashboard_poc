<template>
  <div class="circular-gauge">
    <ApexChart height=300 type="radialBar" :options="chartOptions" :series="series" />
  </div>
  </template>
  <script>
  export default{
    name:'radialChart',
    data:function(){
      return{
        chartOptions:{},
        series: [44, 55, 67, 83],
      }
    }
  }
  </script>
  <style>
 
  </style>