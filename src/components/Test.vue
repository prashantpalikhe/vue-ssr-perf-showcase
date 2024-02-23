<script setup lang="ts">
import { ref, watch } from 'vue'
await Promise.resolve()
const thing = ref('')
watch(thing, () => {})
</script>

<template>
  <div>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ratione doloribus
    consectetur sint hic odit neque iusto ex vitae quaerat cupiditate sequi
    magni, voluptates nobis voluptatem aliquid! Iste voluptatibus accusantium
    animi?
  </div>
</template>
