<script setup lang="ts">
import { onMounted } from 'vue';
// import { Head } from '@inertiajs/vue3';

onMounted(() => {
  // Ensure script executes after component DOM is fully mounted
  const initLinkedInBadge = () => {
    // Remove any previously appended script tag to force re-parsing
    document.querySelectorAll('script[src*="platform.linkedin.com/badges/js/profile.js"]').forEach(el => el.remove());

    const script = document.createElement('script');
    script.src = 'https://platform.linkedin.com/badges/js/profile.js';
    script.async = true;
    script.defer = true;
    script.type = 'text/javascript';
    document.head.appendChild(script);
  };

  setTimeout(initLinkedInBadge, 150);
});

const experience = [
  {
    company: 'Ilusion Vault',
    role: 'Creator and Developer (Self-Employed)',
    type: 'Self-Employed',
    period: 'Apr 2026 – Current',
    location: 'Remote',
    bullets: [
      'Built a client-side zero-knowledge encryption flow (Web Crypto API + R2/S3 pre-signed uploads) ensuring the server never accesses plaintext data.',
      'Engineered a high-performance encryption pipeline with Web Workers and key-caching, bulk-upload.',
      'Designed and implemented a modern, premium UI (glass-morphism dashboard, responsive Vue components, vue-sonner toasts) that showcases encrypted file sharing and folder permissions.',
      'Strengthened overall security by adding a strict Content-Security-Policy, extra HTTP headers, and front-end sanitization (DOMPurify) while maintaining full SEO compliance.',
    ],
    accent: '#00cc88',
  },
  {
    company: 'SecretAlign',
    role: 'Laravel Developer (Contract)',
    type: 'Contract',
    period: 'Mar 2025 – May 2025',
    location: 'Remote',
    bullets: [
      'Diagnosed and resolved production bugs across multiple Laravel modules, improving application stability and user experience.',
      'Created and maintained technical documentation for APIs, modules, and workflows to support onboarding and long-term maintainability.',
      'Refactored backend code to improve performance, readability, and adherence to Laravel best practices.',
      'Developed and integrated new backend features based on evolving product requirements.',
    ],
    accent: '#006c46',
  },
  {
    company: 'Yantravyuh LLP',
    role: 'Full Stack Developer Intern',
    type: 'Internship',
    period: 'Jun 2024 – Feb 2025',
    location: 'Thane, Maharashtra',
    bullets: [
      'Enhanced frontend components and layouts using Vue.js to improve usability and responsiveness.',
      'Delivered backend features and bug fixes in PHP/Laravel to ensure reliable end-to-end platform functionality.',
      'Refactored Laravel and Vue.js components to improve performance, scalability, and code maintainability.',
      'Prepared clear technical documentation to support development workflows and cross-team collaboration.',
    ],
    accent: '#0d1c2f',
  },
];

const projects = [
  {
    title: 'Kesari Awayddings',
    subtitle: 'Destination Wedding Platform',
    tags: ['Vue.js', 'Laravel', 'MySQL'],
    accent: '#00cc88',
    bullets: [
      'Implemented a complete booking workflow for destination weddings across India, including venue discovery, guest management, menu selection, and payment processing.',
    ],
  },
  {
    title: 'LongLif- Personal AI Consultant',
    subtitle: 'AI Emotion & Schedule Consultant',
    tags: ['Python', 'Colab', 'Hugging-Face', 'Modal', 'Vercel', 'NextJS'],
    accent: '#0078D4',
    bullets: [
      'Auto-tuned the Qwen 7B AI model for managing the time and emotions of an individual on Google Colab, hosting it on Modal cloud hosting.',
      'Called the exposed API of the model from a React frontend for better integration with the consultant.',
    ],
  },
  {
    title: 'Mock Backend APIs Platform',
    subtitle: 'Developer API Mocking Platform',
    tags: ['Next.js', 'Django', 'MySQL'],
    accent: '#006c46',
    bullets: [
      'Built a customizable mock server platform allowing dynamic API route creation, configurable request types, and user-defined responses for rapid frontend development.',
    ],
  },
];

const education = [
  {
    institution: 'University of Mumbai',
    degree: 'Bachelor of Engineering in Information Technology',
    period: 'Nov 2022 – Jun 2025',
    location: 'Thane, Maharashtra',
  },
  {
    institution: 'Puranmal Lahoti Government Polytechnic',
    degree: 'Diploma in Information Technology',
    period: 'Aug 2019 – Jul 2022',
    location: 'Latur, Maharashtra',
  },
];
</script>

