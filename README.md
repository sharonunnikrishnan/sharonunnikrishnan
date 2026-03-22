<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sharon Unnikrishnan — Backend Engineer</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,500;0,700;1,500&family=Plus+Jakarta+Sans:wght@300;400;500;600&family=JetBrains+Mono:wght@300;400&display=swap" rel="stylesheet"/>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            display: ['Playfair Display', 'Georgia', 'serif'],
            body: ['Plus Jakarta Sans', 'sans-serif'],
            mono: ['JetBrains Mono', 'monospace'],
          },
          colors: {
            g: {
              50:'#f0fdf4', 100:'#dcfce7', 200:'#bbf7d0', 300:'#86efac',
              400:'#4ade80', 500:'#22c55e', 600:'#16a34a', 700:'#15803d',
              800:'#166534', 900:'#14532d',
            }
          },
          animation: {
            'float':      'float 6s ease-in-out infinite',
            'float-slow': 'float 9s ease-in-out infinite',
            'float-fast': 'float 4s ease-in-out infinite',
            'pulse-slow': 'pulse 3s ease-in-out infinite',
            'fadeUp':     'fadeUp 0.7s ease forwards',
            'slideDown':  'slideDown 0.3s ease forwards',
          },
          keyframes: {
            float:     { '0%,100%': { transform:'translateY(0px)' }, '50%': { transform:'translateY(-18px)' } },
            fadeUp:    { from: { opacity:'0', transform:'translateY(28px)' }, to: { opacity:'1', transform:'translateY(0)' } },
            slideDown: { from: { opacity:'0', transform:'translateY(-12px)' }, to: { opacity:'1', transform:'translateY(0)' } },
          }
        }
      }
    }
  </script>
  <style>
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { font-family: 'Plus Jakarta Sans', sans-serif; }

    /* ── Glassmorphism ── */
    .glass {
      background: rgba(255,255,255,0.18);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border: 1px solid rgba(255,255,255,0.35);
    }
    .glass-nav {
      background: rgba(255,255,255,0.82);
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      border: 1px solid rgba(255,255,255,0.65);
      box-shadow: 0 4px 24px rgba(20,83,45,0.10);
    }
    .glass-mobile-menu {
      background: rgba(255,255,255,0.94);
      backdrop-filter: blur(28px);
      -webkit-backdrop-filter: blur(28px);
      border-top: 1px solid rgba(134,239,172,0.3);
    }
    .glass-card {
      background: rgba(255,255,255,0.22);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid rgba(255,255,255,0.4);
      box-shadow: 0 8px 32px rgba(20,83,45,0.08), inset 0 1px 0 rgba(255,255,255,0.6);
      transition: all 0.3s ease;
    }
    .glass-card:hover {
      background: rgba(255,255,255,0.32);
      border-color: rgba(34,197,94,0.5);
      box-shadow: 0 16px 48px rgba(20,83,45,0.14), inset 0 1px 0 rgba(255,255,255,0.7);
      transform: translateY(-4px);
    }
    /* wide cards shouldn't lift on hover */
    .glass-card.no-lift:hover { transform: none; }

    /* ── Blobs ── */
    .orb { border-radius: 50%; filter: blur(60px); position: absolute; pointer-events: none; }

    /* ── Skill pills ── */
    .skill-pill {
      background: rgba(255,255,255,0.35);
      backdrop-filter: blur(8px);
      border: 1px solid rgba(255,255,255,0.5);
      transition: all 0.2s ease;
    }
    .skill-pill:hover { background: rgba(34,197,94,0.2); border-color: rgba(34,197,94,0.5); }

    /* ── Contact rows ── */
    .contact-row {
      background: rgba(255,255,255,0.2);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255,255,255,0.35);
      transition: all 0.2s ease;
    }
    .contact-row:hover { background: rgba(34,197,94,0.15); border-color: rgba(34,197,94,0.4); transform: translateX(6px); }

    /* ── Form inputs ── */
    .form-input {
      background: rgba(255,255,255,0.25);
      backdrop-filter: blur(8px);
      border: 1px solid rgba(255,255,255,0.45);
      color: #14532d;
      transition: all 0.2s ease;
    }
    .form-input:focus {
      outline: none;
      background: rgba(255,255,255,0.4);
      border-color: rgba(34,197,94,0.6);
      box-shadow: 0 0 0 3px rgba(34,197,94,0.12);
    }
    .form-input::placeholder { color: rgba(20,83,45,0.4); }

    /* ── Photo frame ── */
    .photo-frame-outer {
      background: rgba(255,255,255,0.22);
      backdrop-filter: blur(16px);
      border: 2px dashed rgba(134,239,172,0.6);
      transition: all 0.3s ease;
    }
    .photo-frame-outer:hover { border-style: solid; border-color: rgba(34,197,94,0.7); background: rgba(255,255,255,0.3); }

    /* ── Scroll reveal ── */
    .reveal, .tl-item {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }
    .reveal.show, .tl-item.show { opacity: 1; transform: translateY(0); }

    /* ── Back to top ── */
    #back-to-top {
      transition: all 0.35s cubic-bezier(0.34,1.56,0.64,1);
      transform: translateY(24px) scale(0.85);
      opacity: 0;
      pointer-events: none;
    }
    #back-to-top.visible { transform: translateY(0) scale(1); opacity: 1; pointer-events: auto; }

    /* ── Mobile menu ── */
    #mobile-menu { display: none; }
    #mobile-menu.open { display: block; animation: slideDown 0.28s ease forwards; }

    /* ── Hamburger ── */
    .ham-line {
      display: block; width: 22px; height: 2px;
      background: #166534; border-radius: 2px;
      transition: all 0.3s ease; transform-origin: center;
    }
    #ham-btn.open .ham-line:nth-child(1) { transform: translateY(7px) rotate(45deg); }
    #ham-btn.open .ham-line:nth-child(2) { opacity: 0; transform: scaleX(0); }
    #ham-btn.open .ham-line:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

    /* ── Scrollbar ── */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: rgba(34,197,94,0.4); border-radius: 99px; }
  </style>
