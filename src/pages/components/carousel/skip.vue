<script setup lang="ts">
const slideIndex = ref(0)
const slides = [
  'bg-yellow-400 h-25',
  'bg-teal-400 h-25',
  'bg-blue-400  h-50',
  'bg-red-400 h-45',
  'bg-pink-400 h-25',
  'bg-lime-400 h-40',
  'bg-indigo-400 h-65',
]
</script>

<template>
  <VCarousel v-model="slideIndex" vertical slider-class="h-75 scroll-smooth">
    <VCarouselItem
      v-for="(slide, index) in slides"
      :key="index"
      class="flex items-center justify-center w-full text-4xl text-white"
      :class="slide"
    >Slide {{ index + 1 }}</VCarouselItem>
    <template #overlay="{ prevSlide, nextSlide }">
      <div class="absolute top-0 w-full h-full">
        <VButton icon class="absolute left-4 sa-ml sa-shade-strongest" @click="prevSlide(1)">
          <tabler-chevron-left />
        </VButton>
        <div
          class="absolute sa-bc sa-center sa-shade-strongest w-12 rounded-lg mb-2 h-8 text-xs font-bold"
        >{{ slideIndex + 1 }}</div>
        <VButton icon class="absolute sa-mr right-4 sa-shade-strongest" @click="nextSlide(2)">
          <tabler-chevron-right />
        </VButton>
      </div>
    </template>
  </VCarousel>
</template>
