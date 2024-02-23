<template>
  <article>
    <Test v-for="i in 2000" :key="i" />
  </article>
</template>

<script setup>
import Test from '../components/Test.vue'
</script>