</head>
<body class="min-h-screen overflow-x-hidden" style="background: linear-gradient(135deg, #d1fae5 0%, #f0fdf4 30%, #dcfce7 60%, #bbf7d0 100%);">

<!-- ══════════════════════════════════════════════
     BACKGROUND ORBS + GRID
══════════════════════════════════════════════ -->
<div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
  <div class="orb w-96 h-96 bg-green-300 opacity-40 top-[-80px] left-[-60px] animate-float"></div>
  <div class="orb w-80 h-80 bg-emerald-200 opacity-50 top-1/3 right-[-40px] animate-float-slow"></div>
  <div class="orb w-72 h-72 bg-green-400 opacity-25 bottom-1/4 left-1/4 animate-float-fast"></div>
  <div class="orb w-64 h-64 bg-teal-200 opacity-35 bottom-[-40px] right-1/3 animate-float"></div>
  <div class="orb w-48 h-48 bg-lime-200 opacity-40 top-2/3 left-[-20px] animate-float-slow"></div>
  <svg class="absolute inset-0 w-full h-full opacity-[0.04]" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <pattern id="grid" width="48" height="48" patternUnits="userSpaceOnUse">
        <path d="M 48 0 L 0 0 0 48" fill="none" stroke="#166534" stroke-width="1"/>
      </pattern>
    </defs>
    <rect width="100%" height="100%" fill="url(#grid)"/>
  </svg>
</div>

<!-- ══════════════════════════════════════════════
     NAV
══════════════════════════════════════════════ -->
<nav class="fixed top-0 left-0 right-0 z-50 px-3 sm:px-4 pt-3 sm:pt-4">
  <div class="glass-nav max-w-6xl mx-auto rounded-2xl">

    <!-- Top bar -->
    <div class="flex justify-between items-center px-5 py-3">
      <a href="#about" class="font-display font-bold text-g-800 text-lg tracking-tight">Sharon Unnikrishnan</a>

      <!-- Desktop links -->
      <ul class="hidden md:flex gap-1 list-none m-0 p-0">
        <li><a href="#about"      class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 px-3 py-2 rounded-xl hover:bg-g-100 hover:text-g-900 transition-all no-underline">About</a></li>
        <li><a href="#skills"     class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 px-3 py-2 rounded-xl hover:bg-g-100 hover:text-g-900 transition-all no-underline">Skills</a></li>
        <li><a href="#experience" class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 px-3 py-2 rounded-xl hover:bg-g-100 hover:text-g-900 transition-all no-underline">Experience</a></li>
        <li><a href="#projects"   class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 px-3 py-2 rounded-xl hover:bg-g-100 hover:text-g-900 transition-all no-underline">Projects</a></li>
        <li><a href="#contact"    class="font-mono text-[0.62rem] tracking-widest uppercase text-white bg-g-700 px-3 py-2 rounded-xl hover:bg-g-800 transition-all no-underline">Contact</a></li>
      </ul>

      <!-- Hamburger (mobile only) -->
      <button id="ham-btn" aria-label="Toggle menu"
        class="md:hidden flex flex-col gap-1.5 p-2 rounded-xl hover:bg-g-100 transition-colors"
        onclick="toggleMenu()">
        <span class="ham-line"></span>
        <span class="ham-line"></span>
        <span class="ham-line"></span>
      </button>
    </div>

    <!-- Mobile dropdown -->
    <div id="mobile-menu" class="md:hidden glass-mobile-menu rounded-b-2xl overflow-hidden">
      <ul class="flex flex-col list-none m-0 px-3 py-3 gap-1">
        <li><a href="#about"      onclick="closeMenu()" class="flex items-center gap-3 font-mono text-[0.68rem] tracking-widest uppercase text-g-700 px-4 py-3 rounded-xl hover:bg-g-100 transition-all no-underline">
          <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><circle cx="12" cy="8" r="4"/><path d="M4 20c0-4 3.6-7 8-7s8 3 8 7"/></svg>About</a></li>
        <li><a href="#skills"     onclick="closeMenu()" class="flex items-center gap-3 font-mono text-[0.68rem] tracking-widest uppercase text-g-700 px-4 py-3 rounded-xl hover:bg-g-100 transition-all no-underline">
          <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>Skills</a></li>
        <li><a href="#experience" onclick="closeMenu()" class="flex items-center gap-3 font-mono text-[0.68rem] tracking-widest uppercase text-g-700 px-4 py-3 rounded-xl hover:bg-g-100 transition-all no-underline">
          <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"/></svg>Experience</a></li>
        <li><a href="#projects"   onclick="closeMenu()" class="flex items-center gap-3 font-mono text-[0.68rem] tracking-widest uppercase text-g-700 px-4 py-3 rounded-xl hover:bg-g-100 transition-all no-underline">
          <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>Projects</a></li>
        <li><a href="#contact"    onclick="closeMenu()" class="flex items-center gap-3 font-mono text-[0.68rem] tracking-widest uppercase text-white bg-g-700 px-4 py-3 rounded-xl hover:bg-g-800 transition-all no-underline">
          <svg class="w-4 h-4 text-white flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>Contact</a></li>
      </ul>
    </div>
  </div>
</nav>

<!-- ══════════════════════════════════════════════
     HERO
