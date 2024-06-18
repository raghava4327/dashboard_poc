<template>
    <div class="line-chart">
        <ApexChart width=500 type="line" :options="chartOptions" :series="series"></ApexChart>
    </div>
</template>

<script>
export default {
    name: 'LineChart',
    data() {
        return {

            series: [
                {
                    name: "Pageviews",
                    data: [28, 29, 33, 36, 32, 32, 3]
                },
                {
                    name: "Visitors",
                    data: [12, 40, 14, 33, 17, 13, 13]
                }
            ],
            chartOptions: {
                chart: {
                    height: 350,
                    background:"#fff",
                    type: 'line',
                    dropShadow: {
                        enabled: true,
                        color: '#000',
                        top: 18,
                        left: 7,
                        blur: 10,
                        opacity: 0.2
                    },
                    zoom: {
                        enabled: false
                    },
                    toolbar: {
                        show: false
                    }
                },
                colors: ['#cde7b8', '#eeeeee'],
                dataLabels: {
                    enabled: false,
                },
                stroke: {
                    curve: 'straight'
                },

                grid: {
                    borderColor: '#e7e7e7',
                    xaxis: {
                        lines: {
                            show: true
                        }
                    },
                    yaxis: {
                        lines: {
                            show: true
                        }
                    },
                },
                markers: {
                    size: 3
                },
                xaxis: {

                    categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul'],

                },
                yaxis: {

                    min: 0,
                    max: 80
                },
                legend: {
                    position: 'top',
                    horizontalAlign: 'right',
                    floating: true,
                    offsetY: -5,
                    offsetX: -5
                }
            },


        }




    }
}
</script>

<style scoped>
.line-chart {
    grid-column: 2 / 3;
    /* Span the second column */
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
</style>

