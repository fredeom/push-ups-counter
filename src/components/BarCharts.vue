<script setup>
import { Bar } from 'vue-chartjs'
import { Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale} from 'chart.js'
</script>

<template>
    <Bar
      id="my-chart-id"
      :options="chartOptions"
      :data="chartData"
    />
  </template>
  
<script>
ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
    name: 'BarChart',
    components: { Bar },
    data() {
        const data =  [];
        for (let i = 1; i <= 7; i++) {
            const name = "day" + i;
            data.push({
                x: "day" + i,
                y: localStorage[name] ? localStorage[name] : 0
            })
        }
        return {
            chartData: {
                datasets: [ {
                    label: "Push-ups",
                    data: data
                } ]
            },
            chartOptions: {
                responsive: true,
                maintainAspectRatio: true,
            }
        }
    }
}
</script>