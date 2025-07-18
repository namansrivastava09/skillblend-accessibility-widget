<template>
  <div class="panel">
    <h3>Accessibility Tools</h3>
    <button @click="toggleContrast">Contrast+</button>
    <button @click="increaseFont">Bigger Text</button>
    <button @click="enableDyslexiaFont">Dyslexia Font</button>
  </div>
</template>

<script setup>
function toggleContrast() {
  document.body.style.filter = 'contrast(120%)';
  localStorage.setItem("contrast", "on");
}

function increaseFont() {
  document.body.style.fontSize = '1.3rem';
  localStorage.setItem("fontsize", "1.3rem");
}

function enableDyslexiaFont() {
  const link = document.createElement("link");
  link.href = "https://cdn.jsdelivr.net/npm/opendyslexic@latest/opendyslexic.css";
  link.rel = "stylesheet";
  document.head.appendChild(link);
  document.body.classList.add("dyslexia-font");
  localStorage.setItem("font", "dyslexia");
}
</script>

<style scoped>
.panel {
  position: fixed;
  bottom: 80px;
  right: 20px;
  background: #f5f5f5;
  padding: 1rem;
  border-radius: 10px;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.1);
  z-index: 999;
}
button {
  display: block;
  margin: 8px 0;
  width: 100%;
  padding: 8px;
  border: none;
  background-color: black;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}
</style>
