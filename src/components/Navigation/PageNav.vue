<script setup lang="ts">
import { useAppStore } from '~/stores/app'

const appStore = useAppStore()
const route = useRoute()
const prevPage = ref({ title: '', to: '' })
const nextPage = ref({ title: '', to: '' })

for (let i = 0; i < appStore.componentPages.length; i++) {
  const page = appStore.componentPages[i]
  if (`${page.to}` === `${route.path}`) {
    if (i > 0)
      prevPage.value = appStore.componentPages[i - 1]

    if (i < appStore.componentPages.length - 1)
      nextPage.value = appStore.componentPages[i + 1]

    break
  }
}
</script>

<template>
  <div class="flex items-center mt-12">
    <router-link
      v-if="prevPage.to"
      :to="prevPage.to"
      size="lg"
      class="sa-btn sa-highlight dark:text-dark-100 sa-btn-lg sa-link gap-2"
    >
      <span>
        <tabler-arrow-left />
      </span>
      <span class="font-bold">{{ prevPage.title }}</span>
    </router-link>
    <div class="flex-grow"></div>
    <router-link
      v-if="nextPage.to"
      :to="nextPage.to"
      size="lg"
      class="sa-btn sa-highlight sa-link dark:text-dark-100 gap-2"
    >
      <span class="font-bold">{{ nextPage.title }}</span>
      <span>
        <tabler-arrow-right />
      </span>
    </router-link>
  </div>
</template>
