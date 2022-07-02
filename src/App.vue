<template>
  <!-- Page title -->
  <!-- <PageTitle /> -->
  <page-title
    :page-title="title"
  />

  <!-- Form Add Post -->
  <form-add
    placeholder="Please enter post text"
    @onStore="storeNewPostHandler"
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
  {
    id: 1,
    title: 'Lorem ipsum dolor sit amet.',
    description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit, maiores.'
  },
  {
    id: 2,
    title: 'Lorem ipsum dolor sit amet.',
    description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit, maiores.'
  },
  {
    id: 3,
    title: 'Lorem ipsum dolor sit amet.',
    description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit, maiores.'
  },
  {
    id: 4,
    title: 'Lorem ipsum dolor sit amet.',
    description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit, maiores.'
  },
  {
    id: 5,
    title: 'Lorem ipsum dolor sit amet.',
    description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Suscipit, maiores.'
  },
]);

const storeNewPostHandler = ({ title, description }) => {
  posts.value.unshift({
    title: title,
    description: description,
  });
}
</script>
