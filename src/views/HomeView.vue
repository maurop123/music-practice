<script setup lang="ts">
import { ref } from 'vue'

const randomKey = ref<string>('Eb')
const randomScale = ref<string>('Pentatonic')
const scales = ['Major', 'Minor', 'Pentatonic']
const keys = [
  'A',
  'B',
  'C',
  'D',
  'E',
  'F',
  'G',
  'A#',
  'C#',
  'D#',
  'F#',
  'G#',
  'Ab',
  'Bb',
  'Db',
  'Eb',
  'Gb'
]

function randomize() {
  console.debug('randomize')
  randomKey.value = keys[Math.floor(Math.random() * keys.length)]
  randomScale.value = scales[Math.floor(Math.random() * scales.length)]
}
</script>

<template>
  <main>
    <header />
    <div class="results">
      <p>{{ randomScale }}</p>
      <p>{{ randomKey }}</p>
    </div>
    <button class="main-button" @click="randomize()">Random</button>
  </main>
</template>

<style>
html,
body,
#app,
main {
  height: 100%;
}
</style>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.results {
  text-align: center;
  font-size: 2em;
  color: white;
}

.main-button {
  background-color: transparent;
  color: #00dd00;
  font-size: 1.5em;
  outline: solid 2px #00dd00;
  padding: 1em;
}
</style>
