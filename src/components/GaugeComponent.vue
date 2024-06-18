<template>
    <div class="container">
      <vue-gauge
        :refid="'type-unique-id'"
        :class="'meticsGauge'"
        :options="{
          needleValue: 400,
          centralLabel: '',
          needleColor: '#410082',
          arcDelimiters: [25, 50, 75],
          arcColors: [ '#8264db','#8264db','#8264db','#8264db'],
          arcOverEffect: true,
          arcLabels:['50','100','150'],
          chartWidth: 250,
          rangeLabel: ['0', '200'],
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
  