══════════════════════════════════════════════ -->
<section id="about" class="relative z-10 min-h-screen flex items-center pt-32 pb-16 px-4">
  <div class="max-w-6xl mx-auto w-full grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">

    <!-- Left: text -->
    <div class="opacity-0 animate-fadeUp" style="animation-delay:0.1s; animation-fill-mode:forwards;">
      <!-- Status pill -->
      <div class="inline-flex items-center gap-2 glass rounded-full px-4 py-2 mb-6">
        <span class="w-2 h-2 rounded-full bg-g-500 animate-pulse-slow"></span>
        <span class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700">Available for opportunities</span>
      </div>

      <h1 class="font-display text-5xl lg:text-7xl font-bold text-g-900 leading-[1.05] tracking-tight mb-3">
        Sharon<br/><span class="text-g-600 italic">Unnikrishnan</span>
      </h1>

      <p class="font-body text-g-700 text-base font-light mb-6 leading-relaxed">
        Laravel Backend Engineer &nbsp;·&nbsp; DevOps &amp; Cloud &nbsp;·&nbsp; AI-Assisted Development
      </p>

      <div class="w-10 h-1 rounded-full bg-gradient-to-r from-g-400 to-g-700 mb-6"></div>

      <p class="text-g-800 text-[0.97rem] leading-[1.85] mb-8 max-w-lg">
        Backend engineer with <strong class="font-semibold text-g-900">7+ years of PHP experience</strong> and
        3 years of Laravel specialisation — building fintech &amp; government platforms deployed on
        <strong class="font-semibold text-g-900">AWS &amp; DigitalOcean</strong>, containerised with Docker &amp;
        Kubernetes, and productivity-boosted with <strong class="font-semibold text-g-900">AI agents</strong>
        like Claude, Cursor, ChatGPT &amp; Gemini.
      </p>

      <!-- Meta info pills -->
      <div class="flex flex-wrap gap-2 mb-8">
        <span class="glass rounded-full px-3 py-1.5 font-mono text-[0.62rem] tracking-wide text-g-700 flex items-center gap-1.5">
          <svg class="w-3 h-3 text-g-500" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>
          Kannur, Kerala, India
        </span>
        <span class="glass rounded-full px-3 py-1.5 font-mono text-[0.62rem] tracking-wide text-g-700 flex items-center gap-1.5">
          <svg class="w-3 h-3 text-g-500" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
          sharonunnikrishnan11@gmail.com
        </span>
        <span class="glass rounded-full px-3 py-1.5 font-mono text-[0.62rem] tracking-wide text-g-700 flex items-center gap-1.5">
          <svg class="w-3 h-3 text-g-500" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.4 2 2 0 0 1 3.6 1.22h3a2 2 0 0 1 2 1.72c.12.96.36 1.9.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.8a16 16 0 0 0 6.29 6.29l.94-.94a2 2 0 0 1 2.11-.45c.91.35 1.85.58 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
          +91 97476 42004
        </span>
      </div>

      <!-- CTAs -->
      <div class="flex gap-3 flex-wrap">
        <a href="mailto:sharonunnikrishnan11@gmail.com"
           class="inline-flex items-center gap-2 bg-g-700 hover:bg-g-800 text-white font-mono text-[0.68rem] tracking-widest uppercase px-5 py-3 rounded-2xl shadow-lg shadow-g-700/30 transition-all hover:-translate-y-1 hover:shadow-xl no-underline">
          <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
          Hire Me
        </a>
        <a href="https://sharonunnikrishnan.github.io/" target="_blank"
           class="inline-flex items-center gap-2 glass text-g-800 font-mono text-[0.68rem] tracking-widest uppercase px-5 py-3 rounded-2xl hover:bg-white/40 transition-all hover:-translate-y-1 no-underline">
          <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
          GitHub
        </a>
      </div>
    </div>

    <!-- Right: photo card + floating badges -->
    <div class="opacity-0 animate-fadeUp relative flex flex-col items-center" style="animation-delay:0.3s; animation-fill-mode:forwards;">

      <!-- Floating: code snippet -->
      <div class="absolute -top-6 -left-4 glass-card rounded-2xl px-4 py-3 animate-float z-20 hidden lg:block">
        <p class="font-mono text-[0.58rem] text-g-800 leading-relaxed">
          <span class="text-g-500">$</span> php artisan serve<br/>
          <span class="text-g-400">→</span> <span class="text-g-700">Server running on :8000</span>
        </p>
      </div>

      <!-- Floating: API status -->
      <div class="absolute -top-2 -right-2 glass-card rounded-2xl px-3 py-2.5 animate-float-slow z-20 hidden lg:flex items-center gap-2">
        <div class="w-7 h-7 rounded-xl bg-g-500/20 flex items-center justify-center">
          <svg class="w-4 h-4 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>
        </div>
        <div>
          <p class="font-mono text-[0.55rem] text-g-500 uppercase tracking-widest">REST API</p>
          <p class="font-semibold text-g-800 text-xs">200 OK</p>
        </div>
      </div>

      <!-- Photo frame -->
      <div class="photo-frame-outer w-60 h-80 rounded-3xl flex flex-col items-center justify-center cursor-pointer overflow-hidden relative z-10"
           onclick="document.getElementById('photo-input').click()" title="Click to upload your photo">
        <img id="profile-photo" src="" alt="Sharon Unnikrishnan" class="w-full h-full object-cover hidden rounded-3xl"/>
        <div id="photo-hint" class="flex flex-col items-center gap-3 text-g-600 px-4 text-center">
          <svg class="w-20 h-20 opacity-50" viewBox="0 0 80 80" fill="none">
            <circle cx="40" cy="28" r="14" stroke="#16a34a" stroke-width="2" fill="rgba(34,197,94,0.1)"/>
            <path d="M12 72c0-15.464 12.536-28 28-28s28 12.536 28 28" stroke="#16a34a" stroke-width="2" stroke-linecap="round" fill="rgba(34,197,94,0.1)"/>
          </svg>
          <span class="font-mono text-[0.6rem] tracking-widest uppercase leading-relaxed">Click to upload<br/>your photo</span>
        </div>
      </div>
      <input type="file" id="photo-input" accept="image/*" class="hidden"/>

      <!-- Name badge -->
      <div class="glass-card rounded-2xl px-5 py-3 mt-4 text-center z-10">
        <p class="font-display font-semibold text-g-900 text-sm">Sharon Unnikrishnan</p>
        <p class="font-mono text-[0.6rem] text-g-600 tracking-widest uppercase mt-0.5">Backend &amp; DevOps Engineer</p>
      </div>

      <!-- Floating: years badge -->
      <div class="absolute bottom-16 -left-6 glass-card rounded-2xl px-3 py-2.5 animate-float-fast z-20 hidden lg:block">
        <p class="font-mono text-[0.55rem] text-g-500 uppercase tracking-widest">Experience</p>
        <p class="font-bold text-g-800 text-sm">7+ Years</p>
      </div>

      <!-- Floating: Laravel badge -->
      <div class="absolute bottom-8 -right-4 glass-card rounded-2xl px-3 py-2.5 animate-float-slow z-20 hidden lg:block">
        <p class="font-mono text-[0.55rem] text-g-500 uppercase tracking-widest">Laravel</p>
        <p class="font-bold text-g-800 text-sm">3 Years</p>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════
     SKILLS
