<script setup lang="ts">
const showAlert = ref(false)

</script>

<template>
  <div class="h-full flex flex-col justify-center items-center">
    <VButton class="absolute sa-mc sa-primary" @click="showAlert = true">Show Alert</VButton>
    <transition name="alert">
      <VAlert v-if="showAlert" class="py-1 sa-danger z-10" role="alert">
        <span class="p-3 pl-5">I'm an alert that informs you of stuff.</span>
        <VButton icon class="mr-2" @click="showAlert = false">
          <tabler-x class="text-xl" />
        </VButton>
      </VAlert>
    </transition>
  </div>
</template>

<style scoped>
.alert-enter-active {
  transition: all 200ms ease-out;
}

.alert-leave-active {
  transition: all 200ms ease-in;
}

.alert-enter-from,
.alert-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
