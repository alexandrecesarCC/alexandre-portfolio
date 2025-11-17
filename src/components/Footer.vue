<script setup>
import { ref, onMounted } from "vue";

const currentYear = ref(new Date().getFullYear());
</script>

<template>
  <footer class="footer">
    <div class="footer-inner">
      <p class="footer-text">
        © {{ currentYear }} — Alexandre César · Desenvolvedor Front-End focado
        em interfaces modernas e funcionais.
      </p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  padding: 2.5rem 1.5rem;
  margin-top: 4rem;
  border-top: 1px solid rgba(198, 255, 0, 0.2);
  background: rgba(10, 10, 12, 0.6);
  backdrop-filter: blur(4px);
}

.footer-inner {
  max-width: 1080px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.footer-text {
  width: 100%;
  text-align: center;
  font-size: 0.85rem;
  color: var(--color-text-muted);
  line-height: 1.5;
}

/* Responsivo */
@media (max-width: 600px) {
  .footer {
    padding: 2rem 1rem;
  }

  .footer-text {
    font-size: 0.8rem;
  }
}
</style>
