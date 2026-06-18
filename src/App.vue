<template>
  <div class="site">

    <nav class="nav" ref="nav">
      <div class="nav-wrap">
        <a href="#top" class="nav-name">łukasz janicki</a>
        <div class="nav-links">
          <a href="#o-mnie">o mnie</a>
          <a href="#projekty">projekty</a>
          <a href="#kontakt">kontakt</a>
        </div>
        <button class="nav-burger" @click="mobileOpen = !mobileOpen" :class="{ open: mobileOpen }">
          <span/><span/><span/>
        </button>
      </div>
      <div class="nav-mobile" :class="{ open: mobileOpen }">
        <a href="#o-mnie" @click="mobileOpen = false">o mnie</a>
        <a href="#projekty" @click="mobileOpen = false">projekty</a>
        <a href="#kontakt" @click="mobileOpen = false">kontakt</a>
      </div>
    </nav>

    <section class="hero" id="top">
      <div class="hero-wrap">
        <div class="hero-left">
          <p class="hero-kicker" ref="kicker">student informatyki / backend dev</p>
          <h1 class="hero-h1" ref="heroTitle">
            <span class="h1-line" ref="line1">Łukasz</span>
            <span class="h1-line accent-line" ref="line2">Janicki</span>
          </h1>
          <p class="hero-bio" ref="heroBio">
            Student 3. roku Akademii Śląskiej i początkujący programista backendowy.
            Tworzę aplikacje głównie w Javie (Spring) i Kotlinie. Aktywnie rozwijam się
            w obszarze integracji rozwiązań AI w nowoczesnym oprogramowaniu.
          </p>
          <div class="hero-btns" ref="heroBtns">
            <a href="#projekty" class="btn-fill">projekty</a>
            <a href="https://github.com/Mafu2k" target="_blank" rel="noreferrer" class="btn-line">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
              github
            </a>
          </div>
        </div>
        <div class="hero-right" ref="heroRight">
          <div class="hero-card">
            <div class="hc-row">
              <span class="hc-label">lokalizacja</span>
              <span class="hc-val">Knurów, śląsk</span>
            </div>
            <div class="hc-row">
              <span class="hc-label">uczelnia</span>
              <span class="hc-val">Akademia Śląska</span>
            </div>
            <div class="hc-row">
              <span class="hc-label">specjalizacja</span>
              <span class="hc-val">aplikacje web&mobile</span>
            </div>

            <div class="hc-divider"/>
            <div class="hc-stack">
              <span v-for="s in coreStack" :key="s" class="hc-tag">{{ s }}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="hero-scroll" ref="heroScroll">
        <span>scroll</span>
        <span class="hs-line"/>
      </div>
    </section>

    <section class="section" id="o-mnie">
      <div class="section-wrap reveal-section">
        <div class="sec-label">o mnie</div>
        <div class="about-grid">
          <div class="about-text">
            <p>
              Student 3. roku Akademii Śląskiej specjalizujący się w backendzie
              (Spring Boot, REST API) oraz rozwiązaniach mobilnych (Kotlin, Flutter).
            </p>
            <p>
              Posiadam zaplecze zawodowe zdobyte w Exorigo-UPOS i Fluor Corporation,
              gdzie pracowałem z infrastrukturą IT oraz narzędziami inżynierskimi.
            </p>
            <p>
              Obecnie moją główną pasją jest praktyczna integracja modeli sztucznej
              inteligencji w aplikacjach.
            </p>
          </div>
          <div class="about-skills">
            <div v-for="cat in skills" :key="cat.name" class="sk-group">
              <p class="sk-name">{{ cat.name }}</p>
              <div class="sk-tags">
                <span v-for="t in cat.tags" :key="t" class="sk-tag">{{ t }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section section-dim">
      <div class="section-wrap reveal-section">
        <div class="sec-label">doświadczenie i edukacja</div>
        <div class="xp-list">
          <div v-for="item in timeline" :key="item.title" class="xp-item reveal-item">
            <div class="xp-meta">
              <span class="xp-type" :class="item.type">{{ item.type === 'edu' ? 'edu' : 'praca' }}</span>
              <span class="xp-period">{{ item.period }}</span>
            </div>
            <div class="xp-body">
              <h3 class="xp-title">{{ item.title }}</h3>
              <p class="xp-org">{{ item.org }}</p>
              <p class="xp-desc">{{ item.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="projekty">
      <div class="section-wrap reveal-section">
        <div class="sec-label">projekty</div>
        <div class="proj-header">
          <h2 class="proj-h2">GitHub</h2>
          <div class="filter-row">
            <button
              v-for="f in filters"
              :key="f"
              class="f-btn"
              :class="{ active: activeFilter === f }"
              @click="activeFilter = f"
            >{{ f }}</button>
          </div>
        </div>
        <div class="proj-grid">
          <a
            v-for="(p, i) in filteredProjects"
            :key="p.title"
            :href="p.link"
            target="_blank"
            rel="noreferrer"
            class="proj-card reveal-item"
            :class="{ 'proj-card--wide': i === 0 && activeFilter === 'Wszystkie' }"
          >
            <div class="pc-top">
              <span class="pc-lang-dot" :style="{ background: langColor(p.lang) }"/>
              <span class="pc-lang mono">{{ p.lang }}</span>
              <span class="pc-date mono">{{ p.updated }}</span>
            </div>
            <h3 class="pc-title">{{ p.title }}</h3>
            <p class="pc-desc">{{ p.desc }}</p>
            <div class="pc-tags">
              <span v-for="t in p.tech" :key="t" class="pc-tag">{{ t }}</span>
            </div>
            <span class="pc-arrow">↗</span>
          </a>
        </div>
      </div>
    </section>

    <section class="section section-dim" id="kontakt">
      <div class="section-wrap reveal-section">
        <div class="sec-label">kontakt</div>
        <div class="contact-wrap">
          <div class="contact-left">
            <h2 class="contact-h2">porozmawiajmy</h2>
            <p class="contact-sub">
              Najszybciej odpowiem na maila. Chętnie porozmawiam o możliwościach
              współpracy lub stażu.
            </p>
          </div>
          <div class="contact-right">
            <a href="mailto:lukijanicki11@gmail.com" class="clink clink--main">
              <span class="clink-label">email</span>
              <span class="clink-val">lukijanicki11@gmail.com</span>
            </a>
            <a href="tel:+48609533901" class="clink">
              <span class="clink-label">telefon</span>
              <span class="clink-val">+48 609 533 901</span>
            </a>
            <a href="https://github.com/Mafu2k" target="_blank" rel="noreferrer" class="clink">
              <span class="clink-label">github</span>
              <span class="clink-val">Mafu2k</span>
            </a>
            <a href="https://linkedin.com/in/łukasz-janicki-b8647b318" target="_blank" rel="noreferrer" class="clink">
              <span class="clink-label">linkedin</span>
              <span class="clink-val">łukasz-janicki-b8647b318</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="footer-wrap">
        <span class="mono muted">© 2026 Łukasz Janicki</span>
        <span class="footer-consent muted">
          Zgoda na przetwarzanie danych osobowych dla celów rekrutacyjnych (RODO).
        </span>
      </div>
    </footer>

  </div>
</template>

<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

export default {

  data() {
    return {
      mobileOpen: false,
      activeFilter: 'Wszystkie',

      coreStack: ['Java', 'Spring Boot', 'Kotlin', 'SQL', 'Docker', 'Git'],

      skills: [
        { name: 'backend', tags: ['Java', 'Spring Boot', 'Kotlin', 'REST API'] },
        { name: 'dane', tags: ['PostgreSQL', 'SQLite', 'Firebase', 'AWS', 'Azure'] },
        { name: 'devops', tags: ['Docker', 'Kubernetes', 'Git / GitHub'] },
        { name: 'frontend', tags: ['React', 'Vue.js', 'JavaScript', 'HTML/CSS'] },
        { name: 'mobilne', tags: ['Flutter', 'Android', 'Kotlin'] },
        { name: 'ai', tags: ['AI Integration', 'NLP', 'Speech Recognition'] },
        { name: '3d / inżynieria', tags: ['SmartPlant 3D', 'Navisworks', 'Blender'] },
        { name: 'narzędzia', tags: ['IntelliJ IDEA', 'Postman', 'Figma'] },
      ],

      timeline: [
        {
          type: 'work',
          title: 'Junior QA Automation Engineer',
          org: 'ING',
          period: 'czerwiec 2026 – teraz',
          desc: 'Na stanowisku Junior QA Automation Engineer w ING zajmuję się tworzeniem i utrzymywaniem automatycznych przypadków testowych w języku Java. Projektuję scenariusze testowe w oparciu o Apache JMeter, a także sporządzam i aktualizuję dokumentację testową. Na co dzień aktywnie uczestniczę w codziennych spotkaniach zespołu (daily) oraz w szkoleniach rozwijających kompetencje techniczne.',
        },
        {
          type: 'work',
          title: 'Associate Design Engineer I',
          org: 'Fluor Corporation',
          period: 'kwiecień 2025 – marzec 2026',
          desc: 'W swojej pracy na stanowisku Associate Design Engineer I w Fluor Corporation zajmowałem się projektowaniem instalacji przy użyciu oprogramowania SmartPlant 3D oraz koordynacją modeli projektowych w środowisku Navisworks oraz na schematach P&ID.',
        },
        {
          type: 'work',
          title: 'Junior Service Technician',
          org: 'Exorigo-UPOS',
          period: 'lipiec – sierpień 2024',
          desc: 'Podczas praktyk w Exorigo-Upos pracowałem w laboratorium serwisowym, gdzie zajmowałem się wdrażaniem, konfiguracją i administracją serwerów opartych na systemie Windows Server oraz Linux. Moje zadania obejmowały również diagnostykę i naprawę sprzętu komputerowego, w tym testowanie oraz serwisowanie urządzeń skanujących marki Honeywell i innych urządzeń.',
        },
        {
          type: 'edu',
          title: 'Inżynieria informatyki',
          org: 'Akademia Śląska, Katowice',
          period: 'październik 2023 – teraz',
          desc: 'Specjalizacja: aplikacje webowe i mobilne. Aktualnie trzeci rok.',
        },
      ],

      projects: [
        {
          title: 'task-app',
          lang: 'Java',
          desc: 'Aplikacja do zarządzania zadaniami. REST API zbudowane w Spring Boocie.',
          tech: ['Java', 'Spring Boot', 'REST API'],
          updated: 'kwi 2026',
          link: 'https://github.com/Mafu2k/task-app',
        },
        {
          title: 'OPSW11',
          lang: 'C#',
          desc: 'Narzędzie desktopowe do optymalizacji Windows 11. Obsługa kilku języków interfejsu, modułowy design.',
          tech: ['C#', '.NET', 'WPF'],
          updated: 'kwi 2026',
          link: 'https://github.com/Mafu2k/OPSW11',
        },
        {
          title: 'WoloPIPE',
          lang: 'HTML',
          desc: 'Strona dla firmy instalacyjno-budowlanej. Responsywny layout, prosta i przejrzysta struktura.',
          tech: ['HTML', 'CSS', 'JS'],
          updated: 'kwi 2026',
          link: 'https://github.com/Mafu2k/WoloPIPE',
        },
        {
          title: 'kon-spaw',
          lang: 'JavaScript',
          desc: 'Strona wizytówka dla firmy konstrukcyjno-spawalniczej.',
          tech: ['JS', 'HTML', 'CSS'],
          updated: 'mar 2026',
          link: 'https://github.com/Mafu2k/kon-spaw',
        },
        {
          title: 'Shinecar44kn',
          lang: 'JavaScript',
          desc: 'Komercyjna strona dla klienta z car detailingu z Knurowa. Wdrożona na żywo.',
          tech: ['JS', 'HTML', 'CSS'],
          updated: 'mar 2026',
          link: 'https://github.com/Mafu2k/Shinecar44kn',
        },
        {
          title: 'Streakify-IOS',
          lang: 'Swift',
          desc: 'Aplikacja iOS do śledzenia nawyków dziennych z seriami i statystykami.',
          tech: ['Swift', 'iOS', 'UIKit'],
          updated: 'mar 2026',
          link: 'https://github.com/Mafu2k/Streakify---IOS',
        },
        {
          title: 'SZA-helpdesk',
          lang: 'Java',
          desc: 'System ticketowy — zarządzanie zgłoszeniami serwisowymi, Spring Boot + PostgreSQL.',
          tech: ['Java', 'Spring Boot', 'PostgreSQL'],
          updated: 'sty 2026',
          link: 'https://github.com/Mafu2k/SZA---helpdesk--v.0.0.1',
        },
        {
          title: 'fakeOLX',
          lang: 'Kotlin',
          desc: 'Klon OLX — platforma ogłoszeniowa z rejestracją, ogłoszeniami i wyszukiwarką.',
          tech: ['Kotlin', 'Spring Boot', 'PostgreSQL'],
          updated: 'sty 2026',
          link: 'https://github.com/Mafu2k/fakeOLX',
        },
        {
          title: 'Finanse-Domowe-Android',
          lang: 'Kotlin',
          desc: 'Aplikacja Android do budżetowania. Kategorie wydatków, historia i wykres miesięczny.',
          tech: ['Kotlin', 'Android', 'SQLite'],
          updated: 'sty 2026',
          link: 'https://github.com/Mafu2k/Finanse-Domowe-Android',
        },
        {
          title: 'Contact-Manager',
          lang: 'JavaScript',
          desc: 'Prosty manager kontaktów w JS — CRUD, localStorage, MIT license.',
          tech: ['JavaScript', 'localStorage'],
          updated: 'sty 2026',
          link: 'https://github.com/Mafu2k/Contact-Manager',
        },
        {
          title: 'aac-app-web',
          lang: 'HTML',
          desc: 'Webowa aplikacja AAC wspierająca komunikację alternatywną.',
          tech: ['HTML', 'CSS', 'JavaScript'],
          updated: 'gru 2025',
          link: 'https://github.com/Mafu2k/aac-app-web',
        },
        {
          title: 'foodpanda-analytics',
          lang: 'JavaScript',
          desc: 'Dashboard analityczny dla platformy gastronomicznej — wykresy i statystyki.',
          tech: ['JavaScript', 'Chart.js'],
          updated: 'lis 2025',
          link: 'https://github.com/Mafu2k/foodpanda-analytics-system',
        },
        {
          title: 'todolist',
          lang: 'Java',
          desc: 'Klasyczna to-do lista w Javie. Jeden z pierwszych projektów ze Spring Bootem.',
          tech: ['Java', 'Spring Boot'],
          updated: 'cze 2025',
          link: 'https://github.com/Mafu2k/todolist',
        },
        {
          title: 'portfolio-v1',
          lang: 'HTML',
          desc: 'Pierwsza wersja portfolio — od tego zaczęło się frontendowe doświadczenie.',
          tech: ['HTML', 'CSS'],
          updated: '2025',
          link: 'https://github.com/Mafu2k/portfolio-v1.0.0.1',
        },
      ],
    }
  },

  computed: {
    filters() {
      return ['Wszystkie', ...new Set(this.projects.map(p => p.lang))]
    },
    filteredProjects() {
      if (this.activeFilter === 'Wszystkie') return this.projects
      return this.projects.filter(p => p.lang === this.activeFilter)
    },
  },

  mounted() {
    this.initNav()
    this.initHero()
    this.initScrollReveal()
  },

  beforeUnmount() {
    ScrollTrigger.getAll().forEach(t => t.kill())
  },

  methods: {
    langColor(lang) {
      const colors = {
        Java: '#f89820',
        Kotlin: '#9b6dff',
        'C#': '#8f44ad',
        JavaScript: '#d4b800',
        HTML: '#c0392b',
        Swift: '#e85d3b',
      }
      return colors[lang] || '#4af0c4'
    },

    initNav() {
      gsap.from(this.$refs.nav, {
        y: -24,
        opacity: 0,
        duration: 0.7,
        ease: 'power2.out',
        delay: 0.1,
      })

      ScrollTrigger.create({
        start: 'top -60',
        onEnter: () => this.$refs.nav.classList.add('nav--scrolled'),
        onLeaveBack: () => this.$refs.nav.classList.remove('nav--scrolled'),
      })
    },

    initHero() {
      const tl = gsap.timeline({ delay: 0.3 })

      tl.from(this.$refs.kicker, {
        opacity: 0,
        y: 16,
        duration: 0.55,
        ease: 'power2.out',
      })
      .from([this.$refs.line1, this.$refs.line2], {
        opacity: 0,
        y: 40,
        duration: 0.65,
        ease: 'power3.out',
        stagger: 0.12,
      }, '-=0.25')
      .from(this.$refs.heroBio, {
        opacity: 0,
        y: 20,
        duration: 0.55,
        ease: 'power2.out',
      }, '-=0.3')
      .from(this.$refs.heroBtns, {
        opacity: 0,
        y: 16,
        duration: 0.5,
        ease: 'power2.out',
      }, '-=0.3')
      .from(this.$refs.heroRight, {
        opacity: 0,
        x: 30,
        duration: 0.7,
        ease: 'power2.out',
      }, '-=0.6')
      .from(this.$refs.heroScroll, {
        opacity: 0,
        duration: 0.5,
      }, '-=0.2')
    },

    initScrollReveal() {
      this.$nextTick(() => {
        gsap.utils.toArray('.reveal-section').forEach(el => {
          const label = el.querySelector('.sec-label')
          const rest = el.querySelectorAll(':scope > *:not(.sec-label)')

          gsap.from(label, {
            opacity: 0,
            x: -20,
            duration: 0.5,
            ease: 'power2.out',
            scrollTrigger: { trigger: el, start: 'top 82%' },
          })
          gsap.from(rest, {
            opacity: 0,
            y: 28,
            duration: 0.6,
            ease: 'power2.out',
            stagger: 0.08,
            scrollTrigger: { trigger: el, start: 'top 78%' },
          })
        })

        gsap.utils.toArray('.reveal-item').forEach(el => {
          gsap.from(el, {
            opacity: 0,
            y: 24,
            duration: 0.55,
            ease: 'power2.out',
            scrollTrigger: { trigger: el, start: 'top 88%' },
          })
        })
      })
    },
  },
}
</script>

<style scoped>
.mono { font-family: var(--mono); }
.muted { color: var(--muted); }
.accent-text { color: var(--accent); }

.nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 99;
  transition: background 0.35s, border-color 0.35s;
  border-bottom: 1px solid transparent;
}

.nav--scrolled {
  background: rgba(13, 13, 13, 0.92);
  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);
  border-color: var(--border);
}

.nav-wrap {
  max-width: 1060px;
  margin: 0 auto;
  padding: 0 24px;
  height: 58px;
  display: flex;
  align-items: center;
  gap: 32px;
}

.nav-name {
  font-size: 0.9rem;
  font-weight: 600;
  color: var(--text);
  letter-spacing: -0.02em;
  margin-right: auto;
}

.nav-links {
  display: flex;
  gap: 24px;
}

.nav-links a {
  font-size: 0.87rem;
  color: var(--muted);
  transition: color 0.2s;
}

.nav-links a:hover { color: var(--text); }

.nav-burger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}

