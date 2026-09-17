<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)

function onScroll() {
  scrolled.value = window.scrollY > 8
}

onMounted(() => window.addEventListener('scroll', onScroll, { passive: true }))
onUnmounted(() => window.removeEventListener('scroll', onScroll))

function warp() {
  window.dispatchEvent(new Event('warp'))
}
</script>

<template>
  <header class="nav" :class="{ 'nav--scrolled': scrolled }">
    <div class="nav__inner">
      <a href="#top" class="nav__mark" @click="warp">Orlando Pagnani Neto</a>
      <nav class="nav__links">
        <a href="#sobre" @click="warp">Sobre</a>
        <a href="#projetos" @click="warp">Projetos</a>
        <a href="#contato" @click="warp">Contato</a>
        <a
          class="nav__icon"
          href="https://github.com/NetoPagnani"
          target="_blank"
          rel="noopener"
          aria-label="GitHub de Orlando Pagnani Neto"
        >
          <svg viewBox="0 0 16 16" width="18" height="18" fill="currentColor">
            <path
              d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38
              0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13
              -.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66
              .07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15
              -.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09
              2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15
              0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38
              A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8Z"
            />
          </svg>
        </a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 50;
  border-bottom: 1px solid transparent;
  transition: border-color 0.2s ease, background-color 0.2s ease;
}

.nav--scrolled {
  background: rgba(5, 7, 10, 0.9);
  backdrop-filter: blur(8px);
  border-bottom-color: var(--border);
}

.nav__inner {
  max-width: var(--page-max);
  margin: 0 auto;
  padding: 14px var(--gutter);
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  row-gap: 6px;
  gap: 16px;
}

.nav__mark {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: clamp(0.85rem, 1.6vw, 1.05rem);
  text-decoration: none;
  color: var(--cyan);
  letter-spacing: 0.02em;
  text-shadow: 0 0 14px rgba(63, 225, 230, 0.35);
  white-space: nowrap;
}

.nav__links {
  display: flex;
  align-items: center;
  gap: clamp(16px, 3vw, 28px);
}

.nav__links a {
  text-decoration: none;
  color: var(--ink-dim);
  font-size: 0.92rem;
  font-weight: 500;
  transition: color 0.15s ease;
}

.nav__links a:hover {
  color: var(--orange);
}

.nav__icon {
  display: flex;
  color: var(--ink-dim);
}

.nav__icon:hover {
  color: var(--cyan) !important;
}

@media (max-width: 520px) {
  .nav__mark {
    font-size: 0.78rem;
  }
  .nav__links {
    gap: 12px;
  }
  .nav__links a:not(.nav__icon) {
    font-size: 0.82rem;
  }
}
</style>
