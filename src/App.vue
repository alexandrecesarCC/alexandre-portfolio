<script setup>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";

import HeroSection from "./sections/HeroSection.vue";
import AboutSection from "./sections/AboutSection.vue";
import SkillsSection from "./sections/SkillsSection.vue";
import ServicesSection from "./sections/ServicesSection.vue";
import ProjectsSection from "./sections/ProjectsSection.vue";
import ContactSection from "./sections/ContactSection.vue";

import { useScrollReveal } from "./composables/useScrollReveal";
useScrollReveal();
</script>

<template>
  <div id="app">
    <Navbar />
    <main>
      <HeroSection />
      <AboutSection />
      <SkillsSection />
      <ServicesSection />
      <ProjectsSection />
      <ContactSection />
    </main>
    <Footer />
  </div>
</template>