.nav-burger span {
  display: block;
  width: 22px;
  height: 1.5px;
  background: var(--muted2);
  border-radius: 1px;
  transition: transform 0.2s, opacity 0.2s;
}

.nav-burger.open span:nth-child(1) { transform: translateY(6.5px) rotate(45deg); }
.nav-burger.open span:nth-child(2) { opacity: 0; }
.nav-burger.open span:nth-child(3) { transform: translateY(-6.5px) rotate(-45deg); }

.nav-mobile {
  max-height: 0;
  overflow: hidden;
  background: rgba(13, 13, 13, 0.98);
  border-bottom: 1px solid transparent;
  transition: max-height 0.3s ease, border-color 0.3s, padding 0.3s;
  display: flex;
  flex-direction: column;
}

.nav-mobile.open {
  max-height: 220px;
  border-color: var(--border);
  padding: 8px 0;
}

.nav-mobile a {
  padding: 12px 28px;
  font-size: 0.95rem;
  color: var(--muted2);
  transition: color 0.2s;
}

.nav-mobile a:hover { color: var(--text); }

.section-wrap {
  max-width: 1060px;
  margin: 0 auto;
  padding: 0 24px;
}

.section {
  padding: 96px 0;
}

.section-dim {
  background: var(--bg2);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}

