<script setup>
import { onMounted, onBeforeUnmount } from 'vue'
import Chart from 'chart.js/auto'

let myPieChart

onMounted(() => {
  const ctx = document.getElementById('my-pie-chart')

  myPieChart = new Chart(ctx, {
    type: 'pie',
    data: {
      labels: ['Red', 'Blue', 'Yellow'],
      datasets: [
        {
          label: 'My First Dataset',
          data: [300, 50, 100],
          backgroundColor: [
            'rgb(255, 99, 132)',
            'rgb(54, 162, 235)',
            'rgb(255, 205, 86)',
          ],
          hoverOffset: 4,
        },
      ],
    },
  })
})

onBeforeUnmount(() => {
  myPieChart.destroy()
})
</script>

<template>
  <canvas id="my-pie-chart">
    <!-- ...  -->
  </canvas>
</template>

<style scoped></style>
