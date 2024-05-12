<script setup>
import launch from '~/assets/launch.png'

onMounted(() => {
  window.ownerId = '5TMT36ueT1om5ZfwzvZpGFAtzJ6S7GTRrckxrUQqU37W'
  window.collectionId = 'gf3WfCP7uL4J4kV26uEw'

  // Dynamically load the script
  const script = document.createElement('script')
  script.src = 'https://storage.googleapis.com/scriptslmt/0.1.3/solana.js'
  script.type = 'module'
  document.head.appendChild(script)
})
</script>

<template>
  <!-- Include External Stylesheet -->
  <link rel="stylesheet" href="https://storage.googleapis.com/scriptslmt/0.1.3/solana.css">

  <section class="mx-auto min-h-screen flex flex-col items-center justify-center gap-20 px-8 py-8 text-left text-amber-6 lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0">
    <div class="rounded-xl bg-stone-9 p-8 px-10">
      <div class="py-8">
        <h1 class="text-4xl font-bold">
          Get your Night Owl
        </h1>
        <hr class="mt-1 border-1 border-amber-6">
        <br>
        <ul>
          <li> Public mint time: 17th May 4pm UTC </li>
          <li> Public mint price: 11 SEI 20 per wallet </li>
          <li> OG & WL Mint time: 16th May 4pm UTC </li>
          <li> OG & WL Mint price: 6 SEI 10 per wallet </li>
        </ul>
        <br>
        <h2 class="mb-2 text-2xl font-bold">
          Mint SEI Night Owl here
        </h2>
        <button class="flex items-center rounded bg-black px-4 py-2 text-sm text-white font-bold hover:bg-stone-900">
          <a href="https://mint-sei-nowls.vercel.app/" target="_blank">Mint Page</a>
          <img :src="launch" class="ml-2 w-8">
        </button>
      </div>
    </div>
  </section>
  <section>
    <TheNFT min-h-screen @nft-section-visible="startAnimations" />
  </section>
</template>