.sec-label {
  font-family: var(--mono);
  font-size: 0.75rem;
  color: var(--accent);
  text-transform: uppercase;
  letter-spacing: 3px;
  margin-bottom: 40px;
}

.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 80px 24px 60px;
}

.hero-wrap {
  max-width: 1060px;
  margin: 0 auto;
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 360px;
  gap: 60px;
  align-items: center;
}

.hero-kicker {
  font-family: var(--mono);
  font-size: 0.78rem;
  color: var(--muted);
  letter-spacing: 1.5px;
  margin-bottom: 22px;
}

.hero-h1 {
  display: flex;
  flex-direction: column;
  font-size: clamp(3.2rem, 8vw, 5.6rem);
  font-weight: 700;
  letter-spacing: -0.04em;
  line-height: 0.95;
  margin-bottom: 28px;
  color: var(--text);
}

.accent-line {
  color: var(--accent);
}

.hero-bio {
  font-size: 1rem;
  color: var(--muted2);
  line-height: 1.75;
  max-width: 480px;
  margin-bottom: 36px;
}

.hero-btns {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
}

.btn-fill {
  background: var(--accent);
  color: #0a0a0a;
  font-size: 0.88rem;
  font-weight: 600;
  padding: 11px 26px;
  border-radius: 6px;
  transition: opacity 0.2s, transform 0.2s;
}

