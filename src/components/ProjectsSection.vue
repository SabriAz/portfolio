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
            <div class="project-tags">
              <span v-for="s in p.stack" :key="s">{{ s }}</span>
            </div>
            <a v-if="p.link"
            :href="p.link"
            target="_blank"
            rel="noopener"
            class="project-link"
            aria-label="Bekijk project"
            >
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
              <path d="M7 17L17 7M9 7h8v8" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
            </a>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Binbendo | Solo',
    desc: 'Full-stack Nintendo-themed webshop. Angular frontend, Spring Boot backend, JWT auth, PostgreSQL database, and nginx deployment on a self-managed Linux VPS.',
    stack: ['Angular', 'Spring Boot', 'PostgreSQL'],
    link: 'https://binbendo.sabriazzouz.com',
  },
  {
    title: 'Educatieve Game | Team',
    desc: 'Mobile educational game built in Flutter for a real client. Intro screens, fade transitions, countdown timers, and validated through usability testing with real users.',
    stack: ['Flutter', 'Dart'],
    link: 'https://game.sabriazzouz.com',
  },
  {
    title: 'Alrijne | Team',
    desc: 'Mobile information app for Alrijne hospital with a working chatbot for patient questions. Built in Flutter with a Python backend handling the conversational logic.',
    stack: ['Flutter', 'Python'],
  },
  {
    title: 'Data Dashboard | Solo',
    desc: 'Looker Studio dashboard connected to a Python notebook running K-Means clustering, with an LLM API call generating automated insights from the clustered data.',
    stack: ['Python', 'K-Means', 'Looker Studio'],
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
  flex-direction: column;
  align-items: flex-end;
  justify-content: space-between;
  gap: 14px;
  padding-top: 4px;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  justify-content: flex-end;
}

.project-tags span {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  color: var(--muted);
  padding: 3px 9px;
  border: 1px solid var(--border);
  border-radius: 100px;
  white-space: nowrap;
  margin-bottom: 1.5rem;
}

.project-link {
  width: 6rem;
  height: 2.5rem;
  border-radius: 100rem;
  border: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--muted);
  transition: background 0.2s, border-color 0.2s, color 0.2s, transform 0.2s;
  flex-shrink: 0;
}

.project-link svg {
  width: 15px;
  height: 15px;
}

.project-link:hover {
  background: var(--accent);
  border-color: var(--accent);
  color: var(--bg);
  transform: translate(1px, -1px);
}

@media (max-width: 768px) {
  .projects { padding: 5rem 1.75rem; }
  .project-row { grid-template-columns: 40px 1fr; }
  .project-tags { display: none; }
  .project-stack {
    grid-row: 2;
    grid-column: 2;
    flex-direction: row;
    justify-content: flex-end;
    padding-top: 0.5rem;
  }
  .project-row:hover { margin: 0; padding: 2.25rem 0; background: transparent; }
}
</style>
