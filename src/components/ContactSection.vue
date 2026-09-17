<script setup></script>

<template>
  <section id="contato" class="contact">
    <div class="contact__panel panel">
      <h2 class="contact__heading">Vamos conversar</h2>
      <p class="contact__text">
        Gosto de trocar ideia sobre projetos em Vue.js e front-end. A forma mais direta de falar
        comigo é por e-mail.
      </p>
      <div class="contact__actions">
        <a class="btn btn--primary" href="mailto:netopagnani@gmail.com">netopagnani@gmail.com</a>
        <a class="btn" href="https://github.com/NetoPagnani" target="_blank" rel="noopener">GitHub</a>
        <a class="btn" href="https://www.linkedin.com/in/orlandopagnanineto/" target="_blank" rel="noopener">
          LinkedIn
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: clamp(48px, 8vh, 80px) var(--gutter) clamp(64px, 10vh, 104px);
  max-width: var(--page-max);
  margin: 0 auto;
}

.contact__panel {
  padding: clamp(32px, 5vw, 56px);
  border-color: var(--border-strong);
  box-shadow: 0 0 40px rgba(63, 225, 230, 0.08);
}

.contact__heading {
  font-size: clamp(1.8rem, 3.6vw, 2.4rem);
}

.contact__text {
  margin-top: 16px;
  max-width: 48ch;
  color: var(--ink-dim);
  line-height: 1.7;
}

.contact__actions {
  margin-top: 28px;
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}
</style>
