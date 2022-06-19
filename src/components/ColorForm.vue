<template>
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
</template>

<script setup>
</script>