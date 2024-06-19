<template>
  <div class="line-chart">
    <ApexChart
      width="600"
      
      type="line"
      :options="chartOptions"
      :series="series"
    ></ApexChart>
  </div>
</template>

<script>
export default {
  name: "LineChart",
  data() {
    return {
      series: [
        {
          name: "Pageviews",
          data: [28, 29, 33, 36, 32, 32, 3],
        },
        {
          name: "Visitors",
          data: [12, 40, 14, 33, 17, 13, 13],
        },
      ],
      chartOptions: {
        chart: {
            parentHeightOffset: 0,
          background: "#fff",
          type: "line",
          dropShadow: {
            enabled: true,
            color: "#000",
            top: 18,
            left: 7,
            blur: 10,
            opacity: 0.2,
          },
          zoom: {
            enabled: false,
          },
          toolbar: {
            show: false,
          },
        },

        colors: ["#7bc044", "#000"],
        dataLabels: {
          enabled: false,
        },
        stroke: {
          curve: "straight",
        },

        grid: {
            
        position:"back",
          borderColor: "#e7e7e9",
          xaxis: {
            lines: {
              show: true,
            },
          },
          yaxis: {
            lines: {
              show: true,
            },
          },
        },
                title: {
        text: 'Left-aligned Title',
        align: 'left',
        style: {
            fontSize: '16px',
            color: '#333'
        },
        offsetY: 80, // Offset from the top of the chart area
        offsetX: 10 // Offset from the left of the chart area
    },
    subtitle: {
        text: 'Subtitle text goes here',
        align: 'left',
        style: {
            fontSize: '14px',
            color: '#666'
        },
        offsetY: 100, // Offset from the top of the chart area
        offsetX: 10 // Offset from the left of the chart area
    },
        markers: {
          size: 4,
          colors:['#68b828','#5c6a5a'] 

        },
        xaxis: {
          labels: {
            show: false,
          },
        },
        yaxis: {
          labels: {
            show: false,
          },
          min: 0,
          max: 80,
        },
        legend: {
          position: "right",
          verticalAlign: "middle",
          floating: true,
          offsetY: 60,
          offsetX: -10,
          markers: {
            width: 12,
            height: 12,
            radius: 0,
            fillColors:['#68b828','#5c6a5a'] // This makes the markers square
          },
        },
      },
    };
  },
};
</script>

<style scoped>
.line-chart {
  grid-column: 2 / 3;
  display: flex;
  justify-content: center;
  align-items: center;
  
}
</style>
