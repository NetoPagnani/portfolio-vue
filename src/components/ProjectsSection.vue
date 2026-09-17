<script setup>
import ProjectRow from './ProjectRow.vue'
import BoltIcon from './BoltIcon.vue'
import { projects } from '../data/projects.js'
</script>

<template>
  <section id="projetos" class="projects">
    <h2 class="projects__heading section-heading"><BoltIcon />Projetos</h2>
    <p class="projects__subtitle">Em ordem cronológica — de 2023 até agora, do JavaScript puro ao Vue 3.</p>
    <div class="projects__grid">
      <ProjectRow v-for="project in projects" :key="project.slug" :project="project" />
    </div>
  </section>
</template>

<style scoped>
.projects {
  padding: clamp(48px, 8vh, 80px) var(--gutter) clamp(24px, 4vh, 40px);
  max-width: var(--page-max);
  margin: 0 auto;
  border-top: 1px solid var(--border);
}

.projects__heading {
  font-size: clamp(1.5rem, 3vw, 1.9rem);
}

.projects__subtitle {
  margin-top: 10px;
  margin-bottom: 26px;
  color: var(--ink-faint);
  font-family: var(--font-led);
  font-size: 0.85rem;
}

.projects__grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 20px;
}

@media (max-width: 760px) {
  .projects__grid {
    grid-template-columns: 1fr;
  }
}
</style>
