<script setup lang="ts">
useHead({
  title: 'Night Owls',
  meta: [
    {
      name: 'description',
      content: 'never sleep',
    },
    {
      name: 'theme-color',
      content: () => isDark.value ? '#00aba9' : '#ffffff',
    },
  ],
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: () => preferredDark.value ? '/owlfav.png' : '/owlfav.png',
    },
  ],
})
</script>

<template>
  <RouterView />
</template>
