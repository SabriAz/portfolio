<template>
  <nav :class="['navbar', { scrolled }]">
    <a href="#hero" class="logo">Sabri</a>
    <div class="links">
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </div>
    <button class="burger" @click="menuOpen = !menuOpen" :aria-expanded="menuOpen">
      <span></span><span></span>
    </button>
    <div :class="['mobile-menu', { open: menuOpen }]" @click="menuOpen = false">
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
const scrolled = ref(false)
const menuOpen = ref(false)
function onScroll() { scrolled.value = window.scrollY > 40 }
onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 2rem 4rem;
  transition: all 0.4s ease;
}

.navbar.scrolled {
  background: rgba(245, 240, 232, 0.92);
  backdrop-filter: blur(16px);
  padding: 1.25rem 4rem;
  border-bottom: 1px solid var(--border);
}

.logo {
  font-family: var(--font-head);
  font-size: 1.2rem;
  font-weight: 400;
  font-style: italic;
  color: var(--text);
  text-decoration: none;
  letter-spacing: -0.01em;
}

.links {
  display: flex;
  gap: 2.5rem;
}

.links a {
  color: var(--muted);
  text-decoration: none;
  font-size: 0.85rem;
  font-weight: 400;
  letter-spacing: 0.03em;
  transition: color 0.2s;
}

.links a:hover { color: var(--text); }

.burger {
  display: none;
  flex-direction: column;
  gap: 6px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.burger span {
  display: block;
  width: 22px;
  height: 1px;
  background: var(--text);
}

.mobile-menu {
  display: none;
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  background: var(--bg);
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2.5rem;
}

.mobile-menu.open { display: flex; }

.mobile-menu a {
  font-family: var(--font-head);
  font-size: 2.5rem;
  font-weight: 300;
  font-style: italic;
  color: var(--text);
  text-decoration: none;
}

@media (max-width: 768px) {
  .links { display: none; }
  .burger { display: flex; }
  .navbar { padding: 1.5rem 1.75rem; }
  .navbar.scrolled { padding: 1.25rem 1.75rem; }
}
</style>
