<script setup lang="ts">
import SmallApp from './components/SmallApp.vue';
import {ref} from 'vue';
const msg = ref(' Child Component');
</script>

<template>
  <SmallApp :message="'Hello from ' +  msg" :count="0" v-model="msg" />
</template>
