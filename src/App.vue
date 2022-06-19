<template>
  <!-- Page title -->
  <!-- <PageTitle /> -->
  <page-title
    :page-title="title"
  />

  <!-- Form Add Post -->
  <form-add
    placeholder="Please enter post text"
  />

  <!-- List Post -->
  <list-post
    :posts="posts"
  />
</template>

<script setup>
import { ref } from 'vue';
import PageTitle from './components/PageTitle.vue';
import FormAdd from './components/FormAdd.vue';
import ListPost from './components/ListPost.vue';

const title = 'Create new POST';
const posts = ref([
  'Lorem ipsum dolor sit.',
  'Lorem ipsum dolor sit.',
  'Lorem ipsum dolor sit.',
  'Lorem ipsum dolor sit.',
  'Lorem ipsum dolor sit.',
  'Lorem ipsum dolor sit.',
  'Lorem ipsum dolor sit.',
])
</script>
