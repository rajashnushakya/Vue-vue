<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <!-- Bind the click event to increment the count -->
  <button @click="count++">Increment Count: {{ count }}</button>
</template>
