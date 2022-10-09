<script lang="ts">
export default {
  // inheritAttrs: false
}
</script>

<script setup lang="ts">
import { ref, onMounted, defineProps, useAttrs } from 'vue'
const iframeRef = ref<HTMLIFrameElement | null>(null)

interface Props {
  inheritStyles?: boolean
  stylesheet?: string
}
const props = defineProps<Props>()
const attrs = useAttrs()

onMounted(() => {
  if (props.inheritStyles) {
    const styles = Array.from(iframeRef.value?.contentWindow?.parent.document.querySelectorAll('style') ?? [])
    styles.forEach((el) => {
      iframeRef.value?.contentDocument?.head.appendChild(el.cloneNode(true))
    })
  }
  if (props.stylesheet) {
    const styleEl = iframeRef.value?.contentDocument?.createElement('style')!
    styleEl.innerText = props.stylesheet
    iframeRef.value?.contentDocument?.head.appendChild(styleEl)
  }
})
</script>

<template>
  <iframe ref="iframeRef" v-bind="attrs" />
  <Teleport v-if="iframeRef?.contentDocument?.body" :to="iframeRef?.contentDocument?.body">
    <slot />
  </Teleport>
</template>

<style scoped>

</style>
