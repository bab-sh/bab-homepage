<template>
  <AuroraBackground>
    <div class="w-5xl gap-8 flex flex-row items-stretch">
      <BlurReveal
          :delay="0.3"
          :duration="0.75"
          class="flex-1 w-full"
      >
          <CodeBlock
              class="h-full"
              :code="babfileContent"
              language="yaml"
              title="Babfile.yml"
          />

      </BlurReveal>


      <BlurReveal
          :delay="0.5"
          class="flex flex-1 flex-row items-stretch gap-2"
      >
        <div class="flex flex-1 flex-col justify-between">
          <div>
            <h2 class="text-7xl font-bold tracking-tighter">
              <LineShadowText
                  class="italic"
              >
                Project Commands,
              </LineShadowText>
              defined in <br>
              <SparklesText
                  text="YAML"
                  :colors="{ first: '#9E7AFF', second: '#FE8BBB' }"
                  :sparkles-count="5"
                  class="inline"
              />
            </h2>
            <p class="mt-3 mb-6 text-left text-lg">
              The alternative for Makefile and Taskfile
            </p>
          </div>

          <div class="flex flex-row items-center gap-4">
            <div class="relative group">
              <Button disabled class="opacity-50 cursor-not-allowed"> Get Started </Button>
              <span class="absolute bottom-full left-1/2 -translate-x-1/2 mb-2 px-3 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap pointer-events-none">
                Coming Soon
              </span>
            </div>
            <div class="relative group">
              <Button disabled variant="outline" class="opacity-50 cursor-not-allowed">
                Learn More
              </Button>
              <span class="absolute bottom-full left-1/2 -translate-x-1/2 mb-2 px-3 py-1 bg-gray-800 text-white text-sm rounded opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap pointer-events-none">
                Coming Soon
              </span>
            </div>
          </div>
        </div>

        <div class="flex h-full items-center justify-center" style="width: 24vh;">
          <span class="block font-bold whitespace-nowrap rotate-90 leading-none p-0 m-0" style="font-size: 22vh; transform-origin: center center; line-height: 1; background: linear-gradient(to right, #8051ff, #ff4796); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent; color: transparent;">BAB</span>
        </div>
      </BlurReveal>
    </div>
  </AuroraBackground>
</template>e
<script setup lang="ts">
import {AuroraBackground} from "@/components/ui/aurora-background";
import {BlurReveal} from "@/components/ui/blur-reveal";
import {Button} from "@/components/ui/button"
import {CodeBlock} from "@/components/ui/code-block"
import babfileContent from "@/assets/babfile.yaml?raw"
import {LineShadowText} from "@/components/ui/line-shadow-text";
import {SparklesText} from "@/components/ui/sparkles-text";
</script>