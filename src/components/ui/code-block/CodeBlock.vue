<template>
  <div class="rounded-sm w-full h-full overflow-hidden flex flex-col">
    <!-- macOS Title Bar -->
    <div class="flex items-center justify-between bg-[#212121] p-2 flex-shrink-0">
      <!-- Traffic Light Buttons -->
      <div class="flex gap-2">
        <button
            @click="$emit('close')"
            class="w-2.5 h-2.5 rounded-full bg-[#ff5f57] hover:bg-[#ff4842] transition-colors"
            aria-label="Close"
        />
        <button
            class="w-2.5 h-2.5 rounded-full bg-[#ffbd2f] hover:bg-[#ffb01f] transition-colors"
            aria-label="Minimize"
        />
        <button
            class="w-2.5 h-2.5 rounded-full bg-[#28c840] hover:bg-[#1fb830] transition-colors"
            aria-label="Zoom"
        />
      </div>

      <!-- Title Label -->
      <span class="absolute left-1/2 -translate-x-1/2 text-xs font-medium text-gray-500">
        {{ title }}
      </span>
    </div>

    <!-- Code Content -->
    <div class="bg-[#292929] flex-1 overflow-auto">
      <pre class="overflow-x-auto text-sm m-0 h-full"><code ref="codeRef" :class="`language-${language}`"></code></pre>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, watch } from 'vue'
import hljs from 'highlight.js'
import yaml from 'highlight.js/lib/languages/yaml'

hljs.registerLanguage('yaml', yaml)

interface Props {
  code: string
  language?: string
  title?: string
}

const props = withDefaults(defineProps<Props>(), {
  language: 'yaml',
  title: ''
})

defineEmits<{
  close: []
}>()

const codeRef = ref<HTMLElement>()

const highlight = () => {
  if (codeRef.value) {
    codeRef.value.textContent = props.code
    hljs.highlightElement(codeRef.value)
  }
}

onMounted(highlight)
watch(() => [props.code, props.language], highlight)
</script>

<style>
@import 'highlight.js/styles/a11y-dark.css';

pre,
pre *,
code,
code *,
.hljs,
.hljs * {
  font-family: 'JetBrains Mono', 'SF Mono', Monaco, Menlo, Consolas, 'Ubuntu Mono', monospace !important;
}

pre {
  line-height: 1.5;
  background: transparent !important;
}

code {
  background: transparent !important;
}

.hljs {
  background: transparent !important;
}
</style>