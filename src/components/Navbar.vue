<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const navItems = [
  { label: "Início", href: "#hero" },
  { label: "Sobre", href: "#about" },
  { label: "Skills", href: "#skills" },
  { label: "Serviços", href: "#services" },
  { label: "Projetos", href: "#projects" },
  { label: "Contato", href: "#contact" },
];

const scrollProgress = ref(0);

const updateProgress = () => {
  const scrollTop = window.scrollY || document.documentElement.scrollTop;
  const docHeight =
    document.documentElement.scrollHeight -
    document.documentElement.clientHeight;

  const progress = docHeight > 0 ? (scrollTop / docHeight) * 100 : 0;
  scrollProgress.value = progress;
};

onMounted(() => {
  window.addEventListener("scroll", updateProgress, { passive: true });
  updateProgress();
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", updateProgress);
});
</script>

<template>
  <header class="navbar">
    <!-- Barra de progresso -->
    <div class="scroll-bar">
      <div
        class="scroll-bar-fill"
        :style="{ width: `${scrollProgress}%` }"
      ></div>
    </div>

    <div class="container navbar-inner">
      <div class="navbar-logo">
        <span class="logo-main">Alexandre</span>
        <span class="logo-second">César</span>
      </div>

      <nav class="navbar-nav">
        <a
          v-for="item in navItems"
          :key="item.href"
          :href="item.href"
          class="nav-link"
        >
          {{ item.label }}
        </a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.navbar {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(15, 15, 18, 0.9);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(198, 255, 0, 0.15);
}

/* Barra de progresso */
.scroll-bar {
  height: 2px;
  width: 100%;
  background: rgba(255, 255, 255, 0.02);
}

.scroll-bar-fill {
  height: 100%;
  background: linear-gradient(
    90deg,
    rgba(198, 255, 0, 0.1),
    rgba(198, 255, 0, 0.9)
  );
  transition: width 0.1s linear;
}

.navbar-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 64px;
}

/* Logo em texto */
.navbar-logo {
  display: flex;
  flex-direction: column;
  line-height: 1;
}

.logo-main {
  font-size: 1rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}

.logo-second {
  font-size: 0.75rem;
  color: var(--color-accent);
  letter-spacing: 0.2em;
  text-transform: uppercase;
}

/* Navegação */
.navbar-nav {
  display: flex;
  gap: 1.5rem;
  align-items: center;
}

.nav-link {
  font-size: 0.9rem;
  color: var(--color-text-muted);
  text-decoration: none;
  transition: color 0.2s ease, transform 0.15s ease;
}

.nav-link:hover {
  color: var(--color-accent);
  transform: translateY(-1px);
}

/* Mobile */
@media (max-width: 768px) {
  .navbar-inner {
    flex-direction: column;
    justify-content: center;
    gap: 0.5rem;
    height: auto;
    padding: 0.75rem 0;
  }

  .navbar-nav {
    flex-wrap: wrap;
    justify-content: center;
    gap: 0.75rem;
  }
}
</style>
