<script setup>
defineProps({
  project: { type: Object, required: true },
})
</script>

<template>
  <article class="card panel">
    <span class="card__year">{{ project.year }}</span>
    <h3 class="card__name">{{ project.name }}</h3>
    <p class="card__tagline">{{ project.tagline }}</p>
    <p class="card__description">{{ project.description }}</p>
    <ul class="card__stack">
      <li v-for="tech in project.stack" :key="tech" class="chip">{{ tech }}</li>
    </ul>
    <div class="card__links">
      <a class="btn" :href="project.repoUrl" target="_blank" rel="noopener">Código</a>
      <a v-if="project.liveUrl" class="btn" :href="project.liveUrl" target="_blank" rel="noopener">
        Ver projeto
      </a>
    </div>
  </article>
</template>

<style scoped>
.card {
  position: relative;
  padding: 28px;
  display: flex;
  flex-direction: column;
  transition: border-color 0.15s ease, background-color 0.15s ease;
}

.card__year {
  position: absolute;
  top: 18px;
  right: 20px;
  font-family: var(--font-led);
  font-size: 0.78rem;
  color: var(--cyan);
  text-shadow: 0 0 8px rgba(63, 225, 230, 0.6);
  letter-spacing: 0.04em;
}

.card:hover {
  border-color: var(--cyan);
  background: var(--bg-panel-hover);
  box-shadow: 0 0 22px rgba(63, 225, 230, 0.12);
}

.card__name {
  padding-right: 56px;
  font-family: var(--font-sans);
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--orange);
}

.card__tagline {
  margin-top: 8px;
  color: var(--ink);
  font-size: 0.95rem;
  font-weight: 500;
}

.card__description {
  margin-top: 14px;
  color: var(--ink-dim);
  font-size: 0.92rem;
  line-height: 1.65;
  flex-grow: 1;
}

.card__stack {
  margin-top: 18px;
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.card__links {
  margin-top: 20px;
  display: flex;
  gap: 10px;
}
</style>
