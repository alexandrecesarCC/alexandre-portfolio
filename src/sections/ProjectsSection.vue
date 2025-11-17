<template>
  <section id="projects" class="section" data-reveal>
    <div class="container">
      <h2 class="section-title">Projetos</h2>
      <p class="section-subtitle">
        Alguns projetos que mostram meu estilo de desenvolvimento, foco em
        clareza, performance e experiência de alto nível.
      </p>

      <div class="projects-grid">
        <article
          v-for="project in projects"
          :key="project.title"
          class="project-card"
        >
          <div class="project-thumb">
            <img
              v-if="project.image"
              :src="project.image"
              :alt="project.title"
              class="project-img"
            />
          </div>

          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-desc">{{ project.desc }}</p>

            <div class="project-tags">
              <span v-for="tag in project.tags" :key="tag" class="project-tag">
                {{ tag }}
              </span>
            </div>

            <div class="project-links">
              <a
                v-if="project.repo"
                :href="project.repo"
                target="_blank"
                rel="noopener noreferrer"
              >
                Código
              </a>
              <a
                v-if="project.demo"
                :href="project.demo"
                target="_blank"
                rel="noopener noreferrer"
              >
                Live
              </a>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "Barbershop — Plataforma em construção",
    desc: "Landing page responsiva com foco em UI/UX, construída para treinar HTML, CSS e JavaScript em um layout dark e moderno.",
    tags: ["Responsivo", "UI/UX", "Landing Page"],
    image: "/projects/barbearia.png",
    demo: "",
    repo: "",
  },
  {
    title: "Zarpli Empregos — Plataforma em construção",
    desc: "Projeto autoral com foco em impacto social, conectando jovens a oportunidades. Em constante evolução, explorando layout, UI e futura integração com APIs.",
    tags: ["Projeto autoral", "Impacto social"],
    image: "/projects/zarpli.png",
    demo: "",
    repo: "",
  },
];
</script>

<style scoped>
.projects-grid {
  display: grid;
  gap: 1.75rem;
  grid-template-columns: minmax(0, 1fr);
}

.project-card {
  display: grid;
  grid-template-columns: minmax(0, 1.3fr) minmax(0, 2fr);
  gap: 1.5rem;
  background: var(--color-bg-card);
  border-radius: 1.25rem;
  padding: 1.5rem;
  border: 1px solid rgba(198, 255, 0, 0.15);
  transition: border-color 0.2s ease, transform 0.2s ease, box-shadow 0.2s ease;
}

.project-card:hover {
  border-color: rgba(198, 255, 0, 0.5);
  transform: translateY(-4px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.75);
}

.project-thumb {
  border-radius: 1rem;
  overflow: hidden;
  background: linear-gradient(135deg, #181820, #0d0d12);
  display: flex;
  align-items: center;
  justify-content: center;
}

.project-img {
  width: 100%;
  display: block;
  object-fit: cover;
}

.project-content {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.project-title {
  font-size: 1.1rem;
}

.project-desc {
  font-size: 0.9rem;
  color: var(--color-text-muted);
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.4rem;
}

.project-tag {
  font-size: 0.75rem;
  padding: 0.2rem 0.7rem;
  border-radius: 999px;
  border: 1px solid rgba(198, 255, 0, 0.5);
}

.project-links {
  display: flex;
  gap: 1rem;
  font-size: 0.85rem;
}

.project-links a {
  color: var(--color-accent);
  text-decoration: none;
}

.project-links a:hover {
  text-decoration: underline;
}

/* Mobile */
@media (max-width: 900px) {
  .project-card {
    grid-template-columns: minmax(0, 1fr);
  }
}
</style>
