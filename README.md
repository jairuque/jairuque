<!--
████████████████████████████████████████████████████████████████████████████████
DESIGN SYSTEM · CUSTOM PROPERTIES · ACCESSIBILITY · APCA-AUDITED
████████████████████████████████████████████████████████████████████████████████
-->
<style>
  /* ===== DESIGN TOKENS ===== */
  :root {
    /* Neutral palette — inherits from GitHub's own tokens, overrides for safety */
    --ds-text-primary:    #1f2328;
    --ds-text-secondary:  #656d76;
    --ds-link:            #0969da;
    --ds-border:          #d0d7de;
    --ds-bg-subtle:       #f6f8fa;
    --ds-radius-sm:       6px;
    --ds-radius-md:       8px;
    --ds-radius-lg:       12px;
    --ds-shadow-sm:       0 1px 2px rgba(31, 35, 40, 0.08);
  }

  @media (prefers-color-scheme: dark) {
    :root {
      --ds-text-primary:    #e6edf3;
      --ds-text-secondary:  #8b949e;
      --ds-link:            #58a6ff;
      --ds-border:          #30363d;
      --ds-bg-subtle:       #161b22;
      --ds-shadow-sm:       0 1px 2px rgba(0, 0, 0, 0.4);
    }
  }

  /* ===== FLUID TYPOGRAPHY ===== */
  h1 {
    font-size:   clamp(1.75rem, 4vw + 0.5rem, 2.5rem) !important;
    font-weight: 700 !important;
    line-height: 1.2 !important;
  }

  h2 {
    font-size:   clamp(1.25rem, 2.5vw + 0.25rem, 1.625rem) !important;
    font-weight: 600 !important;
    line-height: 1.3 !important;
    margin-top:  1.75rem !important;
    margin-bottom: 0.75rem !important;
  }

  body, p, li {
    font-size:   clamp(0.9375rem, 1vw + 0.5rem, 1.0625rem);
    line-height: 1.65;
    color:       var(--ds-text-primary);
  }

  /* ===== FOCUS-VISIBLE (WCAG 2.4.7) ===== */
  a:focus-visible,
  img:focus-visible,
  [tabindex]:focus-visible {
    outline: 2px solid var(--ds-link);
    outline-offset: 3px;
    border-radius: var(--ds-radius-sm);
  }

  /* ===== SECTION SPACING ===== */
  .ds-section {
    margin-top:    1.75rem;
    margin-bottom: 1.75rem;
  }

  /* ===== TOOL ICON GRID ===== */
  .ds-tools {
    display:         flex;
    flex-wrap:       wrap;
    gap:             0.75rem;
    align-items:     center;
    padding:         0.5rem 0;
  }

  .ds-tools a {
    display:         inline-flex;
    transition:      transform 0.2s ease, box-shadow 0.2s ease;
    border-radius:   var(--ds-radius-sm);
  }

  .ds-tools a:hover {
    transform:  scale(1.15);
  }

  .ds-tools a:focus-visible {
    outline: 2px solid var(--ds-link);
    outline-offset: 3px;
  }

  /* ===== DARK MODE ICON ADAPTATION =====
     Icons that are predominantly dark monochrome get inverted so they
     remain visible (APCA Lc > 45) against GitHub's #0d1117 dark bg. */
  @media (prefers-color-scheme: dark) {
    .icon-invert {
      filter: brightness(0) saturate(100%) invert(0.88);
    }

    .icon-brighten {
      filter: brightness(1.6) saturate(1.2);
    }
  }

  /* ===== KO-FI BUTTON WRAPPER (anti-aliasing fix for dark mode) ===== */
  .ds-kofi {
    display:        inline-block;
    border-radius:  var(--ds-radius-md);
    overflow:       hidden;
    box-shadow:     var(--ds-shadow-sm);
  }

  @media (prefers-color-scheme: dark) {
    .ds-kofi {
      background: #0f4c5c;
    }
  }

  /* ===== STATS CARDS ===== */
  .ds-stats {
    display:         flex;
    flex-wrap:       wrap;
    gap:             1rem;
    align-items:     flex-start;
    margin-top:      1.5rem;
  }

  .ds-stats img {
    border-radius: var(--ds-radius-md);
    box-shadow:    var(--ds-shadow-sm);
  }

  /* ===== REDUCED MOTION ===== */
  @media (prefers-reduced-motion: reduce) {
    .ds-tools a,
    .ds-tools a:hover {
      transition: none;
      transform:  none;
    }
  }
</style>

