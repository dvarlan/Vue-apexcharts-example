<template>
    <apexchart width="1300" type="area" :options="chartOptions" :series="series"></apexchart>
</template>

<script setup lang="ts">
    import type { ApexOptions } from 'apexcharts';
    const chartOptions: ApexOptions = {
        chart: {
            id: "my-chart"
        },
        title: {
            text: "A comparison between the temperatures in Atlanta and Augsburg",
            style: {
                fontSize: "18px"
            }
        },
        xaxis: {
            title: {
                text: "Calendarweek 16, 2023",
                style: {
                    fontSize: "18px"
                }
            },
            categories: ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]
        },
        yaxis: {
            title: {
                text: "Temperature in °C",
                style: {
                    fontSize: "18px"
                }
            }
        }
    }
    const series: ApexAxisChartSeries = [
        {
            name: "Temperature Atlanta",
            data: [21, 26, 28, 29, 26, 19, 17]
        },
        {
            name: "Temperature Augsburg",
            data: [11, 12, 12, 11, 17, 18, 19]
        }
    ]
</script>