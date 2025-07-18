<template>
  <button class="floating-btn" @click="$emit('toggle')">☰</button>
</template>

<script setup>
// No logic needed here for now
</script>

<style scoped>
.floating-btn {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: black;
  color: white;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  font-size: 24px;
  z-index: 999;
  border: none;
  cursor: pointer;
}
</style>