<template>
  <Head>
    <title>Shreyash Pawar — Full Stack Developer & Creator of Ilusion Vault</title>
    <meta name="description" content="Portfolio of Shreyash Pawar — Full Stack Developer specializing in Vue.js, Laravel, and zero-knowledge encryption systems. Creator of Ilusion Vault." />
    <meta name="robots" content="index, follow" />
    <link rel="canonical" href="https://shreyash.ilusion.io/" />

    <!-- Open Graph / Social Sharing -->
    <meta property="og:type" content="website" />
    <meta property="og:url" content="https://shreyash.ilusion.io/" />
    <meta property="og:title" content="Shreyash Pawar — Full Stack Developer & Creator of Ilusion Vault" />
    <meta property="og:description" content="Portfolio of Shreyash Pawar — Full Stack Developer specializing in Vue.js, Laravel, and zero-knowledge encryption systems. Creator of Ilusion Vault." />

    <!-- Twitter -->
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content="Shreyash Pawar — Full Stack Developer & Creator of Ilusion Vault" />
    <meta name="twitter:description" content="Portfolio of Shreyash Pawar — Full Stack Developer specializing in Vue.js, Laravel, and zero-knowledge encryption systems. Creator of Ilusion Vault." />
  </Head>

  <div class="portfolio-page bg-[#f7f9fb] text-[#191c1e] min-h-screen flex flex-col dot-grid">

    <!-- Standalone Portfolio Nav -->
    <header class="pf-nav">
      <div class="pf-nav-inner">
        <span class="pf-nav-logo">
          <span class="pf-logo-dot"></span>
          Shreyash Pawar
        </span>
        <div class="flex items-center gap-3">
          <a href="#experience" class="pf-nav-link hidden sm:inline-flex">
            <AppIcon name="work" class="w-4 h-4" />
            Experience
          </a>
          <a href="#projects" class="pf-nav-link hidden sm:inline-flex">
            <AppIcon name="code" class="w-4 h-4" />
            Projects
          </a>
          <a href="#education" class="pf-nav-link hidden sm:inline-flex">
            <AppIcon name="school" class="w-4 h-4" />
            Education
          </a>
          <a href="mailto:shreyashrpawar28@gmail.com" class="pf-nav-link hidden sm:inline-flex">
            <AppIcon name="mail" class="w-4 h-4" />
            Contact
          </a>
          <a href="/shreyash_pawar.pdf" download="shreyash_pawar.pdf" target="_blank" class="pf-nav-resume">
            <AppIcon name="download" class="w-4 h-4" />
            Resume
          </a>
          <a href="https://www.linkedin.com/in/shreyash-pawar28/" target="_blank" rel="noopener noreferrer" class="pf-nav-link hidden sm:inline-flex">
            <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
            LinkedIn
          </a>
          <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="pf-nav-btn">
            <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
            GitHub
          </a>
        </div>
      </div>
    </header>

    <main class="flex-grow">

      <!-- Hero -->
      <section class="hero-section relative overflow-hidden py-20 md:py-28 px-4">
        <div class="hero-glow"></div>
        <div class="max-w-5xl mx-auto px-4 sm:px-8 relative z-10">
          <div class="flex flex-col md:flex-row items-center md:items-start gap-10">
            <!-- Avatar -->
            <div class="avatar-ring flex-shrink-0">
              <div class="avatar-inner">
                <span class="avatar-initials">SP</span>
              </div>
            </div>

            <!-- Info -->
            <div class="text-center md:text-left flex-1 min-w-0">
              <div class="flex flex-wrap items-center justify-center md:justify-start gap-2.5 mb-4">
                <span class="badge">
                  <span class="badge-dot"></span>
                  Available for opportunities
                </span>
              </div>
              <h1 class="font-display text-[clamp(2.25rem,5vw,3.5rem)] font-bold leading-none tracking-tight text-[#191c1e] mb-3">
                Shreyash<br /><span class="text-accent">Pawar</span>
              </h1>
              <p class="font-body text-base sm:text-lg text-[#3c4a41] mb-5 max-w-xl leading-relaxed">
                Full Stack Developer &amp; Creator of <span class="text-accent font-semibold">Ilusion Vault</span> — specializing in Vue.js, Laravel, zero-knowledge encryption, and high-performance modern web platforms.
              </p>

              <!-- Resume Actions -->
              <div class="flex flex-wrap items-center justify-center md:justify-start gap-3 mb-6">
                <a
                  href="/shreyash_pawar.pdf"
                  download="shreyash_pawar.pdf"
                  target="_blank"
                  class="download-btn"
                >
                  <AppIcon name="download" class="w-[18px] h-[18px]" />
                  <span>Download Resume</span>
                </a>
                <a
                  href="/shreyash_pawar.pdf"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="preview-btn"
                >
                  <AppIcon name="visibility" class="w-[18px] h-[18px]" />
                  <span>View PDF</span>
                </a>
              </div>

              <!-- Contact row -->
              <div class="flex flex-wrap justify-center md:justify-start gap-2.5 mb-3">
                <a href="mailto:shreyashrpawar28@gmail.com" class="chip-btn">
                  <AppIcon name="mail" class="w-4 h-4" />
                  shreyashrpawar28@gmail.com
                </a>
                <a href="tel:9420784253" class="chip-btn">
                  <AppIcon name="call" class="w-4 h-4" />
                  9420784253
                </a>
                <span class="chip-info">
                  <AppIcon name="location_on" class="w-4 h-4" />
                  Thane, Maharashtra
                </span>
                <a href="https://shreyash.ilusion.io" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <AppIcon name="language" class="w-4 h-4" />
                  shreyash.ilusion.io
                </a>
              </div>

              <!-- Social row -->
              <div class="flex flex-wrap justify-center md:justify-start gap-2.5">
                <a href="https://www.linkedin.com/in/shreyash-pawar28/" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
                  LinkedIn
                </a>
                <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                  GitHub
                </a>
                <a href="https://medium.com/@shreyash07" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <AppIcon name="article" class="w-4 h-4" />
                  Medium
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Experience -->
      <section id="experience" class="section-wrapper bg-white border-y border-[#e0e3e5]">
        <div class="max-w-5xl mx-auto px-4 sm:px-8">
          <h2 class="section-title">Experience</h2>
          <div class="relative">
            <!-- Timeline line -->
            <div class="timeline-line"></div>
            <div class="flex flex-col gap-8">
              <div v-for="(exp, i) in experience" :key="i" class="timeline-item">
                <div class="timeline-dot" :style="{ background: exp.accent }"></div>
                <div class="vault-card rounded-xl p-6 flex-1">
                  <div class="flex flex-col sm:flex-row sm:items-start sm:justify-between gap-2 mb-4">
                    <div>
                      <h3 class="font-semibold text-[#191c1e] text-lg leading-tight">{{ exp.company }}</h3>
                      <p class="text-sm text-[#3c4a41] font-medium">{{ exp.role }} · <span class="text-[#515f74]">{{ exp.location }}</span></p>
                    </div>
                    <span class="period-badge">{{ exp.period }}</span>
                  </div>
                  <ul class="space-y-2">
                    <li v-for="(b, j) in exp.bullets" :key="j" class="flex items-start gap-2 text-sm text-[#3c4a41] leading-relaxed">
                      <AppIcon name="arrow_right" class="w-4 h-4 text-[#00cc88] mt-0.5 flex-shrink-0" />
                      {{ b }}
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Projects -->
      <section id="projects" class="section-wrapper">
        <div class="max-w-5xl mx-auto px-4 sm:px-8">
          <h2 class="section-title">Projects</h2>
          <div class="flex flex-col gap-6">
            <div v-for="(proj, i) in projects" :key="i" class="vault-card rounded-xl p-6" :class="{ 'ring-1 ring-[#006c46]/20': i === 0 }">
              <div class="flex flex-col sm:flex-row sm:items-start sm:justify-between gap-3 mb-4">
                <div>
                  <div class="flex items-center gap-2 mb-1">
                    <h3 class="font-semibold text-[#191c1e] text-lg leading-tight">{{ proj.title }}</h3>
                    <span v-if="i === 0" class="text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded-full bg-[#006c46]/10 text-[#006c46]">Featured</span>
                  </div>
                  <p v-if="proj.subtitle" class="text-sm text-[#515f74] font-medium mb-2">{{ proj.subtitle }}</p>
                  <div class="flex flex-wrap gap-1.5">
                    <span v-for="tag in proj.tags" :key="tag" class="skill-tag" :style="{ borderColor: proj.accent + '40', color: proj.accent }">{{ tag }}</span>
                  </div>
                </div>
              </div>
              <ul class="space-y-2">
                <li v-for="(b, j) in proj.bullets" :key="j" class="flex items-start gap-2 text-sm text-[#3c4a41] leading-relaxed">
                  <AppIcon name="arrow_right" class="w-4 h-4 mt-0.5 flex-shrink-0" :style="{ color: proj.accent }" />
                  {{ b }}
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- Education -->
      <section id="education" class="section-wrapper bg-white border-t border-[#e0e3e5]">
        <div class="max-w-5xl mx-auto px-4 sm:px-8">
          <h2 class="section-title">Education</h2>
          <div class="flex flex-col gap-4">
            <div v-for="(edu, i) in education" :key="i" class="vault-card rounded-xl p-6 flex flex-col sm:flex-row sm:items-center sm:justify-between gap-3">
              <div>
                <h3 class="font-semibold text-[#191c1e]">{{ edu.institution }}</h3>
                <p class="text-sm text-[#3c4a41]">{{ edu.degree }}</p>
                <p class="text-xs text-[#515f74] mt-1 flex items-center gap-1">
                  <AppIcon name="location_on" class="w-3.5 h-3.5" />
                  {{ edu.location }}
                </p>
              </div>
              <span class="period-badge self-start sm:self-center">{{ edu.period }}</span>
            </div>
          </div>
        </div>
      </section>

      <!-- Connect on LinkedIn -->
      <section class="section-wrapper">
        <div class="max-w-5xl mx-auto px-4 sm:px-8">
          <div class="vault-card rounded-2xl p-8 md:p-10 flex flex-col md:flex-row items-center gap-8">
            <!-- Left: Context -->
            <div class="flex-1 text-center md:text-left">
              <div class="flex items-center justify-center md:justify-start gap-2 mb-3">
                <svg class="w-6 h-6 fill-[#0a66c2]" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
                <h2 class="font-display text-xl font-bold text-[#191c1e]">Connect on LinkedIn</h2>
              </div>
              <p class="text-sm text-[#3c4a41] leading-relaxed max-w-md">
                Let's connect professionally. View my full work history, endorsements, and recommendations on LinkedIn.
              </p>
            </div>
            <!-- Right: LinkedIn Badge Widget -->
            <div class="flex-shrink-0">
              <div class="badge-base LI-profile-badge" data-locale="en_US" data-size="large" data-theme="light" data-type="HORIZONTAL" data-vanity="shreyash-pawar28" data-version="v1">
                <a class="badge-base__link LI-simple-link" href="https://www.linkedin.com/in/shreyash-pawar28?trk=profile-badge"></a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- CTA -->
      <section class="section-wrapper bg-white border-t border-[#e0e3e5]">
        <div class="max-w-5xl mx-auto px-4 sm:px-8 text-center">
          <div class="vault-card rounded-2xl p-10 md:p-16 relative overflow-hidden">
            <div class="cta-glow"></div>
            <h2 class="font-display text-[clamp(1.5rem,4vw,2.5rem)] font-bold text-[#191c1e] mb-3 relative z-10">Let's build something together</h2>
            <p class="text-[#3c4a41] mb-8 relative z-10 max-w-md mx-auto">Open to full-time roles, freelance contracts, and interesting collaborations.</p>
            <div class="flex flex-wrap justify-center gap-4 relative z-10">
              <a href="/shreyash_pawar.pdf" download="shreyash_pawar.pdf" target="_blank" class="cta-primary">
                <AppIcon name="download" class="w-[18px] h-[18px]" />
                Download Resume
              </a>
              <a href="mailto:shreyashrpawar28@gmail.com" class="cta-secondary">
                <AppIcon name="mail" class="w-[18px] h-[18px]" />
                Get in Touch
              </a>
              <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="cta-secondary">
                <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                View GitHub
              </a>
              <a href="https://www.linkedin.com/in/shreyash-pawar28/" target="_blank" rel="noopener noreferrer" class="cta-secondary">
                <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
                LinkedIn
              </a>
              <a href="https://medium.com/@shreyash07" target="_blank" rel="noopener noreferrer" class="cta-secondary">
                <AppIcon name="article" class="w-[18px] h-[18px]" />
                Medium
              </a>
            </div>
          </div>
        </div>
      </section>

    </main>

    <!-- Standalone Portfolio Footer -->
    <footer class="pf-footer">
      <div class="pf-footer-inner">
        <span class="text-xs text-[#515f74]">© {{ new Date().getFullYear() }} Shreyash Pawar</span>
        <div class="flex items-center gap-4">
          <a href="mailto:shreyashrpawar28@gmail.com" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors">shreyashrpawar28@gmail.com</a>
          <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors font-semibold">GitHub</a>
          <a href="https://www.linkedin.com/in/shreyash-pawar28/" target="_blank" rel="noopener noreferrer" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors font-semibold">LinkedIn</a>
          <a href="https://medium.com/@shreyash07" target="_blank" rel="noopener noreferrer" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors font-semibold">Medium</a>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.portfolio-page {
  font-family: 'Hanken Grotesk', sans-serif;
}

