<template>
  <section id="hero" class="section hero" data-reveal>
    <div class="container hero-inner">
      <div class="hero-text">
        <p class="hero-eyebrow">
          Front-End Developer · JavaScript, React &amp; Vue
        </p>

        <h1 class="hero-title">
          Eu sou
          <span>Alexandre César.</span>
        </h1>

        <p class="hero-subtitle">
          Desenvolvo interfaces modernas com foco em clareza, performance e
          experiência — ajudando produtos a entregarem valor desde o primeiro
          contato.
        </p>

        <div class="hero-actions">
          <a href="#projects" class="hero-btn primary">Ver meus projetos</a>
          <a href="#contact" class="hero-btn ghost">Falar comigo</a>
        </div>
      </div>

      <div class="hero-visual">
        <div class="hero-avatar-wrap">
          <div class="hero-avatar-ring"></div>
          <div class="hero-avatar-inner">
            <img
              src="/alexandre-hero.jpg"
              alt="Foto de Alexandre César"
              class="hero-avatar-img"
            />
          </div>
        </div>

        <div class="hero-badge">
          <p class="hero-badge-title">Front-End · UI/UX</p>
          <p class="hero-badge-sub">
            React · Vue · JavaScript · Layouts responsivos
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  display: flex;
  align-items: center;
  min-height: calc(100vh - 64px);
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: "";
  position: absolute;
  width: 520px;
  height: 520px;
  background: radial-gradient(circle, rgba(198, 255, 0, 0.16), transparent 60%);
  top: -80px;
  right: -120px;
  filter: blur(2px);
  opacity: 0.9;
  pointer-events: none;
}

.hero-inner {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: minmax(0, 1.6fr) minmax(0, 1fr);
  gap: 3rem;
  align-items: center;
}

.hero-eyebrow {
  font-size: 0.85rem;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  color: var(--color-accent);
  margin-bottom: 0.75rem;
}

.hero-title {
  font-size: 2.5rem;
  line-height: 1.1;
  margin-bottom: 1rem;
}

.hero-title span {
  display: block;
  font-size: 3rem;
}

.hero-title,
.hero-subtitle,
.hero-actions {
  animation: heroFadeIn 0.9s var(--ease-out-quint);
  animation-fill-mode: both;
}

.hero-title {
  animation-delay: 0.05s;
}

.hero-subtitle {
  animation-delay: 0.12s;
}

.hero-actions {
  animation-delay: 0.2s;
}

.hero-subtitle {
  font-size: 0.98rem;
  color: var(--color-text-muted);
  max-width: 32rem;
  margin-bottom: 2rem;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.hero-btn {
  font-size: 0.9rem;
  padding: 0.85rem 1.6rem;
  border-radius: 999px;
  border: 1px solid transparent;
  text-decoration: none;
  cursor: pointer;
  transition: background 0.2s ease, color 0.2s ease, border-color 0.2s ease,
    transform 0.15s ease, box-shadow 0.2s ease;
}

.hero-btn.primary {
  background: var(--color-accent);
  color: #111;
  font-weight: 600;
  box-shadow: 0 0 24px rgba(198, 255, 0, 0.35);
}

.hero-btn.primary:hover {
  transform: translateY(-1px);
  filter: brightness(1.05);
  box-shadow: 0 0 36px rgba(198, 255, 0, 0.45);
}

.hero-btn.ghost {
  border-color: rgba(198, 255, 0, 0.5);
  color: var(--color-text-main);
  background: transparent;
}

.hero-btn.ghost:hover {
  background: rgba(198, 255, 0, 0.08);
  transform: translateY(-1px);
}

.hero-visual {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
  align-items: center;
}

.hero-avatar-wrap {
  position: relative;
  width: 220px;
  height: 220px;
}

.hero-avatar-ring {
  position: absolute;
  inset: 0;
  border-radius: 50%;
  background: conic-gradient(
    from 160deg,
    rgba(198, 255, 0, 0.2),
    rgba(198, 255, 0, 0.7),
    rgba(198, 255, 0, 0.2)
  );
  filter: blur(4px);
  opacity: 0.9;
  animation: ringSpin 10s linear infinite;
}

.hero-avatar-inner {
  position: absolute;
  inset: 10px;
  background: #050507;
  border-radius: 50%;
  overflow: hidden;
  border: 1px solid rgba(198, 255, 0, 0.35);
  box-shadow: 0 0 0 1px #000, 0 16px 40px rgba(0, 0, 0, 0.9);
}

.hero-avatar-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-badge {
  background: rgba(15, 15, 18, 0.95);
  border-radius: 0.85rem;
  padding: 0.9rem 1rem;
  border: 1px solid rgba(198, 255, 0, 0.35);
  font-size: 0.8rem;
  width: 100%;
  max-width: 260px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.hero-badge-title {
  color: var(--color-accent);
  margin-bottom: 0.25rem;
}

.hero-badge-sub {
  color: var(--color-text-muted);
}

@keyframes heroFadeIn {
  from {
    opacity: 0;
    transform: translateY(12px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes ringSpin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@media (max-width: 900px) {
  .hero-inner {
    grid-template-columns: minmax(0, 1fr);
  }

  .hero-visual {
    order: -1;
  }

  .hero-title {
    font-size: 2.1rem;
  }

  .hero-title span {
    font-size: 2.4rem;
  }
}
</style>
