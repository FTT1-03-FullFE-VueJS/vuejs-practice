<template>
  <h1>{{ pageTitle }}</h1>
</template>

<script setup>
import { defineProps } from 'vue';
/**
 * Props: Những dữ liệu truyền từ component cha vào component con thì đều được gọi là props
 */

const props = defineProps({
  pageTitle: {
    type: String,
    default: 'Create new Post default'
  }
});
</script>
