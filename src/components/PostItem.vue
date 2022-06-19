<template>
  <p>{{ props.index }}. {{ props.content }}</p>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  index: {
    type: Number,
    required: true,
  },
  content: {
    type: String,
    required: true,
  }
})
</script>
