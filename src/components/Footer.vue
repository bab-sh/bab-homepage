<template>
  <footer class="w-full py-4">
    <div class="max-w-7xl mx-auto px-6 flex items-center justify-between">
      <div class="text-gray-400 text-sm flex items-center gap-1">
        <router-link to="/imprint" class="hover:text-white transition-colors">Imprint</router-link>
        <span class="mx-2">|</span>
        <span class="flex items-center gap-1">
          Made with <Heart :size="14" class="text-red-500 fill-red-500" /> by <a href="https://github.com/aiomayo" target="_blank" rel="noopener noreferrer" class="text-white font-medium hover:text-purple-400 transition-colors">aio</a>
        </span>
      </div>

      <a href="https://github.com/bab-sh/bab" target="_blank" rel="noopener noreferrer" class="text-gray-400 hover:text-white transition-colors">
        <GitHubIcon class="w-5 h-5" />
      </a>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { Heart } from 'lucide-vue-next'
import { GitHubIcon } from 'vue3-simple-icons'
</script>