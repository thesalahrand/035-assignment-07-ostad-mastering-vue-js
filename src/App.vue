<script setup>
import { ref } from 'vue'
import Carousel from './components/Carousel.vue'
import PieChart from './components/PieChart.vue'

const compToShow = ref('carousel')
</script>

<template>
  <div class="max-w-[540px] mx-auto py-8 px-4">
    <div class="flex justify-center space-x-8 mb-8">
      <div class="flex items-center">
        <input
          id="carousel"
          value="carousel"
          type="radio"
          v-model="compToShow"
          name="learn-lifecycle-hook"
          class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500"
          @change="compToShow = 'carousel'"
        />
        <label for="carousel" class="ml-2 text-sm font-medium text-gray-900"
          >Show Carousel</label
        >
      </div>
      <div class="flex items-center">
        <input
          v-model="compToShow"
          id="pie-chart"
          value="pie-chart"
          type="radio"
          name="learn-lifecycle-hook"
          class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500"
          @change="compToShow = 'pie-chart'"
        />
        <label for="pie-chart" class="ml-2 text-sm font-medium text-gray-900"
          >Show Pie Chart</label
        >
      </div>
    </div>
    <Carousel v-if="compToShow === 'carousel'" />
    <PieChart v-if="compToShow === 'pie-chart'" />
  </div>
</template>

<style scoped></style>
