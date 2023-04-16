<template>
    <div id="content">
        <div class="chart-wrapper">
            <h3>Simple area chart.</h3>
            <apexchart width="1300" type="area" :options="chartOptions" :series="series"></apexchart>
        </div>
        <hr>
        <div class="chart-wrapper">
            <h3>Simple line chart</h3>
            <apexchart width="1300" type="line" :options="chartOptions" :series="series"></apexchart>
        </div>
        <hr>
        <div class="chart-wrapper">
            <h3>Simple bar chart</h3>
            <apexchart width="1300" type="bar" :options="chartOptions" :series="series"></apexchart>
        </div>
        <hr>
        <div class="chart-wrapper">
            <h3>Mixed chart (line and area)</h3>
            <apexchart width="1300" type="area" :options="chartOptions" :series="mixedSeries"></apexchart>
        </div>
        <hr>
        <div class="chart-wrapper">
            <h3>Pie Chart</h3>
            <apexchart width="1000" type="pie" :options="pieOptions" :series="pieSeries"></apexchart>
        </div>
        <hr>
        <div class="chart-wrapper">
            <h3>Polararea Chart</h3>
            <apexchart width="1000" type="polarArea" :options="pieOptions" :series="pieSeries"></apexchart>
        </div>
    </div>
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
const pieOptions: ApexOptions = {
    chart: {
        id: "my-pie-chart"
    },
    title: {
        text: "Co2 Emissions 2021 (Mton)",
        style: {
            fontSize: "18px"
        }
    },
    labels: ["China", "United States", "EU27", "India", "Russia", "Japan"]
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
const mixedSeries: ApexAxisChartSeries = [
    {
        name: "Temperature Atlanta",
        data: [21, 26, 28, 29, 26, 19, 17],
        type: "area"
    },
    {
        name: "Temperature Augsburg",
        data: [11, 12, 12, 11, 17, 18, 19],
        type: "line"
    }
]
const pieSeries: ApexNonAxisChartSeries = [12466.32, 4752.08, 2774.93, 2648.78, 1942.54, 1084.69]
</script>

<style scoped>
h3 {
    margin-bottom: 20px;
    font-weight: bold;
}

.chart-wrapper {
    margin-top: 20px;
}
</style>