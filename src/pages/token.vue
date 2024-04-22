<script setup>
import { onMounted, ref } from 'vue'
import token from '~/assets/nowlsToken.png'

const tokenomicsTexts = [
  '- Supply: 28,000,000',
  '- Liquidity Pool: 14,000,000',
  '- Holder Airdrop: 12,320,000',
  '- Giveaways: 1,680,000',
]

const showTokenomicsTexts = ref(Array(tokenomicsTexts.length).fill(false))

onMounted(() => {
  tokenomicsTexts.forEach((text, index) => {
    setTimeout(() => {
      showTokenomicsTexts.value[index] = true
    }, (index + 1) * 1000)
  })
})
</script>

<template>
  <section id="tokenomics" class="min-h-screen flex flex-col items-center justify-center gap-20 px-8 py-8 lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0">
    <div class="mb-4 w-50 flex items-center justify-center lg:w-1/3">
      <img :src="token" alt="Logo">
    </div>
    <div class="z-50 my-4 flex flex-col whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <div class="mb-4 text-3xl lg:text-6xl xl:text-6xl">
        <h2>
          $NOWLS Tokenomics
        </h2>
        <hr class="border-1 border-amber-600">
      </div>

      <ul class="my-3 pl-0 text-left">
        <li v-for="(text, index) in tokenomicsTexts" :key="index" class="xl:text-2xl">
          <TypeWritter v-if="showTokenomicsTexts[index]" :text="text" />
        </li>
      </ul>
      <p class="dis mb-4 pl-0 text-white lg:text-lg">
        Profit of sales will go to Liquidity Pool with 14,000,000 $NOWLS token. For holders of Night Owls, 44% of token supply will be airdropped and 6% goes to giveaways.
      </p>
      <div>
        <router-link to="/mint" class="cursor-pointer hover:text-amber-600">
          <button btn>
            Mint
          </button>
        </router-link>
      </div>
    </div>
  </section>
</template>
