<template>
  <div class="top-board">
    <div class="cards-container">
      <CardComponent v-for="(card, index) in cardData" :key="index" :title="card.title.toUpperCase()"
        :value="card.value" :icon="card.icon" :customClass="card.class" />
    </div>

    <div class="charts-container">
      <LineChart :data="lineChartData" class="line-chart" />
      <div class="column-donut-chart">
        <ColumnChart :data="columnChartData" class="column-chart" />
        <DonutChart :data="donutChartData" class="donut-chart" />
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
import axios from 'axios';

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
      lineChartData: [],
      columnChartData: [],
      donutChartData: []
    };
  },
  mounted() {
    this.fetchLineChartData();
    this.fetchColumnChartData();
    this.fetchDonutChartData();
  },
  methods: {
    async fetchLineChartData() {
      try {
        const response = await axios.get('http://localhost:3000/api/line-chart-data');
        console.log(response.data)
        this.lineChartData = response.data;
      } catch (error) {
        console.error('Error fetching line chart data:', error);
      }
    },
    async fetchColumnChartData() {
      try {
        const response = await axios.get('http://localhost:3000/api/servertime-chart-data');
        console.log(response.data)
        this.columnChartData = response.data;
      } catch (error) {
        console.error('Error fetching column chart data:', error);
      }
    },
    async fetchDonutChartData() {
      try {
        const response = await axios.get('http://localhost:3000/api/sales-data');
        console.log(response.data)
        this.donutChartData = response.data;
      } catch (error) {
        console.error('Error fetching donut chart data:', error);
      }
    }
  }
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
  flex-grow: 1;
  gap: 10px;
}

.cards-container .card {
  flex: 1;
}

.charts-container {
  display: flex;
  gap: 20px;
}

.line-chart {
  background-color: white;
  border-radius: 8px;
  width: 700px;
}

.column-donut-chart {
  display: flex;
  flex-direction: column;
  gap: 20px;
  flex-grow: 1;
}

.column-chart,
.donut-chart {
  flex: 2;
  flex-grow: 1;
}

@media screen and (max-width: 1028px) {
  .charts-container {
    flex-wrap: wrap;
    flex-grow: 1;
  }

  .line-chart {
    width: 100%;
  }
}
</style>