══════════════════════════════════════════════ -->
<section id="skills" class="relative z-10 py-20 px-4">
  <div class="max-w-6xl mx-auto">

    <!-- Section header -->
    <div class="flex flex-wrap items-end gap-4 mb-12 reveal">
      <div>
        <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-600 mb-2 flex items-center gap-2">
          <span class="w-5 h-0.5 bg-g-400 rounded-full inline-block"></span>Technical Skills
        </p>
        <h2 class="font-display text-4xl font-bold text-g-900">Core <em class="font-normal text-g-600">Competencies</em></h2>
      </div>
      <!-- Code window illustration -->
      <div class="glass-card rounded-2xl px-4 py-3 hidden md:block ml-auto">
        <svg viewBox="0 0 120 52" class="w-32" fill="none">
          <rect width="120" height="52" rx="10" fill="rgba(255,255,255,0.3)"/>
          <circle cx="14" cy="14" r="4" fill="#f87171"/>
          <circle cx="26" cy="14" r="4" fill="#fbbf24"/>
          <circle cx="38" cy="14" r="4" fill="#4ade80"/>
          <rect x="10" y="26" width="40" height="3" rx="1.5" fill="#16a34a" opacity="0.6"/>
          <rect x="10" y="33" width="60" height="3" rx="1.5" fill="#86efac" opacity="0.5"/>
          <rect x="10" y="40" width="30" height="3" rx="1.5" fill="#16a34a" opacity="0.4"/>
          <rect x="56" y="26" width="25" height="3" rx="1.5" fill="#4ade80" opacity="0.5"/>
          <rect x="76" y="33" width="34" height="3" rx="1.5" fill="#16a34a" opacity="0.3"/>
        </svg>
      </div>
    </div>

    <!-- 4-col grid (2-wide cards on last row) -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">

      <!-- Backend -->
      <div class="glass-card rounded-2xl p-5 reveal">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="m8 21 4-4 4 4M12 17v4"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">Backend</p>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">PHP</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Laravel</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">CodeIgniter</span>
        </div>
      </div>

      <!-- APIs & Payments -->
      <div class="glass-card rounded-2xl p-5 reveal">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">APIs &amp; Payments</p>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">REST APIs</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Webhooks</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">PayU</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Cashfree</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Transcorp</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Eko</span>
        </div>
      </div>

      <!-- Database -->
      <div class="glass-card rounded-2xl p-5 reveal">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><ellipse cx="12" cy="5" rx="9" ry="3"/><path d="M21 12c0 1.66-4 3-9 3s-9-1.34-9-3"/><path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">Database</p>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">MySQL</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">DB2</span>
        </div>
      </div>

      <!-- Frontend -->
      <div class="glass-card rounded-2xl p-5 reveal">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">Frontend</p>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">HTML</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">CSS</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">JavaScript</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">React.js</span>
        </div>
      </div>

      <!-- Practices -->
      <div class="glass-card rounded-2xl p-5 reveal">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">Practices</p>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Authentication</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">RBAC</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">KYC</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Cron Jobs</span>
        </div>
      </div>

      <!-- Dev Tools -->
      <div class="glass-card rounded-2xl p-5 reveal">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">Dev Tools</p>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Git</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">GitHub</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Postman</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Linux</span>
        </div>
      </div>

      <!-- DevOps & Cloud — spans 2 cols -->
      <div class="glass-card no-lift rounded-2xl p-5 reveal lg:col-span-2">
        <div class="flex flex-wrap items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center flex-shrink-0">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">DevOps &amp; Cloud</p>
          <span class="ml-auto font-mono text-[0.55rem] uppercase tracking-widest text-g-500 bg-g-100/70 px-2.5 py-1 rounded-full border border-g-200/60">Infrastructure</span>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <!-- AWS cloud icon -->
            <svg class="w-3.5 h-3.5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"/></svg>
            AWS
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <svg class="w-3.5 h-3.5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/><path d="M2 12h20"/></svg>
            DigitalOcean
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <!-- Docker: container/box icon -->
            <svg class="w-3.5 h-3.5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/></svg>
            Docker
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <!-- Kubernetes: gear/settings icon -->
            <svg class="w-3.5 h-3.5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M19.07 4.93a10 10 0 0 1 0 14.14M4.93 4.93a10 10 0 0 0 0 14.14"/></svg>
            Kubernetes
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <!-- CI/CD: arrows -->
            <svg class="w-3.5 h-3.5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>
            CI/CD Pipelines
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <svg class="w-3.5 h-3.5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
            GitHub Actions
          </span>
        </div>
      </div>

      <!-- AI Agents & Automation — spans 2 cols -->
      <div class="glass-card no-lift rounded-2xl p-5 reveal lg:col-span-2">
        <div class="flex flex-wrap items-center gap-3 mb-4">
          <div class="w-9 h-9 rounded-xl bg-g-600/20 flex items-center justify-center flex-shrink-0">
            <svg class="w-5 h-5 text-g-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 2l2.09 6.26L20 10l-5.91 1.74L12 18l-2.09-5.26L4 11l5.91-1.74z"/><path d="M5 3v4M3 5h4M19 17v4M17 19h4"/></svg>
          </div>
          <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-700 font-medium">AI Agents &amp; Automation</p>
          <span class="ml-auto font-mono text-[0.55rem] uppercase tracking-widest text-g-500 bg-g-100/70 px-2.5 py-1 rounded-full border border-g-200/60">Productivity</span>
        </div>
        <div class="flex flex-wrap gap-2">
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <span class="w-2 h-2 rounded-full bg-orange-400 flex-shrink-0"></span>
            Claude (Anthropic)
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <span class="w-2 h-2 rounded-full bg-sky-400 flex-shrink-0"></span>
            ChatGPT
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <span class="w-2 h-2 rounded-full bg-blue-500 flex-shrink-0"></span>
            Gemini
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800 flex items-center gap-1.5">
            <span class="w-2 h-2 rounded-full bg-purple-400 flex-shrink-0"></span>
            Cursor AI
          </span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">AI-Assisted Dev</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Prompt Engineering</span>
          <span class="skill-pill rounded-full px-3 py-1 font-mono text-[0.63rem] text-g-800">Workflow Automation</span>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════
     EXPERIENCE
