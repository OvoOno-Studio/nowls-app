<script setup>
import token from '~/assets/nowlsToken.png'
import road from '~/assets/roadmap.jpg'
</script>

<template>
  <section id="tokenomics" min-h-screen flex-col items-center justify-center gap-20 px-8 py-8 container lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0>
    <div class="w-50 flex items-center justify-center lg:w-1/3" mb-4>
      <img :src="token" alt="Logo">
    </div>
    <div class="z-50 my-4 flex flex-col whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <div mb-4 text-3xl lg:text-6xl xl:text-6xl>
        <h2>
          $NOWLS Tokenomics
        </h2>
        <hr border-1 border-amber-600>
      </div>

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
  </section>
  <section min-h-screen flex-col items-center justify-center gap-4 px-8 py-8 container lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0>
    <div class="z-50 my-4 flex flex-col whitespace-pre-line text-left font-bold font-sans lg:w-1/3">
      <div mb-4 text-3xl lg:text-6xl xl:text-6xl>
        <h2>
          $NOWLS Roadmap
        </h2>
        <hr border-1 border-amber-600>
      </div>
      <ul my-3 pl-0>
        <li xl:text-2xl>
          Trading Tools, RPC Access
        </li>
        <li xl:text-2xl>
          $NOWLS Airdrop
        </li>
        <li xl:text-2xl>
          Access Alpha Channels
        </li>
      </ul>
    </div>
    <img :src="road" mx-auto w-90 border-rounded opacity-50 transition-duration-150 ease hover:opacity-100 alt="Logo">
  </section>
</template>
