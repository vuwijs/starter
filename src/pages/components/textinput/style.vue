<script setup lang="ts">
const text = ref('')
</script>

<template>
  <div class="grid gap-4">
    <VTextInput placeholder="No style" />
    <VTextInput placeholder="Background style" class="bg-dark-900 bg-opacity-3 dark:bg-opacity-20" />
    <VTextInput placeholder="Background and border style" class="dark:bg-dark-900 dark:bg-opacity-20 border sa-border" />
    <VTextInput
      v-model="text"
      label="Fully customized"
      placeholder="Type here..."
      class="bg-purple-800 border-3 border-purple-400 rounded-xl filter drop-shadow-lg text-white custom-textinput"
    >
      <template #prepend>
        <tabler-palette class="w-12 h-12 min-w-12 text-purple-400 mr-2 ml-1" />
      </template>

      <template #append>
        <VButton v-if="text" icon class="w-12 min-w-12 h-12 min-h-12 bg-purple-400" @click="text = ''">
          <tabler-x class="text-purple-600 text-4xl" />
        </VButton>
      </template>
    </VTextInput>
  </div>
</template>

<style>
.custom-textinput label {
  @apply text-purple-100 text-lg;
}

.custom-textinput input {
  @apply font-bold text-3xl !pt-6;
}

.custom-textinput input::placeholder {
  color: #ffffff50;
}
</style>