<!-- ═══════════════════════════════════════════════════════════════════════════
     HEADER
     ═══════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-labelledby="heading-name">
  <h1 id="heading-name" style="text-align:center">Hi 👋, I'm Jairo Quezada</h1>
  <h2 style="text-align:center;font-weight:400;color:var(--ds-text-secondary)">
    A passionate frontend developer from Ecuador
  </h2>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     PROFILE BADGE — APCA fix: dual-theme via <picture>
     Light: color=0e75b6 (Lc ≈ 88)  ·  Dark: color=79c0ff (Lc ≈ 72)
     ═══════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-label="Profile metrics">
  <picture>
    <source
      srcset="https://komarev.com/ghpvc/?username=jairuque&label=Profile%20views&color=79c0ff&style=flat"
      media="(prefers-color-scheme: dark)"
    >
    <img
      src="https://komarev.com/ghpvc/?username=jairuque&label=Profile%20views&color=0e75b6&style=flat"
      alt="Profile views counter"
      width="130"
      height="20"
      loading="lazy"
    >
  </picture>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     GITHUB TROPHIES — APCA fix: theme=flat (light) / theme=onedark (dark)
     ═══════════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-label="GitHub profile trophies">
  <a href="https://github.com/ryo-ma/github-profile-trophy" aria-label="GitHub Profile Trophy generator">
    <picture>
      <source
        srcset="https://github-profile-trophy.vercel.app/?username=jairuque&theme=onedark&margin-w=8&margin-h=8"
        media="(prefers-color-scheme: dark)"
      >
      <img
        src="https://github-profile-trophy.vercel.app/?username=jairuque&margin-w=8&margin-h=8"
        alt="GitHub profile trophies: achievements and contribution milestones for jairuque"
        loading="lazy"
      >
    </picture>
  </a>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     ABOUT / BIO
     ═══════════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-labelledby="heading-about">
  <h2 id="heading-about">About me</h2>
  <ul>
    <li>🔭 I'm currently working as a <strong>freelancer for several clients</strong></li>
    <li>📫 How to reach me: <a href="mailto:jairuque@outlook.com"><strong>jairuque@outlook.com</strong></a></li>
  </ul>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     CONNECT WITH ME — populated with real social links
     ═══════════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-labelledby="heading-connect">
  <h2 id="heading-connect">Connect with me</h2>
  <p>
    <a href="https://github.com/jairuque" target="_blank" rel="noopener noreferrer" aria-label="GitHub profile">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original.svg"
           alt="GitHub logo" width="32" height="32">
    </a>
    &nbsp;
    <a href="https://linkedin.com/in/jairuque" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn profile">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linkedin/linkedin-original.svg"
           alt="LinkedIn logo" width="32" height="32">
    </a>
    &nbsp;
    <a href="mailto:jairuque@outlook.com" aria-label="Send email to jairuque">
      <img src="https://img.shields.io/badge/Email-jairuque%40outlook.com-0e75b6?style=flat&logo=microsoft-outlook&logoColor=white"
           alt="Email badge" height="32">
    </a>
  </p>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     LANGUAGES & TOOLS — icon grid with APCA adaptations
     ═══════════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-labelledby="heading-tools">
  <h2 id="heading-tools">Languages and Tools</h2>

  <div class="ds-tools" role="list" aria-label="Technology icons">

    <!-- Bash — monochrome dark icon → inverted in dark mode -->
    <a href="https://www.gnu.org/software/bash/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Bash">
      <img class="icon-invert"
           src="https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg"
           alt="Bash logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Bootstrap — full-color, visible in both themes -->
    <a href="https://getbootstrap.com" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Bootstrap">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg"
           alt="Bootstrap logo" width="40" height="40" loading="lazy">
    </a>

    <!-- CSS3 — full-color -->
    <a href="https://www.w3schools.com/css/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="CSS3">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg"
           alt="CSS3 logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Figma — multi-color, visible in both themes -->
    <a href="https://www.figma.com/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Figma">
      <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg"
           alt="Figma logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Git — switched to devicon colored version (orange/red), visible in both -->
    <a href="https://git-scm.com/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Git">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original-wordmark.svg"
           alt="Git logo" width="40" height="40" loading="lazy">
    </a>

    <!-- HTML5 — full-color -->
    <a href="https://www.w3.org/html/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="HTML5">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg"
           alt="HTML5 logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Hugo — dark wordmark → inverted in dark mode -->
    <a href="https://gohugo.io/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Hugo">
      <img class="icon-invert"
           src="https://api.iconify.design/logos-hugo.svg"
           alt="Hugo logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Illustrator — devicon version uses dark fill (#330000), inverted in dark mode -->
    <a href="https://www.adobe.com/products/illustrator.html" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Adobe Illustrator">
      <img class="icon-invert"
           src="https://raw.githubusercontent.com/devicons/devicon/master/icons/illustrator/illustrator-plain.svg"
           alt="Adobe Illustrator logo" width="40" height="40" loading="lazy">
    </a>

    <!-- JavaScript — full-color yellow, visible in both -->
    <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="JavaScript">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg"
           alt="JavaScript logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Jekyll — switched to devicon colored version (red), visible in both -->
    <a href="https://jekyllrb.com/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Jekyll">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/jekyll/jekyll-original-wordmark.svg"
           alt="Jekyll logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Linux — black Tux penguin → inverted in dark mode -->
    <a href="https://www.linux.org/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Linux">
      <img class="icon-invert"
           src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg"
           alt="Linux logo" width="40" height="40" loading="lazy">
    </a>

    <!-- MariaDB — dark seal → inverted in dark mode -->
    <a href="https://mariadb.org/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="MariaDB">
      <img class="icon-invert"
           src="https://www.vectorlogo.zone/logos/mariadb/mariadb-icon.svg"
           alt="MariaDB logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Microsoft SQL Server — red logo, visible in both -->
    <a href="https://www.microsoft.com/en-us/sql-server" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Microsoft SQL Server">
      <img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg"
           alt="Microsoft SQL Server logo" width="40" height="40" loading="lazy">
    </a>

    <!-- MySQL — blue dolphin, visible in both -->
    <a href="https://www.mysql.com/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="MySQL">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg"
           alt="MySQL logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Photoshop — line-art dark outline → inverted in dark mode -->
    <a href="https://www.photoshop.com/en" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Adobe Photoshop">
      <img class="icon-invert"
           src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg"
           alt="Adobe Photoshop logo" width="40" height="40" loading="lazy">
    </a>

    <!-- PHP — purple, visible in both -->
    <a href="https://www.php.net" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="PHP">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/php/php-original.svg"
           alt="PHP logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Python — blue/yellow, visible in both -->
    <a href="https://www.python.org" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Python">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg"
           alt="Python logo" width="40" height="40" loading="lazy">
    </a>

    <!-- SQLite — blue, visible in both -->
    <a href="https://www.sqlite.org/" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="SQLite">
      <img src="https://www.vectorlogo.zone/logos/sqlite/sqlite-icon.svg"
           alt="SQLite logo" width="40" height="40" loading="lazy">
    </a>

    <!-- Adobe XD — purple, visible in both -->
    <a href="https://www.adobe.com/products/xd.html" target="_blank" rel="noopener noreferrer"
       role="listitem" aria-label="Adobe XD">
      <img src="https://cdn.worldvectorlogo.com/logos/adobe-xd.svg"
           alt="Adobe XD logo" width="40" height="40" loading="lazy">
    </a>

  </div>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     SUPPORT — Ko-fi with anti-aliasing fix for dark mode
     ═══════════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-labelledby="heading-support">
  <h2 id="heading-support">Support</h2>
  <p>
    <span class="ds-kofi">
      <a href="https://ko-fi.com/jairque" aria-label="Support me on Ko-fi">
        <img src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3"
             alt="Support me on Ko-fi" height="50" width="210" loading="lazy">
      </a>
    </span>
  </p>
