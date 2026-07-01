<template>
  <section id="hero" class="hero">
    <div class="hero-container">

      <!-- LEFT -->
      <div class="hero-left">
        <p class="eyebrow">Software Engineering Student & Full-Stack Developer</p>

        <h1>
          <span class="line-normal">Hello, I'm</span>
          <span class="line-name">Sabri<span class="accent-dot">.</span></span>
        </h1>

        <p class="desc">
          I build web and mobile applications with a focus on clean design,
          practical solutions, and real-world impact.
        </p>

        <div class="cta-row">
          <a href="#projects" class="btn-primary">View Projects</a>
          <a href="#contact" class="btn-text">Get in touch →</a>
        </div>
      </div>

      <!-- RIGHT -->
      <div class="hero-right">

        <div class="slider">
          <div
              class="slides"
              :style="{ transform: `translateX(-${current * 100}%)` }"
          >
            <img
                v-for="(img, i) in images"
                :key="i"
                :src="img"
                :alt="`Photo ${i + 1}`"
            />
          </div>
          <div class="dots">
            <button
                v-for="n in images.length"
                :key="n"
                :class="['dot-btn', { active: current === n - 1 }]"
                @click="current = n - 1"
            />
          </div>
        </div>
        <div class="bio">
          <p>
            I'm Sabri, a second-year software engineering student at Hogeschool Leiden,
            currently focused on full-stack development.
          </p>

          <p>
            Outside of computer science I'm into music, gaming, and cats. I'm easy to
            work with and focused on clear, practical communication.
          </p>
        </div>

      </div>
    </div>

    <div class="hero-deco">
      <div class="deco-line"></div>
      <span class="deco-label">based in Leiden, NL</span>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import img1 from '@/assets/sabri_1.jpeg'
import img2 from '@/assets/sabri_2.jpeg'
import img3 from '@/assets/sabri_3.jpeg'

const images = [img1, img2, img3]
const current = ref(0)

let timer

function next() {
  current.value = (current.value + 1) % images.length
}

function resetTimer() {
  clearInterval(timer)
  timer = setInterval(next, 9000)
}

onMounted(() => {
  timer = setInterval(next, 9000)
})

onUnmounted(() => {
  clearInterval(timer)
})
</script>

<style scoped>
.hero {
  min-height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  position: relative;
}

.hero-container {
  max-width: 1100px;
  width: 100%;
  margin: 0 auto;
  padding: 0 4rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
}

.hero-left {
  display: flex;
  flex-direction: column;
}

.eyebrow {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  letter-spacing: 0.12em;
  color: var(--accent);
  text-transform: uppercase;
  margin-bottom: 1.5rem;
}

h1 {
  display: flex;
  flex-direction: column;
  margin-bottom: 2rem;
}

.line-normal {
  font-family: var(--font-head);
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  font-weight: 300;
  font-style: italic;
  color: var(--muted);
  line-height: 1.1;
  letter-spacing: -0.02em;
}

.line-name {
  font-family: var(--font-head);
  font-size: clamp(3.5rem, 8vw, 6.5rem);
  font-weight: 600;
  color: var(--text);
  line-height: 0.9;
  letter-spacing: -0.04em;
}

.accent-dot { color: var(--accent); }

.desc {
  font-size: 0.975rem;
  color: var(--muted);
  line-height: 1.8;
  max-width: 420px;
  font-weight: 300;
  margin-bottom: 2.5rem;
}

.cta-row {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.btn-primary {
  background: var(--text);
  color: var(--bg);
  padding: 0.85rem 2rem;
  border-radius: 100px;
  text-decoration: none;
  font-size: 0.875rem;
  font-weight: 500;
}

.btn-primary:hover {
  opacity: 0.8;
  transform: translateY(-1px);
}

.btn-text {
  color: var(--muted);
  text-decoration: none;
  font-size: 0.875rem;
}

.btn-text:hover {
  color: var(--text);
}

.hero-right {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

/* slider */
.slider {
  position: relative;
  overflow: hidden;
  border-radius: 16px;
  width: 100%;
  max-width: 360px;
  aspect-ratio: 4 / 5;
  background: var(--bg3);
}

.slides {
  display: flex;
  height: 100%;
  transition: transform 0.6s cubic-bezier(0.77, 0, 0.18, 1);
}

.slides img {
  min-width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center top;
}

.dots {
  position: absolute;
  bottom: 1rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 6px;
}

.dot-btn {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  border: none;
  background: rgba(255,255,255,0.4);
  cursor: pointer;
}

.dot-btn.active {
  width: 18px;
  background: white;
}

.bio p {
  font-size: 0.875rem;
  color: var(--muted);
  line-height: 1.8;
  font-weight: 300;
  margin-bottom: 0.75rem;
}

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

@media (max-width: 900px) {

  .hero {
    min-height: auto;
    padding: 7rem 0 4rem;
  }

  .hero-container {
    grid-template-columns: 1fr;
    gap: 2.5rem;
    padding: 0 1.75rem;
  }

  .slider {
    max-width: 320px;
    width: 100%;
  }

  .bio {
    text-align: left;
    max-width: 420px;
  }

  .cta-row {
    flex-wrap: wrap;
    gap: 1rem;
  }

  .hero-deco {
    display: none;
  }
}
</style>