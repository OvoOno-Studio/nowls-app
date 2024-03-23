<script setup>
import nft1 from '~/assets/owl1.png'
import nft2 from '~/assets/owl2.png'
import nft3 from '~/assets/owl3.png'
import nft4 from '~/assets/owl4.png'

const images = [nft1, nft2, nft3, nft4]
</script>

<template>
  <div class="bg-zinc-900">
    <div class="flex items-center justify-center">
      <div class="mx-auto max-w-sm px-2">
        <div class="grid grid-cols-2 gap-4 sm:grid-cols-2">
          <img v-for="(image, index) in images" :key="index" :src="image" alt="Night Owls Gif" class="w-full sm:w-sm">
        </div>
      </div>
    </div>
  </div>
</template>
