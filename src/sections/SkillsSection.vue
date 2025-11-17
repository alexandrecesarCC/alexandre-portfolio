<template>
  <section id="skills" class="section" data-reveal>
    <div class="container">
      <h2 class="section-title">Skills</h2>
      <p class="section-subtitle">
        Minhas principais tecnologias, fundamentos e áreas de estudo contínuo.
      </p>

      <div class="skills-grid">
        <div class="skill-card" v-for="skill in skills" :key="skill.name">
          <div class="skill-header">
            <div class="skill-icon">
              <span>{{ skill.short }}</span>
            </div>
            <div>
              <h3 class="skill-name">{{ skill.name }}</h3>
              <p class="skill-level">{{ skill.level }}</p>
            </div>
          </div>

          <p class="skill-desc">{{ skill.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skills = [
  {
    name: "JavaScript",
    short: "JS",
    level: "Base sólida",
    desc: "Lógica, DOM, APIs e boas práticas de estrutura.",
  },
  {
    name: "React",
    short: "RE",
    level: "Componentização",
    desc: "Criação de interfaces declarativas e reutilizáveis.",
  },
  {
    name: "Vue.js",
    short: "VUE",
    level: "Estudo diário",
    desc: "Vue 3 + Vite para interfaces modernas.",
  },
  {
    name: "HTML & CSS",
    short: "HT",
    level: "Fundação forte",
    desc: "Semântica, responsividade e layout.",
  },
  {
    name: "UI, UX & Acessibilidade",
    short: "UX",
    level: "Olhar atento",
    desc: "Experiências intuitivas, acessíveis e modernas.",
  },
];
</script>

<style scoped>
.skills-grid {
  display: grid;
  gap: 1.5rem;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
}

.skill-card {
  background: var(--color-bg-card);
  border: 1px solid rgba(198, 255, 0, 0.15);
  padding: 1.5rem;
  border-radius: 1rem;
  transition: transform 0.2s ease, border-color 0.2s ease;
}

.skill-card:hover {
  transform: translateY(-4px);
  border-color: rgba(198, 255, 0, 0.5);
}

.skill-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 0.75rem;
}

.skill-icon {
  width: 48px;
  height: 48px;
  background: #1f1f23;
  border-radius: 12px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #444;
  font-size: 0.9rem;
  font-weight: 600;
  transition: color 0.2s ease, background 0.2s ease;
}

.skill-card:hover .skill-icon {
  background: var(--color-accent);
  color: #111;
}

.skill-name {
  font-size: 1.1rem;
  margin: 0;
}

.skill-level {
  font-size: 0.85rem;
  color: var(--color-text-muted);
}

.skill-desc {
  margin-top: 0.5rem;
  font-size: 0.9rem;
  color: var(--color-text-muted);
}
</style>