══════════════════════════════════════════════ -->
<section id="experience" class="relative z-10 py-20 px-4">
  <div class="max-w-6xl mx-auto">

    <div class="flex flex-wrap items-end gap-4 mb-12 reveal">
      <div>
        <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-600 mb-2 flex items-center gap-2">
          <span class="w-5 h-0.5 bg-g-400 rounded-full inline-block"></span>Professional Experience
        </p>
        <h2 class="font-display text-4xl font-bold text-g-900">Career <em class="font-normal text-g-600">History</em></h2>
      </div>
      <!-- Timeline illustration -->
      <div class="glass-card rounded-2xl p-3 hidden md:block ml-auto">
        <svg viewBox="0 0 100 50" class="w-28" fill="none">
          <circle cx="16" cy="12" r="5" fill="rgba(34,197,94,0.3)" stroke="#16a34a" stroke-width="1.5"/>
          <line x1="16" y1="17" x2="16" y2="24" stroke="#86efac" stroke-width="1.5"/>
          <circle cx="16" cy="29" r="5" fill="rgba(34,197,94,0.2)" stroke="#16a34a" stroke-width="1.5"/>
          <line x1="16" y1="34" x2="16" y2="41" stroke="#86efac" stroke-width="1.5"/>
          <circle cx="16" cy="46" r="5" fill="rgba(34,197,94,0.1)" stroke="#86efac" stroke-width="1.5"/>
          <rect x="28" y="9"  width="50" height="6" rx="3" fill="#16a34a" opacity="0.5"/>
          <rect x="28" y="26" width="38" height="6" rx="3" fill="#16a34a" opacity="0.35"/>
          <rect x="28" y="43" width="44" height="6" rx="3" fill="#86efac" opacity="0.4"/>
        </svg>
      </div>
    </div>

    <div class="glass-card no-lift rounded-3xl p-6 md:p-8">

      <!-- Job 1 -->
      <div class="tl-item flex gap-4 sm:gap-6 pb-8 border-b border-white/30 mb-8">
        <div class="flex flex-col items-center gap-1 pt-1 flex-shrink-0">
          <div class="w-3 h-3 rounded-full bg-g-500 ring-4 ring-g-200/60"></div>
          <div class="w-0.5 flex-1 bg-gradient-to-b from-g-400/60 to-transparent rounded-full min-h-[60px]"></div>
        </div>
        <div class="flex-1 min-w-0">
          <div class="flex flex-wrap items-start gap-2 mb-3">
            <div>
              <p class="font-display text-base sm:text-lg font-semibold text-g-900">Backend Engineer <span class="text-g-600 font-normal italic">(Freelance Consultant)</span></p>
              <p class="font-mono text-[0.62rem] text-g-600 mt-0.5">ADSS Private Limited</p>
            </div>
            <span class="ml-auto glass rounded-full px-3 py-1 font-mono text-[0.58rem] text-g-700 tracking-wide whitespace-nowrap">Feb 2026 — Present</span>
          </div>
          <ul class="space-y-2">
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Backend consulting &amp; feature enhancements for prepaid card fintech platform.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Maintain &amp; optimise PayU, Cashfree, Eko, Transcorp integrations.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Production support, API troubleshooting, and performance improvements.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>New module development, cron optimisation, and security enhancements.</li>
          </ul>
        </div>
      </div>

      <!-- Job 2 -->
      <div class="tl-item flex gap-4 sm:gap-6 pb-8 border-b border-white/30 mb-8">
        <div class="flex flex-col items-center gap-1 pt-1 flex-shrink-0">
          <div class="w-3 h-3 rounded-full bg-g-500 ring-4 ring-g-200/60"></div>
          <div class="w-0.5 flex-1 bg-gradient-to-b from-g-400/60 to-transparent rounded-full min-h-[60px]"></div>
        </div>
        <div class="flex-1 min-w-0">
          <div class="flex flex-wrap items-start gap-2 mb-3">
            <div>
              <p class="font-display text-base sm:text-lg font-semibold text-g-900">Assistant Manager — Backend Development</p>
              <p class="font-mono text-[0.62rem] text-g-600 mt-0.5">ADSS Private Limited</p>
            </div>
            <span class="ml-auto glass rounded-full px-3 py-1 font-mono text-[0.58rem] text-g-700 tracking-wide whitespace-nowrap">Jan 2023 — Jan 2026</span>
          </div>
          <ul class="space-y-2">
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Owned backend of prepaid card fintech platform; high-volume financial transactions.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Integrated PayU, Cashfree, Eko, Transcorp payments &amp; financial APIs.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>KYC workflows via Laravel REST APIs, secure auth, RBAC.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Cron jobs for settlements and reports; backend architecture &amp; critical fixes.</li>
          </ul>
        </div>
      </div>

      <!-- Job 3 -->
      <div class="tl-item flex gap-4 sm:gap-6 pb-8 border-b border-white/30 mb-8">
        <div class="flex flex-col items-center gap-1 pt-1 flex-shrink-0">
          <div class="w-3 h-3 rounded-full bg-g-400 ring-4 ring-g-200/60"></div>
          <div class="w-0.5 flex-1 bg-gradient-to-b from-g-300/60 to-transparent rounded-full min-h-[60px]"></div>
        </div>
        <div class="flex-1 min-w-0">
          <div class="flex flex-wrap items-start gap-2 mb-3">
            <div>
              <p class="font-display text-base sm:text-lg font-semibold text-g-900">Project Engineer <span class="text-g-600 font-normal italic">(Contract)</span></p>
              <p class="font-mono text-[0.62rem] text-g-600 mt-0.5">National Informatics Centre (NIC)</p>
            </div>
            <span class="ml-auto glass rounded-full px-3 py-1 font-mono text-[0.58rem] text-g-700 tracking-wide whitespace-nowrap">Jul 2018 — Dec 2021</span>
          </div>
          <ul class="space-y-2">
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Treasury Savings Bank system development in a government environment.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Enhanced accounts, fixed deposits, and interest calculation modules.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Resolved production issues and ensured system stability.</li>
          </ul>
        </div>
      </div>

      <!-- Job 4 -->
      <div class="tl-item flex gap-4 sm:gap-6">
        <div class="flex flex-col items-center gap-1 pt-1 flex-shrink-0">
          <div class="w-3 h-3 rounded-full bg-g-300 ring-4 ring-g-200/60"></div>
        </div>
        <div class="flex-1 min-w-0">
          <div class="flex flex-wrap items-start gap-2 mb-3">
            <div>
              <p class="font-display text-base sm:text-lg font-semibold text-g-900">PHP Developer</p>
              <p class="font-mono text-[0.62rem] text-g-600 mt-0.5">SANS IT Consultancy</p>
            </div>
            <span class="ml-auto glass rounded-full px-3 py-1 font-mono text-[0.58rem] text-g-700 tracking-wide whitespace-nowrap">Apr 2017 — Apr 2018</span>
          </div>
          <ul class="space-y-2">
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Backend modules for HRMS using core PHP.</li>
            <li class="text-g-800 text-sm flex gap-2"><span class="text-g-400 mt-1 flex-shrink-0">▸</span>Employee data &amp; leave management workflows.</li>
          </ul>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════
     PROJECTS
