<template>
  <section id="contact" class="section" data-reveal>
    <div class="container">
      <h2 class="section-title">Contato</h2>
      <p class="section-subtitle">
        Estou em busca de oportunidades como Desenvolvedor Front-End (estágio ou
        júnior) e aberto a conexões com pessoas e equipes que valorizam boas
        práticas, colaboração e evolução constante.
      </p>

      <div class="contact-grid">
        <form class="contact-form" @submit.prevent="onSubmit">
          <div class="field">
            <label for="name">Nome</label>
            <input
              id="name"
              type="text"
              v-model="name"
              placeholder="Seu nome"
              required
            />
          </div>

          <div class="field">
            <label for="email">E-mail</label>
            <input
              id="email"
              type="email"
              v-model="email"
              placeholder="seu@email.com"
              required
            />
          </div>

          <div class="field">
            <label for="subject">Assunto</label>
            <input
              id="subject"
              type="text"
              v-model="subject"
              placeholder="Assunto da mensagem"
              required
            />
          </div>

          <div class="field">
            <label for="message">Mensagem</label>
            <textarea
              id="message"
              rows="4"
              v-model="message"
              placeholder="Como posso te ajudar?"
              required
            ></textarea>
          </div>

          <button type="submit" class="contact-btn">Enviar mensagem</button>

          <p class="contact-hint">
            Deixe sua mensagem — responderei o mais rápido possível.
          </p>
        </form>

        <div class="contact-side">
          <p class="contact-side-title">Redes e contato direto</p>

          <div class="contact-links">
            <a
              href="https://github.com/alexandrecesarCC"
              target="_blank"
              rel="noopener noreferrer"
              class="contact-link-card"
            >
              <div class="contact-icon-circle">
                <svg viewBox="0 0 24 24" class="icon">
                  <path
                    fill="currentColor"
                    d="M12 .5A11.5 11.5 0 0 0 .5 12.3c0 5.2 3.4 9.6 8.2 11.2.6.1.8-.3.8-.6v-2c-3.3.7-4-1.4-4-1.4-.5-1.3-1.2-1.6-1.2-1.6-1-.7.1-.7.1-.7 1.2.1 1.8 1.3 1.8 1.3 1 .1.5 1.8 2.8 1.8 1 0 2-.4 2.8-.7.1-.8.4-1.4.8-1.8-2.7-.3-5.4-1.4-5.4-6.1 0-1.3.5-2.5 1.3-3.3-.1-.3-.6-1.6.1-3.3 0 0 1-.3 3.4 1.3a11 11 0 0 1 6.2 0C19 7 20 7.3 20 7.3c.7 1.7.2 3 .1 3.3.8.8 1.3 2 1.3 3.3 0 4.7-2.8 5.8-5.5 6.1.5.4.9 1.2.9 2.4v3.5c0 .3.2.7.8.6a11.8 11.8 0 0 0 8.4-11.2C23.5 5.8 18.3.5 12 .5Z"
                  />
                </svg>
              </div>
              <div>
                <p class="contact-link-label">GitHub</p>
                <p class="contact-link-sub">Projetos, estudos e código.</p>
              </div>
            </a>

            <a
              href="https://www.linkedin.com/in/alexandrecesardev/"
              target="_blank"
              rel="noopener noreferrer"
              class="contact-link-card"
            >
              <div class="contact-icon-circle">
                <svg viewBox="0 0 24 24" class="icon">
                  <path
                    fill="currentColor"
                    d="M4.98 3.5C4.98 4.88 3.88 6 2.5 6S0 4.88 0 3.5 1.12 1 2.5 1s2.48 1.12 2.48 2.5zM.5 8h4V24h-4V8zm7.98 0h3.82v2.2h.06c.53-1 1.84-2.2 3.8-2.2 4.06 0 4.8 2.67 4.8 6.14V24h-4v-8.2c0-2-.04-4.6-2.8-4.6-2.8 0-3.23 2.2-3.23 4.46V24h-4V8z"
                  />
                </svg>
              </div>
              <div>
                <p class="contact-link-label">LinkedIn</p>
                <p class="contact-link-sub">Rede profissional e conexões.</p>
              </div>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const name = ref("");
const email = ref("");
const subject = ref("");
const message = ref("");

const onSubmit = () => {
  const mailto = `mailto:alexandrecesar.dev@gmail.com?subject=${encodeURIComponent(
    subject.value
  )}&body=${encodeURIComponent(
    `Nome: ${name.value}\nE-mail: ${email.value}\n\nMensagem:\n${message.value}`
  )}`;

  window.location.href = mailto;
};
</script>

<style scoped>
.contact-grid {
  display: grid;
  gap: 2rem;
  grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
  align-items: flex-start;
}

.contact-form {
  background: var(--color-bg-card);
  border-radius: 1rem;
  padding: 1.5rem;
  border: 1px solid rgba(198, 255, 0, 0.15);
}

.field {
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
  margin-bottom: 1rem;
}

label {
  font-size: 0.85rem;
}

input,
textarea {
  background: #101015;
  border-radius: 0.6rem;
  border: 1px solid rgba(255, 255, 255, 0.08);
  padding: 0.6rem 0.75rem;
  font-size: 0.9rem;
  color: var(--color-text-main);
  outline: none;
}

input:focus,
textarea:focus {
  border-color: rgba(198, 255, 0, 0.7);
}

.contact-btn {
  margin-top: 0.5rem;
  font-size: 0.9rem;
  padding: 0.75rem 1.4rem;
  border-radius: 999px;
  border: none;
  background: var(--color-accent);
  color: #111;
  cursor: pointer;
  font-weight: 600;
  transition: transform 0.15s ease, filter 0.2s ease;
}

.contact-btn:hover {
  transform: translateY(-1px);
  filter: brightness(1.05);
}

.contact-hint {
  margin-top: 0.75rem;
  font-size: 0.78rem;
  color: var(--color-text-muted);
}

.contact-side-title {
  font-size: 0.95rem;
  margin-bottom: 0.85rem;
}

.contact-links {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.contact-link-card {
  display: flex;
  gap: 0.75rem;
  align-items: center;
  padding: 0.75rem 0.9rem;
  border-radius: 0.85rem;
  text-decoration: none;
  background: rgba(16, 16, 22, 0.95);
  border: 1px solid rgba(198, 255, 0, 0.15);
  transition: border-color 0.2s ease, transform 0.15s ease, background 0.2s ease;
}

.contact-link-card:hover {
  border-color: rgba(198, 255, 0, 0.6);
  background: rgba(16, 16, 22, 1);
  transform: translateY(-1px);
}

.contact-icon-circle {
  width: 32px;
  height: 32px;
  border-radius: 999px;
  background: #1a1a20;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon {
  width: 18px;
  height: 18px;
  color: var(--color-accent);
}

.contact-link-label {
  font-size: 0.88rem;
}

.contact-link-sub {
  font-size: 0.78rem;
  color: var(--color-text-muted);
}

@media (max-width: 900px) {
  .contact-grid {
    grid-template-columns: minmax(0, 1fr);
  }
}
</style>
