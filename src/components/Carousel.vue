<script setup>
import { onMounted, onBeforeUnmount, nextTick } from 'vue'

const images = [
  'https://images.pexels.com/photos/414144/pexels-photo-414144.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
  'https://images.pexels.com/photos/1809644/pexels-photo-1809644.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
  'https://images.pexels.com/photos/540518/pexels-photo-540518.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
  'https://images.pexels.com/photos/1183099/pexels-photo-1183099.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
  'https://images.pexels.com/photos/1529881/pexels-photo-1529881.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1',
]

let myCarousel

onMounted(() => {
  const elem = document.getElementById('my-carousel')
  myCarousel = new Flickity(elem, {
    cellAlign: 'left',
    contain: true,
    imagesLoaded: true,
  })
})

onBeforeUnmount(() => {
  myCarousel.destroy()
})
</script>

<template>
  <div id="my-carousel">
    <div class="carousel-cell" v-for="(image, idx) in images" :key="idx">
      <img :src="image" alt="" />
    </div>
  </div>
</template>

<style scoped>
.carousel-cell.is-selected {
  height: 100%;
}

.carousel-cell.is-selected img {
  height: 100%;
}

:deep(.flickity-prev-next-button.previous),
:deep(.flickity-prev-next-button.next) {
  background-color: white;
}

:deep(.flickity-prev-next-button.previous) {
  left: 24px;
}

:deep(.flickity-prev-next-button.next) {
  right: 24px;
}

:deep(.flickity-page-dots) {
  bottom: -32px;
}
</style>
