<template>
  <div class="form-container">
    <form action="">
      <input type="text" :placeholder="props.placeholder">
      <button type="submit">Add Post</button>
    </form>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  placeholder: {
    type: String,
    // Bắt buộc component cha phải truyền prop placeholder vào nếu không truyền thì nó sẽ báo lỗi.
    required: true,
  }
});

</script>