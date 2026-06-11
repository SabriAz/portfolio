<template>
  <section id="skills" class="skills">
    <div class="container">
      <div class="section-header">
        <span class="label">Skills</span>
        <div class="divider"></div>
      </div>
      <div class="cloud">
        <div class="row">
          <div class="tile t1" style="flex:3">Java</div>
          <div class="tile t1" style="flex:4">Angular</div>
          <div class="tile t1" style="flex:3">Flutter</div>
        </div>
        <div class="row">
          <div class="tile t1" style="flex:5">Spring Boot</div>
          <div class="tile t2" style="flex:3">TypeScript</div>
          <div class="tile t2" style="flex:2">Figma</div>
        </div>
        <div class="row">
          <div class="tile t2" style="flex:2">Python</div>
          <div class="tile t2" style="flex:4">HTML & CSS</div>
          <div class="tile t2" style="flex:3">PostgreSQL</div>
          <div class="tile t2" style="flex:2">Dart</div>
        </div>
        <div class="row">
          <div class="tile t3" style="flex:2">Vue</div>
          <div class="tile t3" style="flex:2">React</div>
          <div class="tile t3" style="flex:1">Git</div>
          <div class="tile t3" style="flex:2">Docker</div>
          <div class="tile t3" style="flex:2">Linux</div>
          <div class="tile t3" style="flex:3">REST APIs</div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.skills {
  padding: 7rem 4rem;
  border-top: 1px solid var(--border);
  background: var(--bg2);
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

.divider { flex: 1; height: 1px; background: var(--border); }

.cloud {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.row {
  display: flex;
  gap: 8px;
}

.tile {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  font-weight: 500;
  white-space: nowrap;
  border: 1px solid var(--border);
  background: var(--card);
  color: var(--text);
}

.t1 {
  font-family: var(--font-head);
  font-size: clamp(1.1rem, 2.2vw, 1.5rem);
  font-weight: 600;
  padding: 1.4rem 1rem;
  background: #fdf4ec;
  border-color: #e8c49a;
  color: #7a3e10;
}

.t2 {
  font-family: var(--font-body);
  font-size: clamp(0.8rem, 1.4vw, 0.95rem);
  font-weight: 400;
  padding: 1.1rem 0.75rem;
  color: var(--text);
}

.t3 {
  font-family: var(--font-body);
  font-size: 0.8rem;
  font-weight: 300;
  padding: 0.85rem 0.75rem;
  background: var(--bg2);
  color: var(--muted);
  border-color: var(--border);
}

@media (max-width: 768px) {
  .skills { padding: 5rem 1.75rem; }
  .row { flex-wrap: wrap; }
  .tile { flex: 1 1 40% !important; }
  .t1 { font-size: 1.1rem; padding: 1.1rem 0.75rem; }
  .t2 { font-size: 0.85rem; }
  .t3 { font-size: 0.75rem; }
}
</style>