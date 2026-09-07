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

const skills = {
  'ETL & Data Integration': ['Informatica PowerCenter 10.x', 'ETL', 'Data Warehousing', 'Change Data Capture (CDC)', 'Incremental Loading'],
  'Informatica': ['Lookup', 'Router', 'Filter', 'Aggregator', 'Joiner', 'Sorter', 'Source Qualifier', 'Mapplets', 'Reusable Transformations', 'Mapping Parameters/Variables', 'Session Variables'],
  'Software Development': ['Laravel', 'Vue.js', 'TypeScript', 'PHP', 'Inertia.js', 'Tailwind CSS', 'REST APIs', 'WebCrypto API'],
  'Databases': ['Oracle', 'SQL Server', 'MySQL', 'SQL', 'PL/SQL'],
  'Programming & Data': ['Python', 'PySpark', 'JavaScript'],
  'Cloud & Infrastructure': ['Azure Fabric', 'Cloudflare R2', 'Nginx', 'Git', 'SVN', 'CI/CD', 'Vite', 'Unix'],
};

const experience = [
  {
    company: 'Tata Consultancy Services (TCS) — Equity Insurance Ltd',
    role: 'ETL Developer',
    type: 'Full-time',
    period: 'Dec 2025 – Jul 2026',
    location: 'India',
    bullets: [
      'Developed and supported Informatica ETL mappings to load agent and policy data from relational sources into the enterprise data warehouse.',
      'Implemented business rules for calculating monthly compensation and incentive amounts and supported data processing for financial, management, and rejection reporting.',
      'Designed mappings using Lookup, Router, Filter, Source Qualifier, Aggregator, Joiner, and Sorter transformations.',
      'Optimized long-running ETL jobs through performance tuning at the mapping, session, and SQL levels.',
      'Created reusable Mapplets and Transformations to improve modularity and reduce redundancy across ETL.',
      'Analyzed Informatica job failures, performed root-cause analysis, and resolved production issues using documented processes.',
      'Wrote SQL queries for data validation, troubleshooting, and ETL-related analysis.',
    ],
    accent: '#00cc88',
  },
  {
    company: 'Tata Consultancy Services (TCS) — Truist Financial Bank',
    role: 'ETL Developer',
    type: 'Full-time',
    period: 'Feb 2024 – Nov 2025',
    location: 'India',
    bullets: [
      'Developed Informatica mappings to load data into staging tables and downstream data warehouse layers for a global trade repository.',
      'Implemented business rules and integrated data from relational databases and flat-file sources.',
      'Implemented Change Data Capture (CDC) for staging using mapping parameters and worked with Mapping Parameters, Mapping Variables, and Session Variables.',
      'Designed ETL workflows using Lookup, Router, Filter, Source Qualifier, Aggregator, Joiner, and Sorter transformations.',
      'Developed reusable transformations, reusable mappings, and Mapplets to improve ETL modularity and minimize duplicate logic.',
      'Monitored daily ETL loads, analyzed job failures, performed root-cause analysis, and resolved failures according to defined processes and SLAs.',
      'Performed performance tuning for long-running Informatica jobs at mapping, session, and SQL levels.',
      'Automated and scheduled Informatica workflows and performed unit and system testing of developed mappings.',
      'Created test plans, test cases, and test scripts based on mapping documents and testing strategies.',
      'Performed small enhancements and supported production ETL workflows.',
    ],
    accent: '#006c46',
  },
];

const projects = [
  {
    title: 'Ilusion Vault — Zero-Knowledge Encrypted Platform',
    subtitle: 'Creator & Full-Stack Developer',
    tags: ['Laravel', 'Vue.js', 'TypeScript', 'Inertia.js', 'WebCrypto API', 'Cloudflare R2', 'MySQL', 'Tailwind CSS'],
    accent: '#006c46',
    link: null,
    bullets: [
      'Built and shipped a full-stack, zero-knowledge encrypted file vault and secret sharing platform from scratch — end-to-end architecture, development, and deployment.',
      'Implemented client-side AES-GCM encryption using the WebCrypto API, ensuring files are encrypted before leaving the browser — the server never sees plaintext data.',
      'Designed a secure vault file management system with folder hierarchy, drag-and-drop uploads, and pre-signed Cloudflare R2/S3 direct-to-storage transfers.',
      'Built self-destructing secret sharing with configurable expiry, view limits, and optional password protection.',
      'Developed a responsive, production-grade dashboard with real-time activity logs, storage quota tracking, and file sharing permissions.',
      'Architected the Laravel backend with Inertia.js for seamless SPA routing, strict CSP security headers, and comprehensive middleware stack.',
    ],
  },
  {
    title: 'Ilusion Vault — Microsoft Fabric Data Engineering',
    subtitle: 'Data Engineering Project',
    tags: ['Microsoft Fabric', 'Azure SQL Server', 'Lakehouse', 'Dataflow Gen2', 'Warehouse', 'Power BI'],
    accent: '#0078D4',
    link: null,
    bullets: [
      'Designed and implemented an end-to-end Microsoft Fabric medallion architecture, organizing data across Bronze, Silver, and Gold layers.',
      'Built a Bronze Lakehouse and used a Fabric Copy Job to incrementally ingest operational data from Azure SQL Server into the data platform.',
      'Implemented the Silver transformation layer using Materialized Lake Views and Dataflow Gen2 to clean, transform, and prepare data for analytical workloads.',
      'Built the Gold layer in a Fabric Warehouse, creating curated datasets optimized for reporting and business analytics.',
      'Connected the Gold Warehouse to Power BI and developed an interactive dashboard for monitoring and analyzing application data.',
    ],
  },
];

