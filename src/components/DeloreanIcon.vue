<template>
  <svg width="112" height="40" viewBox="0 0 118 40" class="car" aria-hidden="true">
    <g class="car__trail">
      <line x1="88" y1="14" x2="80" y2="14" />
      <line x1="92" y1="19" x2="82" y2="19" />
    </g>

    <g class="car__flame">
      <path
        class="car__flame-outer"
        d="M63,29 C79,25.5 98,27 114,31.5 C100,36 74,37 63,34.5 C60.5,32.5 60.5,30.5 63,29 Z"
      />
      <path
        class="car__flame-mid"
        d="M65,30.2 C78,27.8 93,28.8 105,31.8 C92,34.5 73,34.8 65,32.6 Z"
      />
      <path
        class="car__flame-inner"
        d="M67,31.2 C77,29.6 88,30.4 96,32.2 C85,34 72,34.2 67,32.4 Z"
      />
    </g>
    <ellipse class="car__flame-core" cx="65" cy="32.5" rx="4.5" ry="2.4" />

    <path
      class="car__body"
      d="M14 27 V22 H22 L33 11 H54 L64 18 H76 L82 23 V27 Z"
    />
    <path class="car__glass" d="M25 21 L34 12.5 H51 L58 18 Z" />
    <line class="car__seam" x1="43" y1="11" x2="47" y2="18" />
    <path class="car__mirror" d="M23.5 19 L20.5 17.4 L23.5 17.2 Z" />
    <rect class="car__handle" x="45" y="18.6" width="3.2" height="1.1" rx="0.5" />

    <rect class="car__strip" x="16" y="25.2" width="64" height="1.4" rx="0.7" />

    <ellipse class="car__glow" cx="28" cy="31" rx="7" ry="1.6" />

    <g class="car__wheel-group">
      <circle class="car__wheel" cx="28" cy="27" r="6" />
      <g class="car__spokes" transform="translate(28 27)">
        <line x1="0" y1="0" x2="0" y2="-5" />
        <line x1="0" y1="0" x2="4.3" y2="2.5" />
        <line x1="0" y1="0" x2="-4.3" y2="2.5" />
      </g>
      <circle class="car__hub" cx="28" cy="27" r="1.6" />
    </g>
    <g class="car__wheel-group">
      <circle class="car__wheel" cx="68" cy="27" r="6" />
      <g class="car__spokes" transform="translate(68 27)">
        <line x1="0" y1="0" x2="0" y2="-5" />
        <line x1="0" y1="0" x2="4.3" y2="2.5" />
        <line x1="0" y1="0" x2="-4.3" y2="2.5" />
      </g>
      <circle class="car__hub" cx="68" cy="27" r="1.6" />
    </g>
  </svg>
</template>

<style scoped>
.car {
  overflow: visible;
  filter: drop-shadow(0 0 5px rgba(63, 225, 230, 0.4));
}

.car__trail line {
  stroke: var(--cyan);
  stroke-width: 1.4;
  stroke-linecap: round;
  opacity: 0.55;
}

.car__body {
  fill: rgba(180, 200, 210, 0.14);
  stroke: var(--cyan);
  stroke-width: 1.4;
  stroke-linejoin: round;
}

.car__glass {
  fill: rgba(63, 225, 230, 0.22);
  stroke: var(--cyan);
  stroke-width: 0.9;
  stroke-linejoin: round;
}

.car__seam {
  stroke: var(--cyan);
  stroke-width: 0.8;
  opacity: 0.7;
}

.car__mirror {
  fill: var(--cyan);
  opacity: 0.75;
}

.car__handle {
  fill: var(--cyan);
  opacity: 0.6;
}

.car__strip {
  fill: var(--cyan);
  opacity: 0.85;
  filter: drop-shadow(0 0 3px rgba(63, 225, 230, 0.9));
}

.car__glow {
  fill: var(--cyan);
  opacity: 0.18;
}

.car__flame {
  transform-origin: 64px 32px;
  animation: flicker 1.4s ease-in-out infinite;
}

.car__flame-outer {
  fill: var(--orange);
  opacity: 0.5;
  filter: blur(0.5px);
}

.car__flame-mid {
  fill: var(--led-amber);
  opacity: 0.75;
}

.car__flame-inner {
  fill: #fff2c4;
  opacity: 0.9;
}

.car__flame-core {
  fill: #fff8e6;
  opacity: 0.9;
  filter: drop-shadow(0 0 6px rgba(255, 180, 0, 0.85));
}

@keyframes flicker {
  0%,
  100% {
    transform: scaleX(1);
    opacity: 1;
  }
  35% {
    transform: scaleX(1.06);
    opacity: 0.85;
  }
  60% {
    transform: scaleX(0.92);
    opacity: 1;
  }
  80% {
    transform: scaleX(1.03);
    opacity: 0.92;
  }
}

.car__wheel {
  fill: #05070a;
  stroke: var(--cyan);
  stroke-width: 1.3;
}

.car__spokes line {
  stroke: var(--cyan);
  stroke-width: 0.9;
  opacity: 0.75;
}

.car__hub {
  fill: var(--cyan);
}
</style>
