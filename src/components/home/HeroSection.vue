<template>
  <AuroraBackground>
    <div class="w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col lg:flex-row items-stretch gap-4 lg:gap-8">
      <div class="lg:hidden text-center mb-4">
        <h1 class="text-9xl font-bold leading-none" style="background: linear-gradient(to right, #8051ff, #ff4796); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; color: transparent;">BAB</h1>
      </div>

      <BlurReveal
          :delay="0.3"
          :duration="0.75"
          class="flex-1 w-full"
      >
          <CodeBlock
              class="h-[400px] lg:h-full"
              :code="babfileContent"
              language="yaml"
              title="Babfile.yml"
          />

      </BlurReveal>


      <BlurReveal
          :delay="0.5"
          class="flex flex-1 flex-col lg:flex-row items-stretch gap-2"
      >
        <div class="flex flex-1 flex-col justify-between gap-6 items-center lg:items-start">
          <div class="text-center lg:text-left">
            <h2 class="text-5xl sm:text-6xl lg:text-7xl font-bold tracking-tighter leading-tight">
              <span class="inline-block">
                <LineShadowText class="italic">
                  Project
                </LineShadowText>
              </span>
              <br>
              <span class="inline-block">
                <LineShadowText class="italic">
                  Commands,
                </LineShadowText>
              </span>
              <br>
              <span class="inline-block">defined in</span>
              <br>
              <SparklesText
                  text="YAML"
                  :colors="{ first: '#9E7AFF', second: '#FE8BBB' }"
                  :sparkles-count="5"
                  class="inline-block"
              />
            </h2>
            <p class="mt-3 mb-6 text-center lg:text-left text-base lg:text-lg">
              The alternative for Makefile and Taskfile
            </p>
          </div>

          <div class="flex flex-col sm:flex-row items-center gap-3 sm:gap-4 w-full sm:w-auto">
            <div class="relative group w-full sm:w-auto">
              <Button disabled class="opacity-50 cursor-not-allowed w-full sm:w-auto"> Get Started </Button>
              <span class="absolute bottom-full left-1/2 -translate-x-1/2 mb-2 px-3 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap pointer-events-none">
                Coming Soon
              </span>
            </div>
            <div class="relative group w-full sm:w-auto">
              <Button disabled variant="outline" class="opacity-50 cursor-not-allowed w-full sm:w-auto">
                Learn More
              </Button>
              <span class="absolute bottom-full left-1/2 -translate-x-1/2 mb-2 px-3 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap pointer-events-none">
                Coming Soon
              </span>
            </div>
          </div>
        </div>

        <div class="hidden lg:flex h-full items-center justify-center" style="width: 24vh;">
          <span class="block font-bold whitespace-nowrap rotate-90 leading-none p-0 m-0" style="font-size: 25vh; transform-origin: center center; line-height: 1; background: linear-gradient(to right, #8051ff, #ff4796); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; color: transparent;">BAB</span>
        </div>
      </BlurReveal>
    </div>
  </AuroraBackground>
</template>
<script setup lang="ts">
import {AuroraBackground} from "@/components/ui/aurora-background";
import {BlurReveal} from "@/components/ui/blur-reveal";
import {Button} from "@/components/ui/button"
import {CodeBlock} from "@/components/ui/code-block"
import babfileContent from "@/assets/babfile.yaml?raw"
import {LineShadowText} from "@/components/ui/line-shadow-text";
import {SparklesText} from "@/components/ui/sparkles-text";
</script>