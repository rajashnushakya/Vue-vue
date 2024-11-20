<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

// Define props with optional values
const props = defineProps<{
  message?: string;
  count?: number;
}>();
const model = defineModel()
// Initialize a reactive local count with a default value
const count = ref(props.count ?? 0);

// Increment local count
const incrementCount = () => {
  try {
    count.value++;
    console.log('Button clicked. New count:', count.value); // Log message to the console
  } catch (error) {
    console.error('Error:', error); // Catch and log any error
  }
};

// Set up button click event when the component is mounted
onMounted(() => {
  const button = document.querySelector('button');
  if (button) {
    button.addEventListener('click', incrementCount);
  }
});

// Clean up the event listener when the component is unmounted
onUnmounted(() => {
  const button = document.querySelector('button');
  if (button) {
    button.removeEventListener('click', incrementCount);
  }
});
</script>

<template>
  <div>
    <!-- Button to increment the count and log message -->
    <button>Increment Count: {{ count }}</button> 
    <div class="ch">
      <h1>Write a message :<input v-model="model"></h1>
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