const education = [
  {
    institution: 'University of Mumbai',
    degree: 'Bachelor of Engineering in Information Technology',
    period: 'Nov 2022 – Jul 2025',
    location: 'Thane',
    description: 'Coursework: Data Structures, Algorithms, Databases, Computer Systems, Web development'
  },
];
</script>

<template>
  <Head>
    <title>Shreyash Pawar — ETL Developer & Software Engineer</title>
    <meta name="description" content="Portfolio of Shreyash Pawar — ETL Developer specializing in Informatica PowerCenter and Full-Stack Software Engineer. Creator of Ilusion Vault, a zero-knowledge encrypted platform." />
    <meta name="robots" content="index, follow" />
    <link rel="canonical" href="https://shreyash.ilusion.io/" />

    <!-- Open Graph / Social Sharing -->
    <meta property="og:type" content="website" />
    <meta property="og:url" content="https://shreyash.ilusion.io/" />
    <meta property="og:title" content="Shreyash Pawar — ETL Developer & Software Engineer" />
    <meta property="og:description" content="ETL Developer at TCS & Full-Stack Software Engineer. Creator of Ilusion Vault — a zero-knowledge encrypted file vault and secret sharing platform." />

    <!-- Twitter -->
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content="Shreyash Pawar — ETL Developer & Software Engineer" />
    <meta name="twitter:description" content="ETL Developer at TCS & Full-Stack Software Engineer. Creator of Ilusion Vault — a zero-knowledge encrypted file vault and secret sharing platform." />
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
          <a href="mailto:shreyash.pawarr1@gmail.com" class="pf-nav-link hidden sm:inline-flex">
            <span class="material-symbols-outlined text-[16px]">mail</span>
            Contact
          </a>
          <a href="https://www.linkedin.com/in/shreyash-pawar-a59739424/" target="_blank" rel="noopener noreferrer" class="pf-nav-link hidden sm:inline-flex">
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
              <span class="badge mb-4">
                <span class="badge-dot"></span>
                Available for opportunities
              </span>
              <h1 class="font-display text-[clamp(2.25rem,5vw,3.5rem)] font-bold leading-none tracking-tight text-[#191c1e] mb-3">
                Shreyash<br /><span class="text-accent">Pawar</span>
              </h1>
              <p class="font-body text-base sm:text-lg text-[#3c4a41] mb-6 max-w-xl leading-relaxed">
                ETL Developer with 2.5+ years of experience in Data Warehousing and BI, specializing in Informatica PowerCenter. Full-stack software engineer and creator of <span class="text-accent font-semibold">Ilusion Vault</span> — a zero-knowledge encrypted platform.
              </p>

              <!-- Contact row -->
              <div class="flex flex-wrap justify-center md:justify-start gap-2.5 mb-3">
                <a href="mailto:shreyash.pawarr1@gmail.com" class="chip-btn">
                  <span class="material-symbols-outlined text-[16px]">mail</span>
                  shreyash.pawarr1@gmail.com
                </a>
                <a href="tel:8459032640" class="chip-btn">
                  <span class="material-symbols-outlined text-[16px]">call</span>
                  8459032640
                </a>
                <span class="chip-info">
                  <span class="material-symbols-outlined text-[16px]">location_on</span>
                  Thane
                </span>
              </div>

              <!-- Social row -->
              <div class="flex flex-wrap justify-center md:justify-start gap-2.5">
                <a href="https://www.linkedin.com/in/shreyash-pawar-a59739424/" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
                  LinkedIn
                </a>
                <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                  GitHub
                </a>
                <a href="https://medium.com/@shreyash07" target="_blank" rel="noopener noreferrer" class="chip-btn">
                  <span class="material-symbols-outlined text-[16px]">article</span>
                  Medium
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Skills -->
      <section class="section-wrapper">
        <div class="max-w-5xl mx-auto px-4 sm:px-8">
          <h2 class="section-title">Technical Skills</h2>
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
            <div v-for="(items, category) in skills" :key="category" class="vault-card p-5 rounded-xl">
              <h3 class="font-label-sm text-xs text-[#006c46] uppercase tracking-widest mb-3">{{ category }}</h3>
              <div class="flex flex-wrap gap-1.5">
                <span v-for="skill in items" :key="skill" class="skill-tag">{{ skill }}</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Experience -->
      <section class="section-wrapper bg-white border-y border-[#e0e3e5]">
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
                      <p class="text-sm text-[#3c4a41] font-medium">{{ exp.role }} · {{ exp.type }}</p>
                    </div>
                    <span class="period-badge">{{ exp.period }}</span>
                  </div>
                  <ul class="space-y-2">
                    <li v-for="(b, j) in exp.bullets" :key="j" class="flex items-start gap-2 text-sm text-[#3c4a41] leading-relaxed">
                      <span class="material-symbols-outlined text-[#00cc88] text-[16px] mt-0.5 flex-shrink-0" style="font-variation-settings: 'FILL' 1;">arrow_right</span>
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
      <section class="section-wrapper">
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
                <a v-if="proj.link" :href="proj.link" target="_blank" rel="noopener noreferrer" class="chip-btn !text-white !bg-[#191c1e] hover:!bg-[#006c46] transition-colors flex-shrink-0 self-start">
                  <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                  View Source
                </a>
              </div>
              <ul class="space-y-2">
                <li v-for="(b, j) in proj.bullets" :key="j" class="flex items-start gap-2 text-sm text-[#3c4a41] leading-relaxed">
                  <span class="material-symbols-outlined text-[16px] mt-0.5 flex-shrink-0" :style="{ color: proj.accent }" style="font-variation-settings: 'FILL' 1;">arrow_right</span>
                  {{ b }}
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- Education -->
      <section class="section-wrapper">
        <div class="max-w-5xl mx-auto px-4 sm:px-8">
          <h2 class="section-title">Education</h2>
          <div class="flex flex-col gap-4">
            <div v-for="(edu, i) in education" :key="i" class="vault-card rounded-xl p-6 flex flex-col sm:flex-row sm:items-center sm:justify-between gap-3">
              <div>
                <h3 class="font-semibold text-[#191c1e]">{{ edu.institution }}</h3>
                <p class="text-sm text-[#3c4a41]">{{ edu.degree }}</p>
                <p class="text-xs text-[#515f74] mt-1">{{ edu.description }}</p>
                <p class="text-xs text-[#515f74] mt-1 flex items-center gap-1">
                  <span class="material-symbols-outlined text-[14px]">location_on</span>
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
              <div class="badge-base LI-profile-badge" data-locale="en_US" data-size="large" data-theme="light" data-type="HORIZONTAL" data-vanity="shreyash-pawar-a59739424" data-version="v1">
                <a class="badge-base__link LI-simple-link" href="https://in.linkedin.com/in/shreyash-pawar-a59739424?trk=profile-badge"></a>
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
              <a href="mailto:shreyash.pawarr1@gmail.com" class="cta-primary">
                <span class="material-symbols-outlined text-[18px]">mail</span>
                Get in Touch
              </a>
              <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="cta-secondary">
                <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
                View GitHub
              </a>
              <a href="https://www.linkedin.com/in/shreyash-pawar-a59739424/" target="_blank" rel="noopener noreferrer" class="cta-secondary">
                <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h14m-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.28 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93h2.75M6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37h2.77z"/></svg>
                LinkedIn
              </a>
              <a href="https://medium.com/@shreyash07" target="_blank" rel="noopener noreferrer" class="cta-secondary">
                <span class="material-symbols-outlined text-[18px]">article</span>
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
          <a href="mailto:shreyash.pawarr1@gmail.com" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors">shreyash.pawarr1@gmail.com</a>
          <a href="https://github.com/shreyashrpawar" target="_blank" rel="noopener noreferrer" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors font-semibold">GitHub</a>
          <a href="https://www.linkedin.com/in/shreyash-pawar-a59739424/" target="_blank" rel="noopener noreferrer" class="text-xs text-[#515f74] hover:text-[#006c46] transition-colors font-semibold">LinkedIn</a>
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

.context-badge {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: #515f74;
  background: #f7f9fb;
  border: 1px solid #e0e3e5;
  padding: 3px 8px;
  border-radius: 6px;
}

.tech-tag {
  font-size: 0.72rem;
  font-weight: 600;
  padding: 3px 9px;
  border-radius: 5px;
  background: #0d1c2f;
  color: #fff;
}

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

.material-symbols-outlined {
  font-family: 'Material Symbols Outlined';
  font-weight: normal;
  font-style: normal;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
}

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
