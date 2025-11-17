<template>
  <section id="services" class="section" data-reveal>
    <div class="container">
      <h2 class="section-title">Serviços</h2>
      <p class="section-subtitle">
        O que eu desenvolvo, pratico e estudo dentro do Front-End.
      </p>

      <div class="services-grid">
        <div
          class="service-card"
          v-for="service in services"
          :key="service.title"
        >
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-desc">{{ service.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    title: "Landing pages responsivas",
    desc: "Páginas modernas, rápidas e consistentes em qualquer dispositivo.",
  },
  {
    title: "Interfaces com React e Vue",
    desc: "Componentização, organização e UI moderna.",
  },
  {
    title: "UI com foco em acessibilidade",
    desc: "Experiências intuitivas, inclusivas e centradas no usuário.",
  },
];
</script>

<style scoped>
.services-grid {
  display: grid;
  gap: 1.5rem;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
}

.service-card {
  background: var(--color-bg-card);
  border: 1px solid rgba(198, 255, 0, 0.15);
  padding: 1.5rem;
  border-radius: 1rem;
  transition: border-color 0.2s ease, transform 0.2s ease;
}

.service-card:hover {
  border-color: rgba(198, 255, 0, 0.5);
  transform: translateY(-4px);
}

.service-title {
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
}

.service-desc {
  font-size: 0.9rem;
  color: var(--color-text-muted);
}
</style>