══════════════════════════════════════════════ -->
<section id="projects" class="relative z-10 py-20 px-4">
  <div class="max-w-6xl mx-auto">

    <div class="mb-12 reveal">
      <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-600 mb-2 flex items-center gap-2">
        <span class="w-5 h-0.5 bg-g-400 rounded-full inline-block"></span>Key Projects
      </p>
      <h2 class="font-display text-4xl font-bold text-g-900">Notable <em class="font-normal text-g-600">Work</em></h2>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-5">

      <!-- MyDop -->
      <div class="glass-card rounded-3xl p-6 relative overflow-hidden reveal group">
        <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-g-400 to-g-700 rounded-t-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
        <div class="mb-5 flex justify-center">
          <svg viewBox="0 0 120 80" class="w-32 h-20" fill="none">
            <rect x="10" y="20" width="100" height="60" rx="10" fill="rgba(34,197,94,0.12)" stroke="rgba(34,197,94,0.3)" stroke-width="1.5"/>
            <rect x="10" y="20" width="100" height="22" rx="10" fill="rgba(34,197,94,0.2)"/>
            <rect x="10" y="32" width="100" height="10" fill="rgba(34,197,94,0.15)"/>
            <rect x="22" y="52" width="30" height="5" rx="2.5" fill="rgba(22,101,52,0.4)"/>
            <rect x="22" y="62" width="50" height="4" rx="2" fill="rgba(134,239,172,0.5)"/>
            <circle cx="88" cy="57" r="10" fill="rgba(34,197,94,0.2)" stroke="rgba(34,197,94,0.5)" stroke-width="1.5"/>
            <path d="M88 52v10M83 57h10" stroke="#16a34a" stroke-width="1.5" stroke-linecap="round"/>
            <rect x="20" y="25" width="35" height="4" rx="2" fill="rgba(255,255,255,0.6)"/>
          </svg>
        </div>
        <p class="font-mono text-[0.55rem] tracking-widest uppercase text-g-500 mb-1">Project 01 · Laravel · Fintech</p>
        <p class="font-display text-xl font-bold text-g-900 mb-2">MyDop</p>
        <p class="text-g-700 text-sm leading-relaxed">Prepaid card platform — KYC onboarding, bill payments, money transfers, and multi-gateway payment integrations (PayU, Cashfree, Eko, Transcorp).</p>
      </div>

      <!-- Treasury Savings Bank -->
      <div class="glass-card rounded-3xl p-6 relative overflow-hidden reveal group">
        <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-g-400 to-g-700 rounded-t-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
        <div class="mb-5 flex justify-center">
          <svg viewBox="0 0 120 80" class="w-32 h-20" fill="none">
            <rect x="15" y="35" width="90" height="45" rx="4" fill="rgba(34,197,94,0.1)" stroke="rgba(34,197,94,0.25)" stroke-width="1.5"/>
            <polygon points="60,8 100,35 20,35" fill="rgba(34,197,94,0.2)" stroke="rgba(34,197,94,0.4)" stroke-width="1.5"/>
            <rect x="26" y="42" width="12" height="30" rx="2" fill="rgba(22,101,52,0.3)"/>
            <rect x="44" y="42" width="12" height="30" rx="2" fill="rgba(22,101,52,0.3)"/>
            <rect x="62" y="42" width="12" height="30" rx="2" fill="rgba(22,101,52,0.3)"/>
            <rect x="80" y="42" width="12" height="30" rx="2" fill="rgba(22,101,52,0.3)"/>
            <rect x="15" y="72" width="90" height="5" rx="2" fill="rgba(34,197,94,0.3)"/>
            <circle cx="60" cy="22" r="5" fill="rgba(255,255,255,0.5)" stroke="rgba(34,197,94,0.4)" stroke-width="1"/>
          </svg>
        </div>
        <p class="font-mono text-[0.55rem] tracking-widest uppercase text-g-500 mb-1">Project 02 · PHP · Government</p>
        <p class="font-display text-xl font-bold text-g-900 mb-2">Treasury Savings Bank</p>
        <p class="text-g-700 text-sm leading-relaxed">Government banking system enhancements — accounts, fixed deposits, and interest calculation modules for the National Informatics Centre.</p>
      </div>

      <!-- HRMS -->
      <div class="glass-card rounded-3xl p-6 relative overflow-hidden reveal group">
        <div class="absolute top-0 left-0 right-0 h-1 bg-gradient-to-r from-g-400 to-g-700 rounded-t-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
        <div class="mb-5 flex justify-center">
          <svg viewBox="0 0 120 80" class="w-32 h-20" fill="none">
            <circle cx="40" cy="28" r="12" fill="rgba(34,197,94,0.15)" stroke="rgba(34,197,94,0.35)" stroke-width="1.5"/>
            <circle cx="80" cy="28" r="12" fill="rgba(34,197,94,0.1)" stroke="rgba(34,197,94,0.25)" stroke-width="1.5"/>
            <path d="M18 72c0-12 10-20 22-20s22 8 22 20" stroke="rgba(34,197,94,0.4)" stroke-width="1.5" stroke-linecap="round" fill="rgba(34,197,94,0.08)"/>
            <path d="M58 72c0-12 10-20 22-20s22 8 22 20" stroke="rgba(134,239,172,0.5)" stroke-width="1.5" stroke-linecap="round" fill="rgba(34,197,94,0.05)"/>
            <rect x="48" y="38" width="24" height="18" rx="4" fill="rgba(34,197,94,0.2)" stroke="rgba(34,197,94,0.4)" stroke-width="1"/>
            <path d="M54 47h12M54 52h8" stroke="#16a34a" stroke-width="1.2" stroke-linecap="round"/>
          </svg>
        </div>
        <p class="font-mono text-[0.55rem] tracking-widest uppercase text-g-500 mb-1">Project 03 · Core PHP · MySQL</p>
        <p class="font-display text-xl font-bold text-g-900 mb-2">HRMS</p>
        <p class="text-g-700 text-sm leading-relaxed">Human Resource Management System — employee data handling and leave management workflows built on core PHP with MySQL backend.</p>
      </div>

    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════
     EDUCATION
