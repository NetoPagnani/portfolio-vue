<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const now = ref(new Date())
let timer = null

onMounted(() => {
  timer = setInterval(() => {
    now.value = new Date()
  }, 1000)
})

onUnmounted(() => clearInterval(timer))

const MONTHS = [
  'JAN', 'FEV', 'MAR', 'ABR', 'MAI', 'JUN',
  'JUL', 'AGO', 'SET', 'OUT', 'NOV', 'DEZ',
]

function formatDate(date) {
  const day = String(date.getDate()).padStart(2, '0')
  return `${day} ${MONTHS[date.getMonth()]} ${date.getFullYear()}`
}

function formatTime(date) {
  return new Intl.DateTimeFormat('pt-BR', {
    hour: '2-digit',
    minute: '2-digit',
    second: '2-digit',
    hour12: false,
  }).format(date)
}

const rows = [
  { key: 'stack', label: 'Stack atual', tone: 'orange', value: 'VUE.JS · TYPESCRIPT' },
  { key: 'now', label: 'Tempo presente', tone: 'amber', live: true },
  { key: 'next', label: 'Próximo destino', tone: 'cyan', value: 'NOVOS PROJETOS' },
]
</script>

<template>
  <div class="circuits panel">
    <div v-for="row in rows" :key="row.key" class="circuits__row" :class="`circuits__row--${row.tone}`">
      <span class="circuits__label">{{ row.label }}</span>
      <span v-if="row.live" class="circuits__value">
        {{ formatDate(now) }} — {{ formatTime(now) }}
      </span>
      <span v-else class="circuits__value">{{ row.value }}</span>
    </div>
  </div>
</template>

<style scoped>
.circuits {
  padding: 18px clamp(18px, 3vw, 28px);
  background: #060809;
  border: 1px solid var(--border-strong);
  border-radius: 6px;
  box-shadow: inset 0 0 24px rgba(0, 0, 0, 0.6);
}

.circuits__row {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 16px;
  padding: 9px 0;
}

.circuits__row + .circuits__row {
  border-top: 1px solid rgba(160, 200, 210, 0.08);
}

.circuits__label {
  font-family: var(--font-sans);
  font-size: 0.72rem;
  font-weight: 600;
  color: var(--ink-faint);
  white-space: nowrap;
}

.circuits__value {
  font-family: var(--font-led);
  font-size: clamp(0.95rem, 2vw, 1.15rem);
  letter-spacing: 0.04em;
  text-align: right;
}

.circuits__row--orange .circuits__value {
  color: var(--orange);
  text-shadow: 0 0 10px rgba(255, 138, 61, 0.55);
}

.circuits__row--amber .circuits__value {
  color: var(--led-amber);
  text-shadow: 0 0 10px rgba(255, 180, 0, 0.55);
}

.circuits__row--cyan .circuits__value {
  color: var(--cyan);
  text-shadow: 0 0 10px rgba(63, 225, 230, 0.55);
}
</style>