.dot-grid {
  background-image: radial-gradient(#bbcabe 0.8px, transparent 0.8px);
  background-size: 24px 24px;
}

/* Hero */
.hero-section {
  background: linear-gradient(135deg, #f7f9fb 0%, #eef5f1 100%);
}
.hero-glow {
  position: absolute;
  top: -80px;
  right: -80px;
  width: 480px;
  height: 480px;
  background: radial-gradient(circle, rgba(0, 204, 136, 0.12) 0%, transparent 70%);
  pointer-events: none;
}

/* Avatar */
.avatar-ring {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: linear-gradient(135deg, #00cc88, #006c46);
  padding: 3px;
  flex-shrink: 0;
}
.avatar-inner {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: #f7f9fb;
  display: flex;
  align-items: center;
  justify-content: center;
}
.avatar-initials {
  font-family: 'Hanken Grotesk', sans-serif;
  font-size: 2rem;
  font-weight: 700;
  color: #006c46;
  letter-spacing: -0.02em;
}

/* Badge */
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  background: rgba(0, 204, 136, 0.12);
  border: 1px solid rgba(0, 204, 136, 0.3);
  color: #005033;
  font-size: 0.8rem;
  font-weight: 600;
  padding: 4px 12px;
  border-radius: 999px;
  letter-spacing: 0.02em;
}
.badge-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #00cc88;
  animation: pulse 2s infinite;
}
@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.6; transform: scale(0.85); }
}

