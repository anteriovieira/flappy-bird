<template>
  <div id="app">
    <canvas ref="flappy" width="288" height="512"></canvas>
  </div>
</template>

<script>
import FlappyBind from './FlappyBird'

export default {
  name: 'app',
  mounted() {
    const cvs = this.$refs.flappy
    const ctx = cvs.getContext('2d')

    const flappy = new FlappyBind(ctx, cvs)

    setTimeout(() => {
      flappy.draw()
    }, 0)

    document.addEventListener('touchstart', (e) => {
      flappy.fly()

      e.preventDefault()
    })

    document.addEventListener('keydown', (e) => {
      flappy.fly()

      e.preventDefault()
    })
  }
}
</script>
