<script setup>
import BoltIcon from './BoltIcon.vue'

const stack = ['Vue 3', 'TypeScript', 'Tailwind CSS', 'JavaScript', 'Python', 'Flutter', 'Dart']
</script>

<template>
  <section id="sobre" class="about">
    <h2 class="about__heading section-heading"><BoltIcon />Sobre</h2>
    <div class="about__body">
      <p>
        Comecei estudando front-end em cursos práticos — sites institucionais, players de áudio,
        consumo de APIs — e de lá para cá fui trocando HTML e CSS soltos por componentes e estado
        previsível.
      </p>
      <p>
        Hoje trabalho principalmente com Vue 3, e venho estudando Flutter e Dart para levar essas
        mesmas interfaces para o mobile.
      </p>
      <ul class="about__stack">
        <li v-for="item in stack" :key="item" class="chip">{{ item }}</li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: clamp(48px, 8vh, 80px) var(--gutter);
  max-width: var(--page-max);
  margin: 0 auto;
  border-top: 1px solid var(--border);
}

.about__heading {
  font-size: clamp(1.5rem, 3vw, 1.9rem);
  margin-bottom: 26px;
}

.about__body {
  max-width: var(--content-max);
  display: flex;
  flex-direction: column;
  gap: 16px;
  color: var(--ink-dim);
  font-size: 1.02rem;
  line-height: 1.75;
}

.about__body p {
  color: inherit;
}

.about__stack {
  margin-top: 8px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
</style>
