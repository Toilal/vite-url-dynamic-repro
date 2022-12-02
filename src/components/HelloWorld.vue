<script setup lang="ts">
import { computed, ref } from 'vue'

defineProps<{ msg: string }>()

const vueSvgStaticUrl = computed(() => {
  return new URL(`../assets/vue.svg`, import.meta.url).href
})

const vueSvgDynamicUrl = computed(() => {
  const name = 'vue'
  return new URL(`../assets/${name}.svg`, import.meta.url).href
})

const invalidSvgStaticUrl = computed(() => {
  return new URL(`../assets/invalid.svg`, import.meta.url).href
})

const invalidSvgDynamicUrl = computed(() => {
  const name = 'invalid'
  return new URL(`../assets/${name}.svg`, import.meta.url).href
})

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <h2>vueSvgStaticUrl: {{ vueSvgStaticUrl }}</h2>
  <h2>vueSvgDynamicUrl: {{ vueSvgDynamicUrl }}</h2>

  <br/>

  <h2>invalidSvgStaticUrl: {{ invalidSvgStaticUrl }}</h2>
  <h2>invalidSvgDynamicUrl: {{ invalidSvgDynamicUrl }}</h2>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
  >create-vue</a
  >, the official Vue + Vite starter
  </p>
  <p>
    Install <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a> in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
