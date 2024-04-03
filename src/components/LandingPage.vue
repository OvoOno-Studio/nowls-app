<script setup>
import { onMounted, ref } from 'vue'
import logofull from '~/assets/owl.gif'
import banner from '~/assets/bannerNOWLS.jpg'
import token from '~/assets/nowlsToken.png'
import image from '~/assets/nowlsImage.jpg'

const progress = ref(0)
const circleLength = 283
const showScrollToTop = ref(false)

function updateProgressCircle() {
  const totalHeight = document.body.scrollHeight - window.innerHeight
  const scrolled = window.pageYOffset
  progress.value = (scrolled / totalHeight) * 100

  const offset = circleLength * (1 - progress.value / 100)
  const circle = document.querySelector('.progress-circle-bar')
  circle.style.strokeDashoffset = offset

  showScrollToTop.value = scrolled > 0.9 * totalHeight
}

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  window.ownerId = '5TMT36ueT1om5ZfwzvZpGFAtzJ6S7GTRrckxrUQqU37W'
  window.collectionId = 'gf3WfCP7uL4J4kV26uEw'

  // Dynamically load the script
  const script = document.createElement('script')
  script.src = 'https://storage.googleapis.com/scriptslmt/0.1.3/solana.js'
  script.type = 'module'
  document.head.appendChild(script)

  updateProgressCircle()
  window.addEventListener('scroll', updateProgressCircle)
})

const sections = [
  { id: 1, text: '$NOWLS', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 2, text: 'NFT + TOKEN ', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 3, text: 'HOOT_HOOT', changeable: true, class: 'text-4xl lg:text-6xl' },
  { id: 4, text: 'NFT_SUPPLY: 2800', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 5, text: '$NOWLS_SUPPLY: 28000000', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 6, text: 'PUBLIC_PRICE: 0.28 SOL', changeable: true, class: 'text-4xl lg:text-7xl' },
  { id: 7, text: 'DOUBLE_REWARDS_WITH_SECOND_PURCHASE', changeable: true, class: 'text-4xl lg:text-6xl' },
  { id: 8, text: 'NEVER_SLEEP', changeable: true, class: 'text-4xl lg:text-6xl' },
]

const slider = sections.slice(0, 9)
const nonslider = sections.slice(5)
</script>

<template>
  <!-- Include External Stylesheet -->
  <link rel="stylesheet" href="https://storage.googleapis.com/scriptslmt/0.1.3/solana.css">

  <!-- progress circle -->
  <div class="progress-circle-container">
    <svg class="progress-circle" viewBox="0 0 100 100">
      <circle class="progress-background" cx="50" cy="50" r="45" />
      <circle :style="{ strokeDashoffset: circleLength - (progress * circleLength / 100) }" class="progress-circle-bar" cx="50" cy="50" r="45" />
    </svg>
    <div class="scroll-to-top" @click="scrollToTop">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M12 19V5M5 12l7-7 7 7" />
      </svg>
    </div>
  </div>
  <!-- SLIDER -->
  <div class="h-screen flex flex-col gap-0 container md:gap-100">
    <template v-for="(section, index) in slider" :key="index">
      <div v-if="section.text" class="content min-h-screen min-w-full flex items-center justify-center" :class="section.class">
        <TypeWritter :text="section.text" :changeable="section.changeable" />
      </div>
    </template>
  </div>

  <!-- HOOT HOOT -->
  <section mx-auto min-h-screen flex flex-col items-center justify-center px-8 py-8 container md:flex-row space-y-4 md:px-20 md:space-x-4 md:space-y-0>
    <div class="z-50 my-4 flex flex-col whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <h2 mb-4 text-3xl lg:text-6xl xl:text-6xl>
        Night Owls
      </h2>
      <ul my-3 pl-0>
        <li xl:text-2xl>
          NFTS Supply: 2800
        </li>
        <li xl:text-2xl>
          Presale: 0.17 SOL
        </li>
        <li xl:text-2xl>
          Public: 0.28 SOL
        </li>
      </ul>
      <p class="dis" mb-4 pl-0 text-white lg:text-lg>
        Night Owls on Solana coming in 2800 unique NFTs. Holding NFT will guarantee access to the optimized trading tools with built-in node access. <br> <br> Each wallet will get airdrop of $NOWLS after the public sale.
      </p>
    </div>
    <div class="lg:w-1/3" mb-4>
      <img :src="logofull" mx-auto alt="Logo">
    </div>
  </section>

  <section mx-auto min-h-screen flex-col items-center justify-center py-4 container lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0>
    <img :src="banner" class="lg:w-2/3" mx-auto border-rounded alt="Logo">
  </section>

  <section mx-auto min-h-screen flex-col items-center justify-center py-8 container lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0>
    <div class="z-50 my-4 flex flex-col whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <h2 mb-4 text-3xl lg:text-6xl xl:text-6xl>
        $NOWLS Tokenomics
      </h2>
      <ul my-3 pl-0>
        <li xl:text-2xl>
          Token Supply: 28,000,000
        </li>
        <li xl:text-2xl>
          Liquidity Pool: 14,000,000
        </li>
        <li xl:text-2xl>
          Holder Airdrop: 12,320,000
        </li>
        <li xl:text-2xl>
          Giveaways: 1,680,000
        </li>
      </ul>
      <p class="dis" mb-4 pl-0 text-white lg:text-lg>
        Profit of sales will go to Liquidity Pool with 14,000,000 $NOWLS token. For holders of Night Owls, 44% of token supply will be airdropped and 6% goes to giveaways.
      </p>
    </div>
    <div class="lg:w-1/3" mb-4>
      <img :src="token" mx-auto alt="Logo">
    </div>
  </section>

  <section mx-auto min-h-screen items-center px-8 container md:flex-row space-y-4 lg:py-4 md:px-20 md:space-x-4 md:space-y-0>
    <img :src="image" mx-auto border-rounded alt="Logo">
    <h2 font-bold lg:px-3 lg:py-5 lg:text-4xl>
      <a href="https://launchmynft.io/collections/5TMT36ueT1om5ZfwzvZpGFAtzJ6S7GTRrckxrUQqU37W/gf3WfCP7uL4J4kV26uEw"> <u>Mint on launchmynft.io </u> </a>
    </h2>
    <div id="mint-button-container" />
    <div id="mint-counter" />
  </section>

  <!-- Flexing 1 -->
  <section v-if="nonslider[0].text" class="min-h-screen flex items-center justify-center">
    <TypeWritter :text="nonslider[0].text" :changeable="nonslider[0].changeable" class="text-4xl lg:text-6xl" />
  </section>
  <!-- NFT Section -->
  <TheNFT @nft-section-visible="startAnimations" />
  <!-- Flexing 2 -->
  <section v-if="nonslider[1].text" class="min-h-screen flex items-center justify-center">
    <TypeWritter :text="nonslider[1].text" :changeable="nonslider[1].changeable" class="text-4xl lg:text-6xl" />
  </section>
</template>
