<template>
    <div class="column-chart">
        <ApexChart width=200 type="bar" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>
    <script>
    export default{
        name:'barChart',
        data:function(){
            return {
                chartOptions:{},
                series: [{
            name: 'Inflation',
            data: [2.3, 3.1, 4.0, 10.1, 4.0, 3.6, 3.2, 2.3, 1.4, 0.8, 0.5, 0.2]
          }],
            }
        }
    }
    </script>
    <style>

    </style>