.text-accent { color: #006c46; }

/* Chips */
.chip-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 14px;
  border-radius: 8px;
  border: 1px solid #bbcabe;
  background: #fff;
  color: #3c4a41;
  font-size: 0.8rem;
  font-weight: 500;
  text-decoration: none;
  transition: border-color 0.15s, color 0.15s;
}
.chip-btn:hover { border-color: #00cc88; color: #006c46; }
.chip-info {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 14px;
  border-radius: 8px;
  background: #f7f9fb;
  color: #515f74;
  font-size: 0.8rem;
  font-weight: 500;
}

/* Resume Buttons */
.download-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 0.65rem 1.4rem;
  border-radius: 9px;
  background: #006c46;
  color: #fff;
  font-weight: 700;
  font-size: 0.9rem;
  text-decoration: none;
  transition: background 0.15s, transform 0.1s, box-shadow 0.15s;
  box-shadow: 0 2px 8px rgba(0, 108, 70, 0.25);
}
.download-btn:hover {
  background: #005033;
  transform: translateY(-1px);
  box-shadow: 0 4px 14px rgba(0, 108, 70, 0.35);
}

.preview-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 0.65rem 1.25rem;
  border-radius: 9px;
  border: 1px solid #bbcabe;
  background: #fff;
  color: #3c4a41;
  font-weight: 600;
  font-size: 0.88rem;
  text-decoration: none;
  transition: border-color 0.15s, color 0.15s, background 0.15s;
}
.preview-btn:hover {
  border-color: #006c46;
  color: #006c46;
  background: #f0f7f4;
}

