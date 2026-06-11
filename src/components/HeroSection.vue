<template>
  <section id="hero" class="hero">
    <div class="hero-inner">
      <p class="eyebrow">Full-stack developer & student</p>
      <h1>
        <span class="line-normal">Hello, I'm</span>
        <span class="line-name">Sabri<span class="dot">.</span></span>
      </h1>
      <p class="desc">
        I build full-stack web apps and mobile experiences —<br />
        thoughtful code, clean interfaces, real results.
      </p>
      <div class="cta-row">
        <a href="#projects" class="btn-primary">See my work</a>
        <a href="#contact" class="btn-text">Get in touch →</a>
      </div>
    </div>
    <div class="hero-deco">
      <div class="deco-line"></div>
      <span class="deco-label">based in Leiden, NL</span>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 10rem 4rem 6rem;
  max-width: 1100px;
  margin: 0 auto;
  position: relative;
}

.eyebrow {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  letter-spacing: 0.12em;
  color: var(--accent);
  text-transform: uppercase;
  margin-bottom: 1.5rem;
  animation: fadeUp 0.6s ease both;
}

h1 {
  display: flex;
  flex-direction: column;
  margin-bottom: 2rem;
  animation: fadeUp 0.6s 0.1s ease both;
}

.line-normal {
  font-family: var(--font-head);
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 300;
  font-style: italic;
  color: var(--muted);
  line-height: 1.1;
  letter-spacing: -0.02em;
}

.line-name {
  font-family: var(--font-head);
  font-size: clamp(5rem, 13vw, 10rem);
  font-weight: 600;
  color: var(--text);
  line-height: 0.9;
  letter-spacing: -0.04em;
}

.dot { color: var(--accent); }

.desc {
  font-size: 1.05rem;
  color: var(--muted);
  line-height: 1.8;
  max-width: 480px;
  font-weight: 300;
  margin-bottom: 3rem;
  animation: fadeUp 0.6s 0.2s ease both;
}

.cta-row {
  display: flex;
  align-items: center;
  gap: 2rem;
  animation: fadeUp 0.6s 0.3s ease both;
}

.btn-primary {
  background: var(--text);
  color: var(--bg);
  padding: 0.85rem 2rem;
  border-radius: 100px;
  text-decoration: none;
  font-size: 0.875rem;
  font-weight: 500;
  letter-spacing: 0.02em;
  transition: opacity 0.2s, transform 0.2s;
}

.btn-primary:hover { opacity: 0.8; transform: translateY(-1px); }

.btn-text {
  color: var(--muted);
  text-decoration: none;
  font-size: 0.875rem;
  font-weight: 400;
  transition: color 0.2s;
}

.btn-text:hover { color: var(--text); }

.hero-deco {
  position: absolute;
  bottom: 3rem;
  right: 4rem;
  display: flex;
  align-items: center;
  gap: 12px;
}

.deco-line {
  width: 40px;
  height: 1px;
  background: var(--border);
}

.deco-label {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  color: var(--muted);
  letter-spacing: 0.1em;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@media (max-width: 768px) {
  .hero { padding: 8rem 1.75rem 5rem; }
  .hero-deco { display: none; }
}
</style>
