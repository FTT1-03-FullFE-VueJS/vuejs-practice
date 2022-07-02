<template>
  <p>{{ props.index }}. {{ props.content.title }}</p>
  <p>{{ props.content.description }}</p>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  index: {
    type: Number,
    required: true,
  },
  content: {
    type: Object,
    required: true,
  }
})
</script>
