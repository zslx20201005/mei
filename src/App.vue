<script lang="ts" setup>
import { onMounted } from 'vue'
import { $computed, $ref } from 'vue/macros'

const el = $ref<HTMLCanvasElement>()
const ctx = $computed(() => el!.getContext('2d')!)

function init() {
  ctx.strokeStyle = '#fff'
  ctx.beginPath()
  ctx.moveTo(30, 50)
  ctx.lineTo(150, 100)
  ctx.stroke()
}

function line(x1: number, y1: number, x2: number, y2: number) {
  ctx.beginPath()
  ctx.moveTo(x1, y1)
  ctx.lineTo(x2, y2)
}

onMounted(() => {
  init()
})
</script>

<template>
  <canvas ref="el" width="600" height="600" style="border:1px solid #fff" />
</template>

<style>
body{
  margin: 0;
  background-color: black;
}
</style>
