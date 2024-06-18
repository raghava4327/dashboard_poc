<template>
    <div class="bottom">
      <div class="bottom-left">
      <RadialComponent />
      <div class="bottom-left-area">
        <p>Page Views</p>
        <AreaChart />
      </div>
      </div>
      <div class="bottom-right">
        <div class="bottom-right-top">
          <div class="info">
            <p class="btm-right-top-val">20.99mb/s</p>
            <p class="btm-right-subtitle"> DOWNLOAD SPEED</p>
          </div>
          <div class="gauge-wrapper">
            <GaugeComponent />
          </div>
        </div>
        <div class="bottom-right-bottom">
          <div class="info">
            <p class="btm-right-btm-val">65.35%</p>
            <p class="btm-right-subtitle">CPU USAGE</p>
            <p class="btm-right-subtitle">Sentiments two occassional affronting soltitude travelling and one contrasted.Fortune day out married parties</p>
          </div>
          <div class="gauge-wrapper">
            <SecondGauge />
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import GaugeComponent from './GaugeComponent.vue';
  import SecondGauge from './SecondGauge.vue';
  import RadialComponent from './RadialComponent.vue'
  import AreaChart from './AreaChart.vue'
  export default {
    components: {
      GaugeComponent,
      SecondGauge,
      RadialComponent,
      AreaChart
    }
  };
  </script>
  
  <style scoped>
  .bottom {
    display: flex;
    justify-content: space-between;
    margin: 20px;
    gap:10px;
  }
  
  .bottom-left {
    display: flex;
    justify-content: center;
    flex-direction: column;
    width:50%;
    background-color: white;
  }
  .bottom-left-area{
    display:flex;
    justify-content: space-between;
    align-items: center;
    padding-left:20px;
    margin-top:30px;
    border-top:1px solid #b3b3b3;
  }
  .bottom-right {
    width: 50%;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  
  .bottom-right-top,
  .bottom-right-bottom {
    display: flex;
    padding: 20px;
    background-color: white;
    justify-content: space-between;
    align-items: flex-start;
  }
  
  .info {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  
  .gauge-wrapper {
    display: flex;
    align-items: center;
  }

  .btm-right-top-val{
    color:#410082;
    font-weight: bolder;
    font-size:30px;
    
  }
  .btm-right-btm-val{
    color:#68b828;
    font-weight: bolder;
    font-size:30px;
    text-align: left;
  }
  .btm-right-subtitle{
    font-size:10px;
    text-align: left;
    letter-spacing:0.5px;
    color:#b3b3b3;
    margin-top:10px

  }
  </style>
  