.btn-fill:hover {
  opacity: 0.88;
  transform: translateY(-1px);
}

.btn-line {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  border: 1px solid var(--border2);
  color: var(--muted2);
  font-size: 0.88rem;
  font-weight: 500;
  padding: 11px 22px;
  border-radius: 6px;
  transition: border-color 0.2s, color 0.2s;
}

.btn-line:hover {
  border-color: #444;
  color: var(--text);
}

.hero-card {
  background: var(--bg3);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 24px;
}

.hc-row {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 12px;
  margin-bottom: 14px;
}

.hc-label {
  font-family: var(--mono);
  font-size: 0.72rem;
  color: var(--muted);
  letter-spacing: 0.5px;
  flex-shrink: 0;
}

.hc-val {
  font-size: 0.85rem;
  color: var(--muted2);
  text-align: right;
}

.hc-divider {
  height: 1px;
  background: var(--border);
  margin: 18px 0;
}

.hc-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
}

.hc-tag {
  font-family: var(--mono);
  font-size: 0.72rem;
  background: #1a1a1a;
  border: 1px solid var(--border2);
  color: var(--muted2);
  padding: 4px 10px;
  border-radius: 4px;
}

.hero-scroll {
  display: flex;
  align-items: center;
  gap: 14px;
  max-width: 1060px;
  margin: 48px auto 0;
  padding: 0 24px;
}

