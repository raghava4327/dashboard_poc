<template>
  <div class="top-board">
    <div class="cards-container">
      <CardComponent 
        v-for="(card, index) in cardData" 
        :key="index" 
        :title="card.title.toUpperCase()" 
        :value="card.value" 
        :icon="card.icon" 
        :customClass="card.class"
      />
    </div>
    
    <div class="charts-container">
      <div class="line-chart">
      <LineChart />
      </div>
      <div class="column-donut-chart">
        <ColumnChart class="column-chart"/>
        <DonutChart class="donut-chart"/>
      </div>
    </div>
  </div>
 
</template>

<script>
import CardComponent from "./Cardcomponent.vue";
import LineChart from "./LineChart.vue";
import ColumnChart from "./ColumnChart.vue";
import DonutChart from "./DonutChart.vue";
import { faUser } from '@fortawesome/free-regular-svg-icons';
import { faCloud, faCamera } from '@fortawesome/free-solid-svg-icons';

export default {
  name: "TopComponent",
  components: {
    CardComponent,
    LineChart,
    ColumnChart,
    DonutChart,
  },
  data() {
    return {
      cardData: [
        {
          title: "Server uptime",
          value: "99.7%",
          icon: faCloud,
          class: "green-icon"
        },
        { 
          title: "Users total", 
          value: "117K", 
          icon: faUser, 
          class: "purple-icon"
        },
        { 
          title: "New Daily photos", 
          value: "2,470", 
          icon: faCamera, 
          class: "blue-icon"
        },
      ],
    };
  },
};
</script>

<style scoped>
.top-board {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
}

.cards-container {
  display: flex;
  flex-direction: column;
  flex: 1;
  gap: 10px;
}

.cards-container .card {
  flex: 1;
}

.charts-container {
  display: flex;

  gap: 20px;
 
  /* flex-wrap:wrap; */
}

.line-chart {
  /* flex: 1; */
  background-color: white;;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    width:100%;
}

.column-donut-chart {
  display: flex;
  flex-grow:1;
  flex-direction: column;
  gap: 20px;
}

.column-chart,
.donut-chart {
  flex: 1;
}
@media screen and (max-width: 860px) {
  .charts-container{
    flex-wrap: wrap;
  }
  .line-chart {
    border: 1px solid green;  
    width:100%;
}
}



</style>
