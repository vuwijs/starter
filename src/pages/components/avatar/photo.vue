<script setup lang="ts">
const photo
  = 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80'
</script>

<template>
  <VAvatar name="Alex Lifeson" :photo="photo" class="rounded-full overflow-hidden" size="sm" />
  <VAvatar name="Rob Taylor" :photo="photo" />
  <VAvatar name="Bryan Adams" :photo="photo" class="rounded-full overflow-hidden" size="lg" />
  <VAvatar name="Alex Lifeson" :photo="photo" size="xl" />
</template>