.hero-scroll span:first-child {
  font-family: var(--mono);
  font-size: 0.7rem;
  color: var(--muted);
  letter-spacing: 2px;
}

.hs-line {
  display: block;
  flex: 1;
  max-width: 80px;
  height: 1px;
  background: linear-gradient(90deg, var(--muted), transparent);
}

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 56px;
  align-items: start;
}

.about-text p {
  color: var(--muted2);
  font-size: 0.97rem;
  line-height: 1.8;
  margin-bottom: 18px;
}

.about-text p:last-child { margin-bottom: 0; }

.sk-group {
  margin-bottom: 22px;
}

.sk-name {
  font-family: var(--mono);
  font-size: 0.72rem;
  color: var(--muted);
  letter-spacing: 1.5px;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.sk-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
}

.sk-tag {
  font-size: 0.8rem;
  color: var(--muted2);
  background: #181818;
  border: 1px solid var(--border);
  padding: 4px 11px;
  border-radius: 4px;
}

.xp-list {
  display: flex;
  flex-direction: column;
  gap: 0;
}

.xp-item {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: 24px;
  padding: 28px 0;
  border-bottom: 1px solid var(--border);
}

.xp-item:first-child {
  border-top: 1px solid var(--border);
}

.xp-meta {
  display: flex;
  flex-direction: column;
  gap: 8px;
  padding-top: 3px;
}

