<template>
  <div class="list-post">
    <post-item
      v-for="(post, index) in posts"
      :key="index"
      :index="index + 1"
      :content="post"
    />
  </div>
</template>

<script setup>
import PostItem from './PostItem.vue';
import { defineProps } from 'vue';

const porps = defineProps({
  posts: {
    type: Array,
    // Đối với array or object thì default phải là một function return đúng giá giá mình muốn nhận
    default: []
  }
});
</script>