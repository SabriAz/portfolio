<template>
  <section id="skills" class="skills">
    <div class="container">

      <div class="section-header">
        <span class="label">Skills</span>
        <div class="divider"></div>
      </div>

      <div class="skills-grid">

        <div class="skill-group">
          <span class="group-label">Advanced</span>
          <div class="row">
            <div class="tile t1">Java</div>
            <div class="tile t1">Angular</div>
            <div class="tile t1">Spring Boot</div>
          </div>
        </div>

        <div class="skill-group">
          <span class="group-label">Intermediate</span>
          <div class="row">
            <div class="tile t2">Flutter</div>
            <div class="tile t2">TypeScript</div>
            <div class="tile t2">HTML & CSS</div>
            <div class="tile t2">PostgreSQL</div>
          </div>
        </div>

        <div class="skill-group">
          <span class="group-label">Familiar</span>
          <div class="row">
            <div class="tile t3">Vue</div>
            <div class="tile t3">React</div>
            <div class="tile t3">Python</div>
            <div class="tile t3">Docker</div>
            <div class="tile t3">Linux</div>
            <div class="tile t3">Git</div>
            <div class="tile t3">REST APIs</div>
            <div class="tile t3">Figma</div>
          </div>
        </div>

      </div>

    </div>
  </section>
</template>

<style scoped>
.skills {
  padding: 7rem 2rem;
  border-top: 1px solid var(--border);
  background: var(--bg2);
}

.container {
  max-width: 1400px;
  margin: 0 auto;
}

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

.skills-grid {
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
}

.skill-group {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.group-label {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--muted);
}

.row {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

/* base tile */
.tile {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  white-space: nowrap;
  border: 1px solid var(--border);
  background: var(--card);
  color: var(--text);
  font-weight: 500;
}

/* strength levels */
.t1 {
  font-family: var(--font-head);
  font-size: 1.2rem;
  font-weight: 600;
  padding: 1.3rem 1rem;
  background: #fdf4ec;
  border-color: #e8c49a;
  color: #7a3e10;
}

.t2 {
  font-family: var(--font-body);
  font-size: 0.95rem;
  padding: 1rem 0.9rem;
}

.t3 {
  font-family: var(--font-body);
  font-size: 0.8rem;
  font-weight: 300;
  padding: 0.75rem 0.75rem;
  color: var(--muted);
  background: var(--bg2);
}

@media (max-width: 768px) {
  .skills {
    padding: 5rem 1.75rem;
  }

  .t1 {
    font-size: 1.1rem;
    padding: 1.1rem 0.75rem;
  }

  .t2 {
    font-size: 0.85rem;
  }

  .t3 {
    font-size: 0.75rem;
  }
}
</style>