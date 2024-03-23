<script setup>
import nft1 from '~/assets/owl1.png'
import nft2 from '~/assets/owl2.png'
import nft3 from '~/assets/owl3.png'
import nft4 from '~/assets/owl4.png'

const images = [nft1, nft2, nft3, nft4]
</script>

<template>
  <div class="bg-zinc-900">
    <div class="h-screen flex items-center justify-center">
      <div class="mx-auto max-w-3xl px-2">
        <div class="grid grid-cols-2 gap-4 sm:grid-cols-4">
          <img v-for="(image, index) in images" :key="index" :src="image" alt="Night Owls Gif" class="w-full sm:w-auto">
        </div>
        <div class="mt-8 flex flex-row gap-8">
          <TypeWritter text="HOOT" :changeable="true" class="text-6xl sm:text-9xl" />
          <TypeWritter text="HOOT" :changeable="true" class="text-6xl sm:text-9xl" />
        </div>
      </div>
    </div>
  </div>
</template>
