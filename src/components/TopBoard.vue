<template>
  <div class="top-board">
    <CardComponent v-for="(card, index) in cardData" :key="index" :title="card.title.toUpperCase()" :value="card.value" :icon="card.icon" :customClass="card.class"/>
    
    <LineChart  class="line-chart"/>
    <ColumnChart class="column-chart"/>
  
    <DonutChart class="donut-chart"/>
  </div>
</template>

<script>
import CardComponent from "./Cardcomponent.vue";
import LineChart from "./LineChart.vue";
import ColumnChart from "./ColumnChart.vue";
import DonutChart from "./DonutChart.vue";
// import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faUser } from '@fortawesome/free-regular-svg-icons';
import { faCloud, faCamera } from '@fortawesome/free-solid-svg-icons';

export default {
  name: "TopComponent",
  components: {
    CardComponent,
    LineChart,
    ColumnChart,
    DonutChart,
    // FontAwesomeIcon
  },
  data() {
    return {
      cardData: [
        {
          title: "Server uptime",
          value: "99.7%",
          icon: faCloud,
          class:"green-icon"
        },
        { 
          title: "Users total", 
          value: "117K", 
          icon: faUser, 
          class:"purple-icon"
        },
        { 
          title: "New Daily photos", 
          value: "2,470", 
          icon: faCamera, 
          class:"blue-icon"
        },
      ],
    };
  },
};
</script>

<style scoped>
.top-board {
  margin:20px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: repeat(3, auto);
  gap: 10px;
  grid-template-areas: 
    "card1 line-chart donut-chart"
    "card2 line-chart column-chart"
    "card3 line-chart column-chart";
}

.card:nth-child(1) {
  grid-area: card1;
}

.card:nth-child(2) {
  grid-area: card2;
}

.card:nth-child(3) {
  grid-area: card3;
}

.line-chart {
  grid-area: line-chart;
}

.column-chart, .donut-chart {
  height: 100%;
  width: 100%;
}

.column-chart {
  grid-area: column-chart;
}

.donut-chart {
  grid-area: donut-chart;
}
</style>
