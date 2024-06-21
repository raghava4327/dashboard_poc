<template>
    <div class="container">
      <vue-gauge
        :refid="'type-unique'"
        :class="'metricsGauge'"
        :options="{
          needleValue: 400,
          needleColor: '#68b828',
          arcDelimiters: [25, 50,75],
          arcColors: [ '#68b828','#68b828','#68b828','#d5080f'],
          arcOverEffect: true,
          arcLabels:['25','50','75'],
          chartWidth: 250,
          rangeLabel: ['0', '100'],
          hasNeedle: true,
        }"
      >
      </vue-gauge>
    </div>
  </template>
  
  <script>
  import VueGauge from "vue-gauge";
  export default {
    components: { VueGauge },
  };
  </script>
  
  <style>
  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    /* margin-top: 60px; */
  }
  .container {
    display: flex;
    justify-content: center;
   
  }
  </style>
  