/* Sections */
.section-wrapper {
  padding: 4rem 1rem;
}
.section-title {
  font-family: 'Hanken Grotesk', sans-serif;
  font-size: clamp(1.35rem, 3vw, 1.75rem);
  font-weight: 700;
  color: #191c1e;
  letter-spacing: -0.02em;
  margin-bottom: 1.75rem;
  position: relative;
  padding-bottom: 0.75rem;
}
.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 40px;
  height: 3px;
  background: #00cc88;
  border-radius: 2px;
}

/* Cards */
.vault-card {
  background: #fff;
  border: 1px solid #e0e3e5;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.vault-card:hover {
  border-color: #00cc88;
  box-shadow: 0 4px 16px rgba(0, 204, 136, 0.08);
}

/* Skills */
.skill-tag {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 10px;
  border-radius: 6px;
  background: #f0f7f4;
  color: #006c46;
  border: 1px solid rgba(0, 108, 70, 0.15);
}

/* Timeline */
.timeline-line {
  position: absolute;
  left: 18px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, #00cc88, #bbcabe);
}
.timeline-item {
  display: flex;
  gap: 2rem;
  padding-left: 2.5rem;
  position: relative;
}
.timeline-dot {
  position: absolute;
  left: 10px;
  top: 24px;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 0 0 0 2px #bbcabe;
}

