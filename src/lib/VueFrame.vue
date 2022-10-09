<script setup lang="ts">
import { ref } from 'vue'
const iframeRef = ref<HTMLIFrameElement | null>(null)
</script>

<template>
  <iframe ref="iframeRef" />
</template>

<style scoped>

</style>
