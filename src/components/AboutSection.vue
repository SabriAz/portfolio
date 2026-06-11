<template>
  <section id="about" class="about">
    <div class="container">
      <div class="stats">
        <div class="stat">
          <span class="stat-n">2+</span>
          <span class="stat-l">Years coding</span>
        </div>
        <div class="stat">
          <span class="stat-n">5+</span>
          <span class="stat-l">Projects shipped</span>
        </div>
        <div class="stat">
          <span class="stat-n">HBO</span>
          <span class="stat-l">Hogeschool Leiden</span>
        </div>
        <div class="stat">
          <span class="stat-n">3</span>
          <span class="stat-l">Stacks mastered</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  border-top: 1px solid var(--border);
  padding: 3rem 4rem;
}

.container { max-width: 1100px; margin: 0 auto; }

.stats {
  display: flex;
  gap: 4rem;
  flex-wrap: wrap;
}

.stat { display: flex; flex-direction: column; gap: 4px; }

.stat-n {
  font-family: var(--font-head);
  font-size: 2rem;
  font-weight: 600;
  color: var(--text);
  letter-spacing: -0.03em;
}

.stat-l {
  font-size: 0.78rem;
  color: var(--muted);
  font-weight: 300;
}

@media (max-width: 768px) {
  .about { padding: 2.5rem 1.75rem; }
  .stats { gap: 2rem; }
}
</style>