══════════════════════════════════════════════ -->
<section class="relative z-10 py-20 px-4">
  <div class="max-w-6xl mx-auto">

    <div class="mb-12 reveal">
      <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-600 mb-2 flex items-center gap-2">
        <span class="w-5 h-0.5 bg-g-400 rounded-full inline-block"></span>Education
      </p>
      <h2 class="font-display text-4xl font-bold text-g-900">Academic <em class="font-normal text-g-600">Background</em></h2>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
      <div class="glass-card rounded-3xl p-6 flex gap-5 items-start reveal">
        <div class="w-14 h-14 rounded-2xl bg-g-500/15 flex items-center justify-center flex-shrink-0">
          <svg class="w-8 h-8 text-g-600" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>
        </div>
        <div>
          <p class="font-display text-lg font-semibold text-g-900 mb-1">Master of Computer Applications</p>
          <p class="font-body text-g-600 italic text-sm mb-3">VTU University</p>
          <span class="glass rounded-full px-3 py-1 font-mono text-[0.6rem] text-g-700">2015</span>
        </div>
      </div>
      <div class="glass-card rounded-3xl p-6 flex gap-5 items-start reveal">
        <div class="w-14 h-14 rounded-2xl bg-g-500/15 flex items-center justify-center flex-shrink-0">
          <svg class="w-8 h-8 text-g-600" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"/></svg>
        </div>
        <div>
          <p class="font-display text-lg font-semibold text-g-900 mb-1">Bachelor of Computer Applications</p>
          <p class="font-body text-g-600 italic text-sm mb-3">Mangalore University</p>
          <span class="glass rounded-full px-3 py-1 font-mono text-[0.6rem] text-g-700">2012</span>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ══════════════════════════════════════════════
     CONTACT
══════════════════════════════════════════════ -->
<section id="contact" class="relative z-10 py-20 px-4">
  <div class="max-w-6xl mx-auto">

    <div class="mb-12 reveal">
      <p class="font-mono text-[0.62rem] tracking-widest uppercase text-g-600 mb-2 flex items-center gap-2">
        <span class="w-5 h-0.5 bg-g-400 rounded-full inline-block"></span>Contact
      </p>
      <h2 class="font-display text-4xl font-bold text-g-900">Get In <em class="font-normal text-g-600">Touch</em></h2>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">

      <!-- Left: info -->
      <div class="reveal">
        <!-- Envelope illustration card -->
        <div class="glass-card no-lift rounded-3xl p-6 mb-6 flex items-center gap-5">
          <svg viewBox="0 0 80 60" class="w-20 h-16 flex-shrink-0" fill="none">
            <rect x="4" y="8" width="72" height="48" rx="8" fill="rgba(34,197,94,0.12)" stroke="rgba(34,197,94,0.3)" stroke-width="1.5"/>
            <path d="M4 16l36 22 36-22" stroke="rgba(34,197,94,0.5)" stroke-width="1.5"/>
            <path d="M4 56l26-20M76 56L50 36" stroke="rgba(134,239,172,0.4)" stroke-width="1.2" stroke-linecap="round"/>
            <circle cx="62" cy="16" r="10" fill="rgba(34,197,94,0.2)" stroke="rgba(34,197,94,0.4)" stroke-width="1.2"/>
            <path d="M58 16h8M62 12v8" stroke="#16a34a" stroke-width="1.5" stroke-linecap="round"/>
          </svg>
          <p class="font-body text-g-800 text-sm leading-relaxed">Available for freelance, full-time roles, and fintech consulting. Based in Kannur, Kerala — open to remote opportunities worldwide.</p>
        </div>

        <!-- Contact links -->
        <div class="flex flex-col gap-3">
          <a href="mailto:sharonunnikrishnan11@gmail.com" class="contact-row rounded-2xl px-4 py-3.5 flex items-center gap-3 text-g-800 font-mono text-[0.68rem] no-underline">
            <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
            sharonunnikrishnan11@gmail.com
          </a>
          <a href="tel:+919747642004" class="contact-row rounded-2xl px-4 py-3.5 flex items-center gap-3 text-g-800 font-mono text-[0.68rem] no-underline">
            <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.4 2 2 0 0 1 3.6 1.22h3a2 2 0 0 1 2 1.72c.12.96.36 1.9.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.8a16 16 0 0 0 6.29 6.29l.94-.94a2 2 0 0 1 2.11-.45c.91.35 1.85.58 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
            +91 97476 42004
          </a>
          <a href="https://sharonunnikrishnan.github.io/" target="_blank" class="contact-row rounded-2xl px-4 py-3.5 flex items-center gap-3 text-g-800 font-mono text-[0.68rem] no-underline">
            <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
            https://sharonunnikrishnan.github.io/
          </a>
          <div class="contact-row rounded-2xl px-4 py-3.5 flex items-center gap-3 text-g-800 font-mono text-[0.68rem]">
            <svg class="w-4 h-4 text-g-500 flex-shrink-0" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>
            Kannur, Kerala, India
          </div>
        </div>
      </div>

      <!-- Right: contact form -->
      <div class="glass-card no-lift rounded-3xl p-6 md:p-8 reveal">
        <form onsubmit="handleSubmit(event)" class="flex flex-col gap-4">
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div class="flex flex-col gap-1.5">
              <label class="font-mono text-[0.58rem] tracking-widest uppercase text-g-600">Full Name</label>
              <input type="text" placeholder="Your name" required class="form-input rounded-xl px-4 py-3 font-body text-sm"/>
            </div>
            <div class="flex flex-col gap-1.5">
              <label class="font-mono text-[0.58rem] tracking-widest uppercase text-g-600">Email</label>
              <input type="email" placeholder="your@email.com" required class="form-input rounded-xl px-4 py-3 font-body text-sm"/>
            </div>
          </div>
          <div class="flex flex-col gap-1.5">
            <label class="font-mono text-[0.58rem] tracking-widest uppercase text-g-600">Subject</label>
            <input type="text" placeholder="Job opportunity / Project inquiry" required class="form-input rounded-xl px-4 py-3 font-body text-sm"/>
          </div>
          <div class="flex flex-col gap-1.5">
            <label class="font-mono text-[0.58rem] tracking-widest uppercase text-g-600">Message</label>
            <textarea rows="5" placeholder="Tell me about your project or opportunity…" required class="form-input rounded-xl px-4 py-3 font-body text-sm resize-none"></textarea>
          </div>
          <button type="submit" id="send-btn"
            class="inline-flex items-center justify-center gap-2 bg-g-700 hover:bg-g-800 text-white font-mono text-[0.68rem] tracking-widest uppercase px-6 py-3.5 rounded-xl shadow-lg shadow-g-700/30 transition-all hover:-translate-y-1 hover:shadow-xl mt-1">
            Send Message
            <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
          </button>
        </form>
      </div>

    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════
     FOOTER
