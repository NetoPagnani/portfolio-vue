<script setup>
import TimeCircuits from './TimeCircuits.vue'
import DeloreanIcon from './DeloreanIcon.vue'
</script>

<template>
  <section id="top" class="hero">
    <div class="hero__grid-top">
      <div class="hero__text">
        <p class="hero__role">Desenvolvedor Front-end</p>
        <h1 class="hero__name">Orlando Pagnani Neto</h1>
        <p class="hero__bio">
          Construo interfaces com Vue.js — do protótipo à aplicação funcional, cuidando de
          estado, roteamento e dados reais. Venho do front-end clássico com JavaScript, HTML e
          CSS, e hoje estou expandindo para mobile com Flutter.
        </p>
        <div class="hero__actions">
          <a class="btn btn--primary" href="mailto:netopagnani@gmail.com">Enviar e-mail</a>
          <a class="btn" href="https://github.com/NetoPagnani" target="_blank" rel="noopener">GitHub</a>
          <a class="btn" href="https://www.linkedin.com/in/orlandopagnanineto/" target="_blank" rel="noopener">
            LinkedIn
          </a>
        </div>
      </div>

      <div class="hero__circuits-wrap">
        <DeloreanIcon class="hero__car" />
        <TimeCircuits class="hero__circuits" />
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding: clamp(96px, 16vh, 148px) var(--gutter) clamp(56px, 8vh, 88px);
  max-width: var(--page-max);
  margin: 0 auto;
}

.hero__grid-top {
  display: grid;
  grid-template-columns: minmax(0, 1.2fr) minmax(0, 0.8fr);
  gap: clamp(32px, 5vw, 64px);
  align-items: center;
}

.hero__role {
  font-family: var(--font-led);
  font-size: 0.85rem;
  color: var(--cyan);
  margin: 0 0 16px;
}

.hero__name {
  font-size: clamp(2.1rem, 4.6vw, 3.2rem);
  max-width: 16ch;
  letter-spacing: 0.01em;
}

.hero__bio {
  margin-top: 22px;
  max-width: 56ch;
  color: var(--ink-dim);
  font-size: 1.05rem;
  line-height: 1.7;
}

.hero__actions {
  margin-top: 28px;
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.hero__circuits-wrap {
  position: relative;
}

.hero__car {
  position: absolute;
  top: -26px;
  right: 0;
  transform: rotate(-3deg);
}

@media (max-width: 860px) {
  .hero__grid-top {
    grid-template-columns: 1fr;
  }
}
</style>