.xp-type {
  font-family: var(--mono);
  font-size: 0.7rem;
  font-weight: 500;
  letter-spacing: 1px;
  text-transform: uppercase;
  display: inline-block;
  padding: 3px 9px;
  border-radius: 3px;
  width: fit-content;
}

.xp-type.work {
  background: rgba(74, 240, 196, 0.08);
  color: var(--accent);
  border: 1px solid rgba(74, 240, 196, 0.2);
}

.xp-type.edu {
  background: rgba(255, 255, 255, 0.04);
  color: var(--muted2);
  border: 1px solid var(--border2);
}

.xp-period {
  font-family: var(--mono);
  font-size: 0.72rem;
  color: var(--muted);
  line-height: 1.4;
}

.xp-title {
  font-size: 1rem;
  font-weight: 600;
  color: var(--text);
  margin-bottom: 4px;
}

.xp-org {
  font-size: 0.87rem;
  color: var(--accent);
  margin-bottom: 10px;
}

.xp-desc {
  font-size: 0.88rem;
  color: var(--muted);
  line-height: 1.75;
}

.proj-header {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 20px;
  margin-bottom: 28px;
  flex-wrap: wrap;
}

.proj-h2 {
  font-size: 1.35rem;
  font-weight: 600;
  color: var(--text);
  letter-spacing: -0.02em;
}

