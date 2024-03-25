<script>
export default {
  props: {
    changeable: {
      type: Boolean,
      default: false,
    },
    text: {
      type: String,
      default: 'Night Owl.',
    },
  },
  data() {
    return {
      letters: [],
    }
  },
  watch: {
    text(newVal) {
      this.letters = newVal.split('')
    },
  },
  mounted() {
    this.startTypewriterAnimation()
  },
  methods: {
    startTypewriterAnimation() {
      const animateLetters = () => {
        this.letters.forEach((letter, index) => {
          setTimeout(() => {
            this.letters[index] = letter
          }, index * 100)
        })
        setTimeout(() => {
          this.letters = []
          setTimeout(() => {
            this.letters = this.text.split('')
            animateLetters()
          }, 100)
        }, this.letters.length * 100)
      }
      animateLetters()
    },
  },
}
</script>

<template>
  <div>
    <span v-for="(letter, index) in letters" :key="index" class="inline-block font-bold font-sans icon-btn" :style="{ animationDelay: `${index * 100}ms` }">
      {{ letter }}
    </span>
  </div>
</template>

  <style scoped>
  @keyframes typewriter {
  0% {
    opacity: 0;
    transform: translateY(-10px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

span {
  animation: typewriter 0.5s ease forwards;
}
</style>
