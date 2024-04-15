<script setup>
import launch from '~/assets/launch.png'
import image from '~/assets/nowlsImage.jpg'

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
  <section class="mx-auto min-h-screen flex flex-col items-center justify-center gap-20 px-8 py-8 text-left text-black lg:flex md:flex-row space-y-4 lg:px-8 md:px-20 md:space-x-4 md:space-y-0">
    <div class="rounded-xl bg-amber-6 p-8 px-10">
      <div class="py-8">
        <h1 class="text-4xl font-bold">
          Mint yourself an owl
        </h1>
        <hr class="mt-1 border-1 border-black">
      </div>
      <div class="py-4">
        <h2 class="mb-2 text-2xl font-bold">
          Mint Here
        </h2>
        <div id="mint-button-container" />
        <div class="flex items-center">
          <span class="mt-8">Or</span>
        </div>
        <div class="mt-4 py-4">
          <h2 class="mb-2 text-2xl font-bold">
            Mint on Launchmynft.io
          </h2>
          <button class="flex items-center rounded bg-black px-4 py-2 text-sm text-white font-bold hover:bg-stone-900">
            <a href="https://launchmynft.io/collections/5TMT36ueT1om5ZfwzvZpGFAtzJ6S7GTRrckxrUQqU37W/gf3WfCP7uL4J4kV26uEw" target="_blank">Go to Launchmynft.io</a>
            <img :src="launch" class="ml-2 w-8">
          </button>
        </div>
        <div id="mint-counter" class="mt-4" />
      </div>
    </div>
    <div class="mb-4">
      <img :src="image" class="mx-auto w-xs rounded-2xl" alt="Logo">
    </div>
  </section>
</template>
