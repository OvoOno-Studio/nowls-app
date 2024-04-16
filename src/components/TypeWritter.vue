<script>
export default {
  props: {
    text: {
      type: String,
      default: 'Welcome to Night Owls',
    },
  },
  mounted() {
    this.animateText()
  },
  methods: {
    animateText() {
      const text = this.text
      const span = this.$refs.animatedText
      let index = 0

      function animate() {
        if (index < text.length) {
          span.textContent += text.charAt(index)
          index++
          setTimeout(animate, 100)
        }
      }

      animate()
    },
  },
}
</script>

<template>
  <div>
    <span ref="animatedText" class="animated-text" />
  </div>
</template>

<style scoped>
.animated-text {
  overflow: hidden;
  white-space: nowrap;
}
</style>
