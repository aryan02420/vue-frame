<script setup lang="ts">
import { ref, defineProps } from 'vue'

defineProps<{
  title: string
}>()

const count = ref(0)
</script>

<template>
  <div>
    <h2>{{ title }}</h2>
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>
</template>

<style scoped>
div {
  display: grid;
  place-items: center;
}
</style>
