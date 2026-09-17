<script setup>
import FluxIcon from './FluxIcon.vue'

const year = new Date().getFullYear()
</script>

<template>
  <footer class="footer">
    <p class="footer__mark"><FluxIcon :size="14" />Orlando Pagnani Neto — {{ year }}</p>
    <p>Construído com Vue 3 e Vite.</p>
  </footer>
</template>

<style scoped>
.footer {
  padding: 28px var(--gutter) 40px;
  max-width: var(--page-max);
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 8px;
  font-family: var(--font-led);
  font-size: 0.8rem;
  color: var(--ink-faint);
}

.footer__mark {
  display: inline-flex;
  align-items: center;
  gap: 8px;
}
</style>
