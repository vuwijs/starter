<script setup lang="ts">
import { useImageToDataUrl } from '~/saturn/vue/src'

const file = ref<File>()
const dataUrl = ref('')

const handleChange = async (val?: FileList) => {
  if (val) {
    file.value = val[0]
    dataUrl.value = await useImageToDataUrl(file.value, 200, 200)
  } else {
    file.value = undefined
    dataUrl.value = ''
  }
}
</script>

<template>
  <div
    class="relative sa-center w-48 h-48 sa-highlight-strongest rounded-full border-6 sa-border cursor-pointer"
  >
    <VFileSelector
      :accepts="['jpg', 'jpeg', 'gif', 'png', 'svg']"
      class="sa-center w-full h-full rounded-full overflow-hidden"
      @change="handleChange"
    >
      <img v-if="dataUrl" :src="dataUrl" />
      <tabler-photo v-else class="text-7xl opacity-10" />
    </VFileSelector>
    <VButton
      icon
      size="lg"
      class="absolute sa-br m-1 border-4 sa-border bg-dark-200 dark:bg-dark-700 pointer-events-none"
    >
      <tabler-pencil class="text-xl opacity-20" />
    </VButton>
  </div>
</template>