══════════════════════════════════════════════ -->
<footer class="relative z-10 px-4 pb-6">
  <div class="max-w-6xl mx-auto glass-card no-lift rounded-3xl px-8 py-5 flex flex-col sm:flex-row justify-between items-center gap-3">
    <p class="font-mono text-[0.62rem] text-g-700 tracking-wide">© 2025 Sharon Unnikrishnan. All rights reserved.</p>
    <a href="https://sharonunnikrishnan.github.io/" target="_blank" class="font-mono text-[0.62rem] text-g-600 hover:text-g-800 transition-colors no-underline">https://sharonunnikrishnan.github.io/</a>
  </div>
</footer>

<!-- ══════════════════════════════════════════════
     BACK TO TOP BUTTON
══════════════════════════════════════════════ -->
<button id="back-to-top"
  onclick="scrollToTop()"
  aria-label="Back to top"
  class="fixed bottom-6 right-6 z-50 w-12 h-12 rounded-2xl glass-card flex items-center justify-center shadow-lg shadow-g-700/20 hover:bg-white/50 hover:shadow-xl hover:shadow-g-700/25 active:scale-95">
  <svg class="w-5 h-5 text-g-700" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
    <path d="M18 15l-6-6-6 6"/>
  </svg>
</button>

<!-- ══════════════════════════════════════════════
     JAVASCRIPT
══════════════════════════════════════════════ -->
<script>
  /* ── Mobile menu ── */
  function toggleMenu() {
    const menu = document.getElementById('mobile-menu');
    const btn  = document.getElementById('ham-btn');
    const isOpen = menu.classList.contains('open');
    menu.classList.toggle('open', !isOpen);
    btn.classList.toggle('open', !isOpen);
  }

  function closeMenu() {
    document.getElementById('mobile-menu').classList.remove('open');
    document.getElementById('ham-btn').classList.remove('open');
  }

  /* Close on outside click */
  document.addEventListener('click', e => {
    const nav = document.querySelector('nav');
    if (nav && !nav.contains(e.target)) closeMenu();
  });

  /* ── Photo upload ── */
  document.getElementById('photo-input').addEventListener('change', e => {
    const file = e.target.files[0];
    if (!file) return;
    const reader = new FileReader();
    reader.onload = ev => {
      const img = document.getElementById('profile-photo');
      img.src = ev.target.result;
      img.classList.remove('hidden');
      document.getElementById('photo-hint').classList.add('hidden');
    };
    reader.readAsDataURL(file);
  });

  /* ── Scroll reveal (Intersection Observer) ── */
  const revealObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const delay = parseInt(entry.target.dataset.delay || 0);
        setTimeout(() => entry.target.classList.add('show'), delay);
        revealObserver.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach((el, i) => {
    el.dataset.delay = (i % 4) * 80;
    revealObserver.observe(el);
  });

  document.querySelectorAll('.tl-item').forEach((el, i) => {
    el.dataset.delay = i * 130;
    revealObserver.observe(el);
  });

  /* ── Back to top ── */
  const bttBtn = document.getElementById('back-to-top');
  window.addEventListener('scroll', () => {
    bttBtn.classList.toggle('visible', window.scrollY > 400);
  }, { passive: true });

  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  /* ── Contact form submit ── */
  function handleSubmit(e) {
    e.preventDefault();
    const btn = document.getElementById('send-btn');
    const orig = btn.innerHTML;
    btn.innerHTML = '✓ &nbsp;Message Sent!';
    btn.style.background = '#14532d';
    btn.disabled = true;
    setTimeout(() => {
      btn.innerHTML = orig;
      btn.style.background = '';
      btn.disabled = false;
      e.target.reset();
    }, 3500);
  }
</script>
</body>
</html>
