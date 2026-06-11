<template>
  <section id="about" class="about">
    <div class="container">
      <div class="section-header">
        <span class="label">About</span>
        <div class="divider"></div>
      </div>
      <div class="about-grid">
        <div class="about-left">
          <h2>Building things that<br /><em>actually work.</em></h2>
        </div>
        <div class="about-right">
          <p>
            I'm a second-year HBO Software Engineering student at Hogeschool Leiden.
            I work across the full stack — Angular frontends, Spring Boot backends,
            PostgreSQL databases, and Flutter mobile apps.
          </p>
          <p>
            Outside of code I'm into cooking, gaming (Minecraft, Subnautica) and
            good music. I bring that same curiosity and attention to detail to
            everything I build.
          </p>
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
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 7rem 4rem;
  border-top: 1px solid var(--border);
}

.container { max-width: 1100px; margin: 0 auto; }

.section-header {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 4rem;
}

.label {
  font-family: var(--font-mono);
  font-size: 0.72rem;
  letter-spacing: 0.14em;
  color: var(--muted);
  text-transform: uppercase;
  white-space: nowrap;
}

.divider {
  flex: 1;
  height: 1px;
  background: var(--border);
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 6rem;
  align-items: start;
}

h2 {
  font-family: var(--font-head);
  font-size: clamp(2rem, 3.5vw, 2.8rem);
  font-weight: 400;
  line-height: 1.2;
  letter-spacing: -0.02em;
  color: var(--text);
}

h2 em {
  font-style: italic;
  color: var(--accent);
}

.about-right p {
  font-size: 0.975rem;
  color: var(--muted);
  line-height: 1.85;
  font-weight: 300;
  margin-bottom: 1.25rem;
}

.stats {
  display: flex;
  gap: 2.5rem;
  margin-top: 2.5rem;
  padding-top: 2rem;
  border-top: 1px solid var(--border);
}

.stat {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.stat-n {
  font-family: var(--font-head);
  font-size: 1.75rem;
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
  .about { padding: 5rem 1.75rem; }
  .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
}
</style>
