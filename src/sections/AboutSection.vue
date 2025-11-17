<template>
  <section id="about" class="section" data-reveal>
    <div class="container">
      <h2 class="section-title">Sobre mim</h2>
      <p class="section-subtitle">
        Um pouco da minha trajetória, estudos e foco profissional.
      </p>

      <div class="about-grid">
        <div>
          <p class="about-text">
            Sou estudante de Engenharia de Software e desenvolvedor Front-End em
            formação, com foco em clareza, performance e experiência. Trabalho
            com HTML, CSS, JavaScript, React e Vue, sempre guiado por princípios
            de clareza, eficiência e evolução contínua — pilares essenciais para
            qualquer profissional orientado a resultados. Minha jornada é movida
            por aprendizado consistente e pela prática diária: construo projetos
            independentes para fortalecer lógica, compreender padrões de
            arquitetura e aplicar versionamento de forma responsável. Meu
            compromisso é simples: entregar interfaces que façam sentido para o
            usuário e código que faça sentido para o time.
          </p>

          <ul class="about-list">
            <li>
              <strong>Foco atual:</strong> JavaScript, React, Vue,
              responsividade e boas práticas.
            </li>
            <li>
              <strong>Interesses:</strong> UI/UX, acessibilidade,
              componentização e integração com APIs.
            </li>
            <li>
              <strong>Objetivo:</strong> Atuar como Desenvolvedor Front-End,
              contribuindo para equipes que valorizam tecnologia moderna,
              qualidade e visão de produto.
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

.about-text {
  font-size: 1rem;
  color: var(--color-text-main);
  margin-bottom: 1.5rem;
  line-height: 1.6;
}

.about-list {
  list-style: none;
  padding: 0;
  display: grid;
  gap: 0.75rem;
}

.about-list li strong {
  color: var(--color-accent);
}
</style>
