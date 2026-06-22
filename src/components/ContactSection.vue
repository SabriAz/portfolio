<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="section-header">
        <span class="label">Contact</span>
        <div class="divider"></div>
      </div>
      <div class="contact-grid">
        <div class="contact-left">
          <h2>Let's build<br /><em>something good.</em></h2>
          <p>Open to internships, freelance work, and collaborations. Feel free to reach out.</p>
          <div class="links">
            <a href="mailto:sabri@sabriazzouz.com" class="link-row">
              <span class="link-label">Email</span>
              <span class="link-val"> →</span>
            </a>
            <a href="https://github.com/SabriAz" target="_blank" rel="noopener" class="link-row">
              <span class="link-label">GitHub</span>
              <span class="link-val"> →</span>
            </a>
            <a href="https://linkedin.com/in/sabri-azzouz" target="_blank" rel="noopener" class="link-row">
              <span class="link-label">LinkedIn</span>
              <span class="link-val"> →</span>
            </a>
          </div>
        </div>
        <form class="contact-form" @submit.prevent="handleSubmit">
          <div class="field">
            <label>Name</label>
            <input v-model="form.name" type="text" placeholder="Your name" required />
          </div>
          <div class="field">
            <label>Email</label>
            <input v-model="form.email" type="email" placeholder="your@email.com" required />
          </div>
          <div class="field">
            <label>Message</label>
            <textarea v-model="form.message" rows="5" placeholder="Hey Sabri, let's talk..." required></textarea>
          </div>
          <button type="submit" :class="['submit', { sent }]">
            {{ sent ? 'Sent ✓' : 'Send message' }}
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'
const form = reactive({ name: '', email: '', message: '' })
const sent = ref(false)
function handleSubmit() {
  sent.value = true
  setTimeout(() => {
    sent.value = false
    form.name = ''; form.email = ''; form.message = ''
  }, 3000)
}
</script>

<style scoped>
.contact {
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

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 6rem;
  align-items: start;
}

h2 {
  font-family: var(--font-head);
  font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 400;
  line-height: 1.15;
  letter-spacing: -0.03em;
  margin-bottom: 1.25rem;
}

h2 em { font-style: italic; color: var(--accent); }

.contact-left p {
  font-size: 0.95rem;
  color: var(--muted);
  font-weight: 300;
  line-height: 1.8;
  margin-bottom: 2.5rem;
}

.links { display: flex; flex-direction: column; }

.link-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.9rem 0;
  border-bottom: 1px solid var(--border);
  text-decoration: none;
  transition: padding-left 0.2s;
}

.link-row:first-child { border-top: 1px solid var(--border); }
.link-row:hover { padding-left: 0.5rem; }

.link-label {
  font-family: var(--font-mono);
  font-size: 0.72rem;
  letter-spacing: 0.1em;
  color: var(--muted);
  text-transform: uppercase;
}

.link-val {
  font-size: 0.875rem;
  color: var(--text);
  font-weight: 300;
}

.contact-form { display: flex; flex-direction: column; gap: 1.5rem; }

.field { display: flex; flex-direction: column; gap: 8px; }

label {
  font-family: var(--font-mono);
  font-size: 0.7rem;
  letter-spacing: 0.1em;
  color: var(--muted);
  text-transform: uppercase;
}

input, textarea {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 6px;
  padding: 0.75rem 1rem;
  color: var(--text);
  font-family: var(--font-body);
  font-size: 0.9rem;
  font-weight: 300;
  resize: vertical;
  outline: none;
  transition: border-color 0.2s;
}

input:focus, textarea:focus { border-color: var(--accent); }
input::placeholder, textarea::placeholder { color: var(--border); }

.submit {
  background: var(--text);
  color: var(--bg);
  border: none;
  border-radius: 100px;
  padding: 0.9rem 2rem;
  font-family: var(--font-body);
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
  transition: opacity 0.2s, transform 0.2s;
  align-self: flex-start;
  letter-spacing: 0.02em;
}

.submit:hover { opacity: 0.75; transform: translateY(-1px); }
.submit.sent { background: var(--accent); }

@media (max-width: 768px) {
  .contact { padding: 5rem 1.75rem; }
  .contact-grid { grid-template-columns: 1fr; gap: 3rem; }
}
</style>
