<script setup>
import logoC from '~/assets/nftCalendar.png'
import logoW from '~/assets/logo.png'

const socials = [
  { name: 'X', icon: 'i-carbon:logo-x', link: 'https://twitter.com/solananowls?s=21&t=7ujY1o2NLmeyKDdBZm-LdQ' },
  { name: 'X', icon: 'i-carbon:logo-discord', link: 'https://discord.gg/3HAHYXsgPy' },
]
</script>

<template>
  <div class="sticky flex items-center justify-center bg-stone-900 p-0 text-sm space-x-8">
    <!-- Social Items -->
    <div flex>
      <a>
        <img :src="logoW" h-6 w-6 icon-btn md:h-10 md:w-10> Night Owls
      </a>
    </div>
    <div>
      <a v-for="social in socials" :key="social.name" :href="social.link" target="_blank" rel="noopener noreferrer" icon-btn>
        <div :class="`${social.icon} w-6 h-6 md:w-10 md:h-10`" />
      </a>
    </div>
    <div>
      <a href="https://nftcalendar.io/b/solana/" target="_blank" icon-btn>
        As Seen On:
        <img :src="logoC" w-15 icon-btn md:w-18>
      </a>
    </div>
  </div>

  <p class="text-sm font-mono icon-btn">
    © 2024 Night Owls
  </p>
</template>
