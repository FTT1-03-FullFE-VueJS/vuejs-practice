<template>
  <div class="container">
    <div class="form-container">
      <form
        :style="{
          marginBottom: '10px'
        }"
        @submit.prevent="addColorHandler"
      >
        <input
          type="text"
          placeholder="Enter the color code vd: #FFFFFF"
          :style="{
            padding: '5px',
            fontSize: '23px',
            marginRight: '10px'
          }"
          v-model="colorValue"
        >
        <button
          type="submit"
          :style="{
            fontSize: '23px',
            padding: '5px',
            cursor: 'pointer',
          }"
        >Add Color</button>
      </form>
    </div>
    <div
      class="content"
      :style="{
        display: 'flex',
      }"
    >
      <div
        class="list-color-btns"
        :style="{
          marginRight: '30px'
        }"
      >
        <button
          v-for="(color, index) in colors"
          :key="index"
          :style="{
            display: 'block',
            marginBottom: '5px',
            padding: '5px',
            fontSize: '23px',
            cursor: 'pointer',
          }"
          type="button"
          :class="{
            'active': index === colorIndexActive
          }"
          @click="changeColorHandler(index)"
          >{{ color }}</button>
      </div>
      <div class="color-preview">
        <div
          class="box-color-preview"
          :style="{
            width: '200px',
            height: '200px',
            backgroundColor: getBackgroundActive,
          }"
        ></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "@vue/reactivity";

/**
 * Danh sách color [#f00, #fff, #ddd], và có một box
 * Khi mà mình click vào những mã màu thì nó sẽ đổ lên cái box
 * Mình sẽ có một cái form để thêm màu
 */
const colorIndexActive = ref(0);
const colorValue = ref('');

const colors = ref([
  '#FF0000',
  '#00FFFF',
  '#FF0000',
  '#00008B'
]);

const getBackgroundActive = computed(() => {
  return colors.value[colorIndexActive.value];
});

const changeColorHandler = (colorIndex) => {
  colorIndexActive.value = colorIndex;
}

const addColorHandler = () => {
  if(colorValue.value.trim().length === 0) {
    alert('Please enter color value before submit!');
  } else {
    colors.value.push(colorValue.value);
    colorValue.value = '';
  }
}

</script>
<style>
button.active {
  background-color: #000;
  color: #fff;
  border: 1px solid #000;
}
</style>
