<template>
  <div class="min-h-screen flex flex-col">
    <main class="flex-1">
      <router-view />
    </main>
    <Footer />
  </div>
</template>
<script setup lang="ts">
import Footer from "@/components/Footer.vue";
</script>