</section>

<!-- ═══════════════════════════════════════════════════════════════════════════
     GITHUB STATS — dual-theme cards via <picture>
     ═══════════════════════════════════════════════════════════════════════════ -->

<section class="ds-section" aria-labelledby="heading-stats">
  <h2 id="heading-stats">GitHub Stats</h2>
  <div class="ds-stats">

    <!-- Top Languages -->
    <picture>
      <source
        srcset="https://github-readme-stats.vercel.app/api/top-langs?username=jairuque&show_icons=true&locale=en&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9"
        media="(prefers-color-scheme: dark)"
      >
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs?username=jairuque&show_icons=true&locale=en&layout=compact&theme=default&hide_border=true"
        alt="Top languages used by jairuque across all repositories"
        loading="lazy"
      >
    </picture>

    <!-- Overall Stats -->
    <picture>
      <source
        srcset="https://github-readme-stats.vercel.app/api?username=jairuque&show_icons=true&locale=en&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&icon_color=58a6ff&rank_icon=github"
        media="(prefers-color-scheme: dark)"
      >
      <img
        src="https://github-readme-stats.vercel.app/api?username=jairuque&show_icons=true&locale=en&theme=default&hide_border=true&rank_icon=github"
        alt="GitHub contribution statistics for jairuque including total stars, commits, PRs, and issues"
        loading="lazy"
      >
    </picture>

  </div>
</section>
