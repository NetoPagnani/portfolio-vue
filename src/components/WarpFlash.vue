<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const active = ref(false)
let resetTimer = null

function trigger() {
  active.value = false
  requestAnimationFrame(() => {
    active.value = true
    clearTimeout(resetTimer)
    resetTimer = setTimeout(() => {
      active.value = false
    }, 260)
  })
}

onMounted(() => window.addEventListener('warp', trigger))
onUnmounted(() => {
  window.removeEventListener('warp', trigger)
  clearTimeout(resetTimer)
})
</script>

<template>
  <div class="warp" :class="{ 'warp--active': active }" aria-hidden="true"></div>
</template>

<style scoped>
.warp {
  position: fixed;
  inset: 0;
  z-index: 5000;
  pointer-events: none;
  opacity: 0;
  background: radial-gradient(
    circle at 50% 40%,
    rgba(255, 255, 255, 0.5) 0%,
    rgba(63, 225, 230, 0.28) 30%,
    rgba(255, 138, 61, 0.12) 55%,
    transparent 75%
  );
}

.warp--active {
  animation: warp-flash 0.26s ease-out;
}

@keyframes warp-flash {
  0% {
    opacity: 0.9;
    transform: scale(0.98);
  }
  100% {
    opacity: 0;
    transform: scale(1.02);
  }
}
</style>
