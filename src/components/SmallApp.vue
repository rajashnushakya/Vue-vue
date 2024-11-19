<script setup lang="ts">
import { ref } from 'vue';

// Define props with optional values
const props = defineProps<{
  message?: string;
  count?: number;
}>();

// Initialize a reactive local count with a default value
const count = ref(props.count ?? 0);

// Increment local count
const incrementCount = () => {
  count.value++;
};
</script>

<template>
  <div>
    <!-- Button to increment the count -->
    <button @click="incrementCount">Increment Count: {{ count }}</button>
    <div class="ch">
      <h1>I am the child component</h1>
    </div>
    <p>Message: {{ message ?? 'No message provided' }}</p> 
    <p>Count: {{ count }}</p>
  </div>
</template>

<style>
.ch h1 {
  font-size: 20px;
  font-family: 'Times New Roman';
  color: blue;
}
</style>
