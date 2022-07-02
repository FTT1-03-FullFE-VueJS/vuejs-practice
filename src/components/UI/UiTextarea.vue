<template>
  <textarea
    name="" id=""
    cols="30"
    rows="5"
    :placeholder="props.placeholder"
    v-model="postDescription"
    @blur="textareaBlurHandler"
  />
  <p v-if="!!postError.length">{{ postError }}</p>
</template>

<script setup>
import { defineProps, ref, watch, defineEmits } from 'vue';

const props = defineProps({
  placeholder: {
    type: String,
    default: ''
  }
});

const emit = defineEmits(['onChange']);

const postDescription = ref('');
const postError = ref('');

watch(postDescription, (newVal, oldVal) => {
  console.log({
    newVal,
    oldVal,
  });
});

/**
 * Handle emit value when blur.
 * @param {object} evt
 * @returns {void}
 */
const textareaBlurHandler = (evt) => {
  if (postDescription.value.trim().length === 0) {
    postError.value = 'Post description is required';
  } else {
    postError.value = '';
    emit('onChange', postDescription.value.trim());
  }
}
</script>
