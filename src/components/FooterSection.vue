<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-inner">
        <span class="logo"><em>Sabri</em></span>
        <span class="copy">© {{ new Date().getFullYear() }} — Built with Vue 3</span>
        <span class="mono">Hogeschool Leiden</span>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  padding: 2rem 4rem;
  border-top: 1px solid var(--border);
}

.container { max-width: 1100px; margin: 0 auto; }

.footer-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.logo {
  font-family: var(--font-head);
  font-size: 1.1rem;
  font-weight: 400;
  color: var(--text);
}

.copy, .mono {
  font-size: 0.8rem;
  color: var(--muted);
  font-family: var(--font-mono);
  font-weight: 300;
}

@media (max-width: 600px) {
  .footer { padding: 1.75rem; }
  .footer-inner { flex-direction: column; align-items: flex-start; }
}
</style>
