<script setup lang="ts">
const code = ref('')
</script>

<template>
  <VCodeInput v-model="code" pattern="XXX-XXX" input-class="border-2 sa-border sa-shade" />
  <div class="font-mono text-xl font-bold">{{ code }}</div>
</template>
