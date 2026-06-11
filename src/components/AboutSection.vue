<template>
  <section id="about" class="about">
    <div class="container">

      <div class="section-header">
        <span class="label">About</span>
        <div class="divider"></div>
      </div>

      <div class="about-grid">

        <div class="about-text">
          <h2>
            Software engineering student,
            builder, and lifelong learner.
          </h2>

          <p>
            I'm a second-year Software Engineering student at
            Hogeschool Leiden with a strong interest in full-stack
            development and mobile applications.
          </p>

          <p>
            I enjoy turning ideas into usable products, whether that's
            building a webshop, developing a Flutter application, or
            working with backend systems and databases.
          </p>

          <p>
            I enjoy learning new programming languages, frameworks, and tools, and applying them in practical projects. I have a strong focus on continuous learning and improving my understanding of modern software development.

            Languages: Dutch (native), English (fluent).
          </p>
        </div>

        <div class="stats">

          <div class="stat">
            <span class="stat-n">2+</span>
            <span class="stat-l">Years Coding</span>
          </div>

          <div class="stat">
            <span class="stat-n">5+</span>
            <span class="stat-l">Projects Built</span>
          </div>

          <div class="stat">
            <span class="stat-n">HBO</span>
            <span class="stat-l">Software Engineering</span>
          </div>

          <div class="stat">
            <span class="stat-n">Full Stack</span>
            <span class="stat-l">Web & Mobile</span>
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

.container {
  max-width: 1100px;
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

.about-grid {
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 6rem;
}

.about-text h2 {
  font-family: var(--font-head);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 400;
  line-height: 1.2;
  letter-spacing: -0.03em;
  margin-bottom: 2rem;
}

.about-text p {
  color: var(--muted);
  line-height: 1.9;
  font-size: 0.95rem;
  margin-bottom: 1.5rem;
  max-width: 600px;
}

.stats {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  align-content: start;
}

.stat {
  padding-bottom: 1rem;
  border-bottom: 1px solid var(--border);
}

.stat-n {
  display: block;
  font-family: var(--font-head);
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.stat-l {
  font-size: 0.85rem;
  color: var(--muted);
}

@media (max-width: 768px) {

  .about {
    padding: 5rem 1.75rem;
  }

  .about-grid {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .stats {
    grid-template-columns: 1fr 1fr;
  }

}
</style>