<template>
  <FloatingButton @toggle="menuOpen = !menuOpen" />
  <MenuPanel v-if="menuOpen" />
</template>

<script setup>
import { ref, onMounted } from 'vue'
import FloatingButton from './components/FloatingButton.vue'
import MenuPanel from './components/MenuPanel.vue'

const menuOpen = ref(false)

onMounted(() => {
  if (localStorage.getItem("contrast") === "on") {
    document.body.style.filter = 'contrast(120%)'
  }
  if (localStorage.getItem("fontsize")) {
    document.body.style.fontSize = localStorage.getItem("fontsize")
  }
  if (localStorage.getItem("font") === "dyslexia") {
    const link = document.createElement("link")
    link.href = "https://cdn.jsdelivr.net/npm/opendyslexic@latest/opendyslexic.css"
    link.rel = "stylesheet"
    document.head.appendChild(link)
    document.body.classList.add("dyslexia-font")
  }
})
</script>
