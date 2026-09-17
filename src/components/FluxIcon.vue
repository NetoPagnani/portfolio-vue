<script setup>
defineProps({
  size: { type: [Number, String], default: 20 },
})
</script>

<template>
  <svg :width="size" :height="size" viewBox="0 0 24 24" class="flux" aria-hidden="true">
    <circle cx="12" cy="12" r="2.6" class="flux__hub" />
    <g class="flux__arms">
      <line x1="12" y1="12" x2="12" y2="3.2" />
      <line x1="12" y1="12" x2="4.4" y2="16.6" />
      <line x1="12" y1="12" x2="19.6" y2="16.6" />
    </g>
    <circle cx="12" cy="3.2" r="1.6" class="flux__tip" />
    <circle cx="4.4" cy="16.6" r="1.6" class="flux__tip" />
    <circle cx="19.6" cy="16.6" r="1.6" class="flux__tip" />
  </svg>
</template>

<style scoped>
.flux {
  overflow: visible;
  filter: drop-shadow(0 0 4px rgba(255, 138, 61, 0.75));
}

.flux__arms line {
  stroke: var(--orange);
  stroke-width: 1.6;
  stroke-linecap: round;
}

.flux__hub,
.flux__tip {
  fill: var(--orange);
}
</style>
