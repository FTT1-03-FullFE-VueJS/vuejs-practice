<template>
  <div class="form-container">
    <form action="" @submit.prevent="storePostHandler">
      <ui-input
        :placeholder="props.placeholder"
        @onChange="titleChangeHandler"
      />
      <br>
      <ui-textarea
        placeholder="Enter the description of the post."
        @onChange="descriptionChangeHandler"
      />
      <br>
      <button type="submit">Add Post</button>
    </form>
  </div>
</template>
<script setup>
import { defineProps, reactive, defineEmits } from 'vue';
import UiInput from './UI/UiInput.vue';
import UiTextarea from './UI/UiTextarea.vue';

const form = reactive({
  title: '',
  description: ''
});

const props = defineProps({
  placeholder: {
    type: String,
    // Bắt buộc component cha phải truyền prop placeholder vào nếu không truyền thì nó sẽ báo lỗi.
    required: true,
  }
});

const emit = defineEmits(['onStore']);

const titleChangeHandler = (value) => {
  form.title = value;
}

const descriptionChangeHandler = (value) => {
  form.description = value;
}

const storePostHandler = () => {
  emit('onStore', form);
}
</script>
