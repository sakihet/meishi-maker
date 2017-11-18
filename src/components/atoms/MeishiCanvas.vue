<template lang="pug">
div
  canvas#cv
  // TODO: fix bug
  p(hidden) {{ leftTopTexts }}
  p(hidden) {{ backgroundColor }}
</template>

<script>
export default {
  name: 'MeishiCanvas',
  props: {
    'leftTopTexts': Array,
    'backgroundColor': String
  },
  mounted () {
    this.drawCanvas()
  },
  updated () {
    this.drawCanvas()
  },
  methods: {
    drawCanvas: function () {
      console.log('draw')
      let cv = document.getElementById('cv')
      let ctx = cv.getContext('2d')
      ctx.clearRect(0, 0, 345, 209)
      ctx.fillStyle = this.backgroundColor
      ctx.fillRect(0, 0, 345, 209)
      ctx.fillStyle = '#000000'
      ctx.font = '12px monospace'
      let texts = this.leftTopTexts
      for (let i = 0; i < texts.length; i++) {
        ctx.fillText(texts[i], 20, 20 + i * 12)
      }
    }
  }
}
</script>

<style>
canvas {
  border: 1px solid;
  width: 345px;
  height: 209px;
}
</style>
