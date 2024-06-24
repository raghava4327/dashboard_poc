<template>
  <div class="bottom">
    <!-- Left Section -->
    <div class="bottom-left">
      <RadialComponent />
      <div class="bottom-left-area">
        <p>Page Views</p>
        <AreaChart :chartData="pageViewsData" />
      </div>
      <div class="bottom-left-area">
        <p>Visitors</p>
        <AreaChart :chartData="visitorsData" />
      </div>
      <div class="bottom-left-area">
        <p>Converted Sales</p>
        <AreaChart :chartData="convertedSalesData" />
      </div>
    </div>

    <!-- Right Section -->
    <div class="bottom-right">
      <!-- Top Right -->
      <div class="bottom-right-top">
  <div class="title-and-gauge">
    <div class="info">
      <p class="btm-right-top-val">{{ downloadSpeed }}</p>
      <p class="btm-right-subtitle">DOWNLOAD SPEED</p>
    </div>
    <div v-if="needleValue" class="gauge-wrapper">
      <GaugeComponent :needleValue="needleValue" />
    </div>
  </div>
  <div v-if="downloadSpeedChartData.length > 0 && uploadSpeedChartData.length > 0">
  <DownloadSpeedAreaChart
    :downloadSpeedData="downloadSpeedChartData"
    :uploadSpeedData="uploadSpeedChartData"
  />
</div>
</div>


      <!-- Bottom Right -->
      <div class="bottom-right-bottom">
        <div class="info">
          <p class="btm-right-btm-val">{{ cpuUsage }}%</p>
          <p class="btm-right-subtitle">CPU USAGE</p>
          <p class="btm-right-subtitle">
            Sentiments two occasional affronting solicitude travelling and one
            contrasted. Fortune day out married parties.
          </p>
        </div>
        <div v-if="cpuUsage" class="gauge-wrapper">
          <SecondGauge :value="cpuUsage" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import RadialComponent from './RadialComponent.vue';
import AreaChart from './AreaChart.vue';
import GaugeComponent from './GaugeComponent.vue';
import SecondGauge from './SecondGauge.vue';
import DownloadSpeedAreaChart from './DownloadSpeedAreaChart.vue';

export default {
  components: {
    RadialComponent,
    AreaChart,
    GaugeComponent,
    SecondGauge,
    DownloadSpeedAreaChart
  },
  data() {
    return {
      pageViewsData: [], // Assuming these are arrays of data for AreaChart
      visitorsData: [],
      convertedSalesData: [],
      downloadSpeed: '', // String for displaying download speed
      downloadSpeedChartData: [], // Array for chart data
      uploadSpeedChartData: [], // Array for chart data
      cpuUsage: '', // String for displaying CPU usage
      needleValue:''
    };
  },
  mounted() {
    this.fetchData(); // Fetch all necessary data on component mount
  },
  methods: {
    async fetchData() {
      try {
  
        const internetSpeedResponse = await axios.get('http://localhost:3000/api/internet-speed');
        const internetSpeedData = internetSpeedResponse.data;
        console.log(internetSpeedData);
        
       
        this.downloadSpeed = `${internetSpeedData[0].download_speed} mb/s`;
        this.downloadSpeedChartData = internetSpeedData.map(item => parseFloat(item.download_speed));
        this.uploadSpeedChartData = internetSpeedData.map(item => parseFloat(item.upload_speed));
        this.needleValue = parseFloat(this.downloadSpeed) * 0.5;


        const cpuUsageResponse = await axios.get('http://localhost:3000/api/cpu-usage');
        const cpuUsageData = cpuUsageResponse.data;
        console.log(cpuUsageData);
        
        // Assuming cpuUsageData is an array of objects with 'cpu_usage' property
        this.cpuUsage = cpuUsageData[0].cpu_usage;
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    },
 
  }
};
</script>

<style scoped>
.bottom {
  display: flex;
  justify-content: space-between;
  margin: 20px;
  gap: 10px;
}

.bottom-left {
  display: flex;
  justify-content: center;
  flex-direction: column;
  width: 50%;
  background-color: white;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.bottom-left-area {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-left: 20px;
  margin-top: 30px;
  border-top: 1px solid #b3b3b3;
}

.bottom-right {
  width: 50%;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.bottom-right-bottom,
.bottom-right-top {
  padding: 20px;
  background-color: white;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  flex-grow: 1;
}

.title-and-gauge {
  display: flex;
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

.btm-right-top-val {
  color: #410082;
  font-weight: bolder;
  font-size: 30px;
}

.btm-right-btm-val {
  color: #68b828;
  font-weight: bolder;
  font-size: 30px;
  text-align: left;
}

.btm-right-subtitle {
  font-size: 10px;
  text-align: left;
  letter-spacing: 0.5px;
  color: #b3b3b3;
  margin-top: 10px;
}
.bottom-right-bottom{
  display:flex;
  justify-content: space-between;
}
@media screen and (max-width: 860px) {
  .bottom {
    display: flex;
    flex-direction: column;
    margin: 20px;
    gap: 10px;
  }
  .bottom-left,
  .bottom-right {
    width: 100%;
  }
  .title-and-gauge,
  .bottom-right-bottom {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  } 
  
}
</style>