.filter-row {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.f-btn {
  font-family: var(--mono);
  font-size: 0.72rem;
  background: none;
  border: 1px solid var(--border2);
  color: var(--muted);
  padding: 5px 14px;
  border-radius: 4px;
  cursor: pointer;
  transition: border-color 0.18s, color 0.18s, background 0.18s;
  letter-spacing: 0.5px;
}

.f-btn:hover {
  border-color: #444;
  color: var(--muted2);
}

.f-btn.active {
  background: var(--accent);
  border-color: var(--accent);
  color: #0a0a0a;
}

.proj-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 10px;
  overflow: hidden;
}

.proj-card {
  position: relative;
  background: var(--bg);
  padding: 22px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  transition: background 0.2s;
}

.proj-card--wide {
  grid-column: span 2;
}

.proj-card:hover {
  background: var(--bg3);
}

.pc-top {
  display: flex;
  align-items: center;
  gap: 7px;
}

.pc-lang-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  flex-shrink: 0;
}

.pc-lang {
  font-size: 0.72rem;
  color: var(--muted);
  flex: 1;
}

.pc-date {
  font-size: 0.68rem;
  color: var(--muted);
}

.pc-title {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--text);
  letter-spacing: -0.01em;
}

.pc-desc {
  font-size: 0.82rem;
  color: var(--muted);
  line-height: 1.65;
  flex: 1;
}

.pc-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
}

.pc-tag {
  font-family: var(--mono);
  font-size: 0.66rem;
  color: var(--muted);
  background: #181818;
  border: 1px solid var(--border);
  padding: 2px 8px;
  border-radius: 3px;
}

.pc-arrow {
  position: absolute;
  top: 16px;
  right: 18px;
  font-size: 1rem;
  color: var(--muted);
  opacity: 0;
  transition: opacity 0.2s, transform 0.2s;
}

.proj-card:hover .pc-arrow {
  opacity: 1;
  transform: translate(2px, -2px);
}

.contact-wrap {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: start;
}

.contact-h2 {
  font-size: 2rem;
  font-weight: 700;
  color: var(--text);
  letter-spacing: -0.04em;
  margin-bottom: 12px;
}

.contact-sub {
  font-size: 0.92rem;
  color: var(--muted);
  line-height: 1.7;
}

.contact-right {
  display: flex;
  flex-direction: column;
  gap: 0;
}

.clink {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 16px;
  padding: 16px 0;
  border-bottom: 1px solid var(--border);
  transition: background 0.15s;
}

.clink:first-child {
  border-top: 1px solid var(--border);
}

.clink:hover .clink-val {
  color: var(--accent);
}

.clink--main .clink-val {
  font-size: 0.95rem;
  font-weight: 600;
}

.clink-label {
  font-family: var(--mono);
  font-size: 0.7rem;
  color: var(--muted);
  letter-spacing: 1px;
  text-transform: uppercase;
  flex-shrink: 0;
}

.clink-val {
  font-size: 0.88rem;
  color: var(--muted2);
  text-align: right;
  transition: color 0.2s;
  word-break: break-all;
}

.footer {
  border-top: 1px solid var(--border);
  padding: 24px 0;
}

.footer-wrap {
  max-width: 1060px;
  margin: 0 auto;
  padding: 0 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
  font-size: 0.78rem;
}

.footer-consent {
  font-family: var(--mono);
  font-size: 0.68rem;
  color: var(--muted);
  max-width: 520px;
  text-align: right;
}

@media (max-width: 860px) {
  .hero-wrap {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .hero-right {
    display: none;
  }

  .about-grid {
    grid-template-columns: 1fr;
    gap: 36px;
  }

  .proj-grid {
    grid-template-columns: 1fr 1fr;
  }

  .proj-card--wide {
    grid-column: span 2;
  }

  .contact-wrap {
    grid-template-columns: 1fr;
    gap: 36px;
  }
}

@media (max-width: 640px) {
  .nav-links { display: none; }
  .nav-burger { display: flex; }

  .section { padding: 72px 0; }

  .hero-h1 {
    font-size: 3rem;
  }

  .proj-grid {
    grid-template-columns: 1fr;
  }

  .proj-card--wide {
    grid-column: span 1;
  }

  .xp-item {
    grid-template-columns: 1fr;
    gap: 10px;
  }

  .footer-wrap {
    flex-direction: column;
    align-items: flex-start;
    gap: 8px;
  }

  .footer-consent {
    text-align: left;
  }
}
</style>
