<script setup>
import logofull from '~/assets/owl.gif'
import road from '~/assets/roadmap.jpg'

const roadmapTexts = [
  '- Presale',
  '- Public Mint',
  '- Tool Access',
  '- $NOWLS Airdrop',
  '- Access Alpha Channels',
]

const showRoadmapTexts = ref(Array(roadmapTexts.length).fill(false))

onMounted(() => {
  roadmapTexts.forEach((text, index) => {
    setTimeout(() => {
      showRoadmapTexts.value[index] = true
    }, (index + 1) * 1500)
  })
})
</script>

<template>
  <!-- HOOT HOOT -->
  <section mx-auto min-h-screen flex flex-col items-center justify-center px-8 py-8 container md:flex-row space-y-4 md:px-20 md:space-x-4 md:space-y-0>
    <div class="lg:w-1/3" mb-4>
      <img :src="logofull" mx-auto alt="Logo">
    </div>
    <div class="z-50 my-4 flex flex-col whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <h2 mb-4 text-3xl lg:text-6xl xl:text-6xl>
        Night Owls
      </h2>
      <hr border-1 border-amber-600>
      <ul my-3 pl-0>
        <li xl:text-2xl>
          <TypeWritter text="Supply: 2800" />
        </li>
        <li xl:text-2xl>
          <TypeWritter text="Mint Price: 0.13 SOL" />
        </li>
      </ul>
      <p class="mb-4 pl-0 text-sm text-white font-mono">
        Night Owls on Solana coming in 2800 unique NFTs. Holding NFT will guarantee access to the optimized trading tools with built-in node access. <br> <br> Each wallet will get airdrop of $NOWLS after the public sale.
      </p>
      <div>
        <router-link to="/token" class="cursor-pointer hover:text-amber-600">
          <button btn>
            $NOWLS
          </button>
        </router-link>
      </div>
    </div>
  </section>

  <section mx-auto min-h-screen flex flex-col items-center justify-center px-8 py-8 container md:flex-row space-y-4 md:px-20 md:space-x-4 md:space-y-0>
    <div class="mb-4 flex items-center justify-center lg:w-1/3">
      <img :src="road" alt="Logo">
    </div>
    <div class="z-50 my-4 flex-col pl-10 text-left font-bold font-sans lg:w-1/3">
      <div class="mb-4 text-3xl lg:text-6xl xl:text-6xl">
        <h2>
          $NOWLS Roadmap
        </h2>
        <hr class="border-1 border-amber-600">
      </div>

      <ul class="my-3 pl-0">
        <li v-for="(text, index) in roadmapTexts" :key="index" class="xl:text-2xl">
          <TypeWritter v-if="showRoadmapTexts[index]" :text="text" />
        </li>
      </ul>
      <button flex items-center justify-center gap-2 btn>
        <a href="https://discord.gg/3HAHYXsgPy"> Join Discord</a>
        <div i-carbon:logo-discord />
      </button>
    </div>
  </section>
</template>
