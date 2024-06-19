<template>
    <div class="donut-chart">
        <ApexChart width=200 type="donut" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>

<script>
export default {
 name: 'donutChart',
 data: function () {
  return {
   chartOptions: {},
   series: [44, 55, 41, 17, 15]

}}}
</script>

<style scoped>
.donut-chart {
    grid-column: 3 / 3;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
</style>