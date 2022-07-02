<template>
  <!-- <input
    type="text"
    :placeholder="props.placeholder"
    v-model="postValue"
    @blur="$emit('onChange', postValue)"
  /> -->
  <input
    type="text"
    :placeholder="props.placeholder"
    v-model="postValue"
    @blur="inputBlurHandler"
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

const postValue = ref('');
const postError = ref('');

watch(postValue, (newVal, oldVal) => {
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
const inputBlurHandler = (evt) => {
  // Validate
  if (postValue.value.trim().length === 0) {
    postError.value = 'Post title is required!';
  } else {
    postError.value = '';
    emit('onChange', postValue.value.trim());
  }
}
</script>