/* Period badge */
.period-badge {
  display: inline-flex;
  align-items: center;
  font-size: 0.75rem;
  font-weight: 600;
  color: #515f74;
  background: #f7f9fb;
  border: 1px solid #e0e3e5;
  padding: 3px 10px;
  border-radius: 6px;
  white-space: nowrap;
  flex-shrink: 0;
}

/* Projects */
.project-card { transition: transform 0.2s, border-color 0.2s, box-shadow 0.2s; }
.project-card:hover { transform: translateY(-2px); }


/* CTA */
.cta-glow {
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at 50% 0%, rgba(0, 204, 136, 0.08) 0%, transparent 70%);
  pointer-events: none;
}
.cta-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 0.75rem 1.75rem;
  border-radius: 10px;
  background: #0d1c2f;
  color: #fff;
  font-weight: 700;
  font-size: 0.9rem;
  text-decoration: none;
  transition: background 0.15s, transform 0.1s;
}
.cta-primary:hover { background: #00cc88; color: #005033; transform: scale(0.98); }
.cta-secondary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 0.75rem 1.75rem;
  border-radius: 10px;
  border: 2px solid #191c1e;
  color: #191c1e;
  font-weight: 700;
  font-size: 0.9rem;
  text-decoration: none;
  transition: background 0.15s, color 0.15s, transform 0.1s;
}
.cta-secondary:hover { background: #191c1e; color: #fff; transform: scale(0.98); }

/* Font utilities */
.font-display { font-family: 'Hanken Grotesk', sans-serif; }
.font-body { font-family: 'Hanken Grotesk', sans-serif; }
.font-label-sm { font-family: 'Hanken Grotesk', sans-serif; letter-spacing: 0.08em; }



/* Standalone Portfolio Nav */
.pf-nav {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(247, 249, 251, 0.92);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid #bbcabe;
}
.pf-nav-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 80rem;
  margin: 0 auto;
  padding: 0.75rem 2rem;
  gap: 1rem;
}
.pf-nav-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-family: 'Hanken Grotesk', sans-serif;
  font-size: 1.05rem;
  font-weight: 700;
  color: #191c1e;
  letter-spacing: -0.01em;
}
.pf-logo-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #00cc88;
  flex-shrink: 0;
}
.pf-nav-link {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  font-size: 0.85rem;
  font-weight: 500;
  color: #3c4a41;
  text-decoration: none;
  padding: 0.4rem 0.85rem;
  border-radius: 7px;
  transition: color 0.15s, background 0.15s;
}
.pf-nav-link:hover { color: #006c46; background: #eceef0; }
.pf-nav-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 0.45rem 1rem;
  border-radius: 7px;
  background: #0d1c2f;
  color: #fff;
  font-size: 0.85rem;
  font-weight: 700;
  text-decoration: none;
  transition: background 0.15s, transform 0.1s;
}
.pf-nav-btn:hover { background: #00cc88; color: #005033; transform: scale(0.97); }

.pf-nav-resume {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  padding: 0.4rem 0.9rem;
  border-radius: 7px;
  background: rgba(0, 108, 70, 0.1);
  border: 1px solid rgba(0, 108, 70, 0.25);
  color: #006c46;
  font-size: 0.85rem;
  font-weight: 600;
  text-decoration: none;
  transition: background 0.15s, color 0.15s;
}
.pf-nav-resume:hover {
  background: #006c46;
  color: #fff;
}

/* Standalone Portfolio Footer */
.pf-footer {
  border-top: 1px solid #bbcabe;
  background: #fff;
}
.pf-footer-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.75rem;
  max-width: 80rem;
  margin: 0 auto;
  padding: 1.25rem 2rem;
}
</style>
