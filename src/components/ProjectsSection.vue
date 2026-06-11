<template>
  <section id="projects" class="projects">
    <div class="container">
      <div class="section-header">
        <span class="label">Projects</span>
        <div class="divider"></div>
      </div>
      <div class="projects-list">
        <article v-for="(p, i) in projects" :key="p.title" class="project-row">
          <span class="project-index">{{ String(i + 1).padStart(2, '0') }}</span>
          <div class="project-info">
            <h3>{{ p.title }}</h3>
            <p>{{ p.desc }}</p>
          </div>
          <div class="project-stack">
            <span v-for="s in p.stack" :key="s">{{ s }}</span>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Binbendo',
    desc: 'Full-stack Nintendo-themed webshop. Angular frontend, Spring Boot backend, JWT auth, PostgreSQL database, admin panel, and nginx deployment on a Linux VPS.',
    stack: ['Angular', 'Spring Boot', 'PostgreSQL'],
  },
  {
    title: 'Data Dashboard',
    desc: 'Looker Studio dashboard connected to a Python notebook running K-Means clustering and an LLM API call for automated insight generation.',
    stack: ['Python', 'K-Means', 'Looker Studio'],
  },
  {
    title: 'Educatieve Game',
    desc: 'Mobile educational game built in Flutter for a real client. Intro screens, fade transitions, countdown timers, and usability tested with real participants.',
    stack: ['Flutter', 'Dart'],
  },
  {
    title: 'Portfolio',
    desc: 'This site — designed and built from scratch with Vue 3 and Vite. Clean, warm, and actually readable.',
    stack: ['Vue 3', 'Vite'],
  },
]
</script>

<style scoped>
.projects {
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

.projects-list { display: flex; flex-direction: column; }

.project-row {
  display: grid;
  grid-template-columns: 52px 1fr auto;
  gap: 2rem;
  align-items: start;
  padding: 2.25rem 0;
  border-bottom: 1px solid var(--border);
  transition: background 0.2s;
}

.project-row:first-of-type { border-top: 1px solid var(--border); }

.project-row:hover { background: var(--bg2); margin: 0 -2rem; padding: 2.25rem 2rem; }

.project-index {
  font-family: var(--font-mono);
  font-size: 0.72rem;
  color: var(--border);
  padding-top: 4px;
  letter-spacing: 0.05em;
}

h3 {
  font-family: var(--font-head);
  font-size: 1.3rem;
  font-weight: 400;
  letter-spacing: -0.02em;
  margin-bottom: 0.5rem;
  color: var(--text);
  transition: color 0.2s;
}

.project-row:hover h3 { color: var(--accent); }

.project-info p {
  font-size: 0.875rem;
  color: var(--muted);
  line-height: 1.7;
  font-weight: 300;
  max-width: 520px;
}

.project-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  justify-content: flex-end;
  padding-top: 4px;
}

.project-stack span {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  color: var(--muted);
  padding: 3px 9px;
  border: 1px solid var(--border);
  border-radius: 100px;
  white-space: nowrap;
}

@media (max-width: 768px) {
  .projects { padding: 5rem 1.75rem; }
  .project-row { grid-template-columns: 40px 1fr; }
  .project-stack { display: none; }
  .project-row:hover { margin: 0; padding: 2.25rem 0; background: transparent; }
}
</style>
