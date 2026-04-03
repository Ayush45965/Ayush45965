
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;700;800&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --c: #00ff9d;
    --c2: #00cfff;
    --c3: #ff4fd8;
    --bg: #050c13;
    --bg2: #0a1520;
    --bg3: #0d1e2e;
    --txt: #cde8ff;
    --muted: #5a8aaa;
    --border: rgba(0,255,157,0.15);
  }

  .readme {
    background: var(--bg);
    font-family: 'JetBrains Mono', monospace;
    color: var(--txt);
    padding: 2rem;
    min-height: 100vh;
    position: relative;
    overflow: hidden;
  }

  .grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,157,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,157,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .scanline {
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      to bottom,
      transparent 0px,
      transparent 3px,
      rgba(0,0,0,0.08) 3px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 0;
  }

  .content { position: relative; z-index: 1; max-width: 860px; margin: 0 auto; }

  /* HERO */
  .hero {
    border: 1px solid var(--border);
    background: linear-gradient(135deg, rgba(0,255,157,0.04), rgba(0,207,255,0.04));
    border-radius: 4px;
    padding: 2.5rem 2rem;
    margin-bottom: 1.5rem;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--c), var(--c2), transparent);
  }

  .hero-tag {
    font-size: 10px;
    color: var(--c);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 1rem;
    opacity: 0.7;
  }

  .hero-tag::before { content: '> '; color: var(--muted); }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.5rem, 7vw, 4.5rem);
    font-weight: 800;
    line-height: 1;
    margin-bottom: 0.5rem;
    background: linear-gradient(135deg, #fff 0%, var(--c) 50%, var(--c2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    font-size: 13px;
    color: var(--c2);
    letter-spacing: 1px;
    margin-bottom: 1.5rem;
  }

  .hero-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 1.5rem;
  }

  .badge {
    font-size: 10px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 4px 10px;
    border-radius: 2px;
    border: 1px solid;
  }

  .badge-green { border-color: var(--c); color: var(--c); background: rgba(0,255,157,0.05); }
  .badge-blue { border-color: var(--c2); color: var(--c2); background: rgba(0,207,255,0.05); }
  .badge-pink { border-color: var(--c3); color: var(--c3); background: rgba(255,79,216,0.05); }

  .hero-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.8;
    max-width: 560px;
  }

  .hero-corner {
    position: absolute;
    bottom: 1rem;
    right: 1.5rem;
    font-size: 10px;
    color: rgba(0,255,157,0.2);
    letter-spacing: 2px;
  }

  /* SECTION */
  .section {
    border: 1px solid var(--border);
    background: var(--bg2);
    border-radius: 4px;
    margin-bottom: 1.5rem;
    overflow: hidden;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 0.75rem 1.25rem;
    border-bottom: 1px solid var(--border);
    background: rgba(0,255,157,0.03);
  }

  .section-dot {
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: var(--c);
  }

  .section-title {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--c);
  }

  .section-body { padding: 1.25rem; }

  /* SKILLS GRID */
  .skill-group { margin-bottom: 1.25rem; }
  .skill-group:last-child { margin-bottom: 0; }

  .skill-group-label {
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 10px;
    padding-bottom: 6px;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .skill-tag {
    font-size: 11px;
    padding: 5px 10px;
    border: 1px solid rgba(0,207,255,0.2);
    border-radius: 2px;
    color: var(--c2);
    background: rgba(0,207,255,0.04);
    transition: all 0.15s;
    cursor: default;
  }

  .skill-tag:hover {
    border-color: var(--c2);
    background: rgba(0,207,255,0.1);
    color: #fff;
  }

  .skill-tag.lang { border-color: rgba(0,255,157,0.2); color: var(--c); background: rgba(0,255,157,0.04); }
  .skill-tag.lang:hover { border-color: var(--c); background: rgba(0,255,157,0.1); }

  .skill-tag.tool { border-color: rgba(255,79,216,0.2); color: var(--c3); background: rgba(255,79,216,0.04); }
  .skill-tag.tool:hover { border-color: var(--c3); background: rgba(255,79,216,0.1); }

  /* BOOKS */
  .books-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 10px;
  }

  .book-card {
    border: 1px solid var(--border);
    border-radius: 3px;
    padding: 12px;
    background: var(--bg3);
    transition: all 0.2s;
    cursor: pointer;
    text-decoration: none;
    display: block;
  }

  .book-card:hover {
    border-color: rgba(0,255,157,0.35);
    background: rgba(0,255,157,0.03);
    transform: translateY(-2px);
  }

  .book-status {
    font-size: 8px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .status-done { color: var(--c); }
  .status-ongoing { color: #f5a623; }

  .book-title {
    font-size: 12px;
    font-weight: 500;
    color: var(--txt);
    line-height: 1.4;
  }

  .book-arrow {
    font-size: 10px;
    color: var(--muted);
    margin-top: 8px;
  }

  /* INTERESTS */
  .interests-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 8px;
  }

  .interest-item {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 12px;
    color: var(--muted);
    padding: 8px 12px;
    border: 1px solid rgba(255,255,255,0.04);
    border-radius: 2px;
  }

  .interest-icon {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--c);
    flex-shrink: 0;
  }

  /* STATS */
  .stats-img {
    border: 1px solid var(--border);
    border-radius: 4px;
    width: 100%;
    filter: hue-rotate(130deg) saturate(1.2);
    display: block;
  }

  /* CONNECT */
  .connect-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    color: var(--c2);
    text-decoration: none;
    border: 1px solid rgba(0,207,255,0.2);
    padding: 8px 16px;
    border-radius: 2px;
    transition: all 0.15s;
  }

  .connect-link:hover {
    border-color: var(--c2);
    background: rgba(0,207,255,0.08);
    color: #fff;
  }

  /* TERMINAL BAR */
  .term-bar {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 0.5rem 1rem;
    background: rgba(0,0,0,0.3);
    border-bottom: 1px solid var(--border);
    font-size: 10px;
    color: var(--muted);
  }

  .term-dot { width: 8px; height: 8px; border-radius: 50%; }

  /* BLINK */
  .cursor::after {
    content: '█';
    animation: blink 1s step-end infinite;
    color: var(--c);
    font-size: 0.8em;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* TWO COL */
  .two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }
  @media(max-width: 600px) { .two-col { grid-template-columns: 1fr; } }

  .copy-btn {
    font-family: 'JetBrains Mono', monospace;
    font-size: 9px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 3px 8px;
    border-radius: 2px;
    cursor: pointer;
    margin-left: auto;
    transition: all 0.15s;
  }

  .copy-btn:hover { border-color: var(--c); color: var(--c); }
</style>

<div class="readme">
  <div class="grid-bg"></div>
  <div class="scanline"></div>

  <div class="content">

    <!-- HERO -->
    <div class="hero">
      <div class="hero-tag">sys/profile/ayush — v2026</div>
      <div class="hero-name">Ayush<span class="cursor"> </span></div>
      <div class="hero-sub">Computer Science Student &nbsp;/&nbsp; Web Enthusiast &nbsp;/&nbsp; Story Writer</div>
      <div class="hero-badges">
        <span class="badge badge-green">B.Sc. CS — Final Year</span>
        <span class="badge badge-blue">Full Stack Learner</span>
        <span class="badge badge-pink">Published Author</span>
        <span class="badge badge-green">Open to Opportunities</span>
      </div>
      <div class="hero-desc">Technology and creativity somehow ended up sharing space in my brain. I build websites, explore programming, and write stories — often at 2am when I should be sleeping.</div>
      <div class="hero-corner">AYUSH.EXE LOADED</div>
    </div>

    <!-- SKILLS -->
    <div class="section">
      <div class="term-bar">
        <div class="term-dot" style="background:#ff5f57"></div>
        <div class="term-dot" style="background:#febc2e"></div>
        <div class="term-dot" style="background:#28c840"></div>
        <span style="margin-left:6px;">skills.config</span>
        <button class="copy-btn" onclick="copyReadme()">copy raw md</button>
      </div>
      <div class="section-header">
        <div class="section-dot"></div>
        <span class="section-title">Tech Stack</span>
      </div>
      <div class="section-body">
        <div class="skill-group">
          <div class="skill-group-label">Languages</div>
          <div class="skill-tags">
            <span class="skill-tag lang">Python</span>
            <span class="skill-tag lang">SQL</span>
            <span class="skill-tag lang">HTML</span>
            <span class="skill-tag lang">CSS</span>
            <span class="skill-tag lang">JavaScript</span>
            <span class="skill-tag lang">C</span>
            <span class="skill-tag lang">C++</span>
            <span class="skill-tag lang">Java</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-label">Tools & Platforms</div>
          <div class="skill-tags">
            <span class="skill-tag">Git</span>
            <span class="skill-tag">GitHub</span>
            <span class="skill-tag">VS Code</span>
            <span class="skill-tag">Jupyter</span>
            <span class="skill-tag">AWS</span>
            <span class="skill-tag">Google Cloud</span>
            <span class="skill-tag">Pygame</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-label">Operating Systems</div>
          <div class="skill-tags">
            <span class="skill-tag tool">Linux</span>
            <span class="skill-tag tool">Windows</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-label">Soft Skills</div>
          <div class="skill-tags">
            <span class="skill-tag tool">Problem Solving</span>
            <span class="skill-tag tool">Team Collaboration</span>
            <span class="skill-tag tool">Creative Writing</span>
            <span class="skill-tag tool">Communication</span>
          </div>
        </div>
      </div>
    </div>

    <!-- BOOKS -->
    <div class="section">
      <div class="section-header">
        <div class="section-dot" style="background:var(--c3)"></div>
        <span class="section-title" style="color:var(--c3)">Published Works — Wattpad</span>
      </div>
      <div class="section-body">
        <div class="books-grid">
          <a class="book-card" href="https://www.wattpad.com/story/400993521-blue-cries" target="_blank">
            <div class="book-status status-done">● Completed</div>
            <div class="book-title">Blue Cries</div>
            <div class="book-arrow">→ read on wattpad</div>
          </a>
          <a class="book-card" href="https://www.wattpad.com/story/401443594-the-smiling-women" target="_blank">
            <div class="book-status status-ongoing">◈ Ongoing</div>
            <div class="book-title">The Smiling Women</div>
            <div class="book-arrow">→ read on wattpad</div>
          </a>
          <a class="book-card" href="https://www.wattpad.com/story/403931448-love-me-hard-hate-me-harder" target="_blank">
            <div class="book-status status-ongoing">◈ Ongoing</div>
            <div class="book-title">Love Me Hard, Hate Me Harder</div>
            <div class="book-arrow">→ read on wattpad</div>
          </a>
          <a class="book-card" href="https://www.wattpad.com/story/407216967-error-404-exit-not-found" target="_blank">
            <div class="book-status status-ongoing">◈ Ongoing</div>
            <div class="book-title">Error 404: Exit Not Found</div>
            <div class="book-arrow">→ read on wattpad</div>
          </a>
        </div>
      </div>
    </div>

    <!-- TWO COL: INTERESTS + CONNECT -->
    <div class="two-col">
      <div class="section" style="margin-bottom:0">
        <div class="section-header">
          <div class="section-dot" style="background:var(--c2)"></div>
          <span class="section-title" style="color:var(--c2)">Interests</span>
        </div>
        <div class="section-body">
          <div class="interests-list">
            <div class="interest-item"><div class="interest-icon"></div>Piano & instruments</div>
            <div class="interest-item"><div class="interest-icon"></div>Reading novels</div>
            <div class="interest-item"><div class="interest-icon"></div>Video gaming</div>
            <div class="interest-item"><div class="interest-icon"></div>Building websites</div>
            <div class="interest-item"><div class="interest-icon"></div>Writing & publishing</div>
          </div>
        </div>
      </div>

      <div class="section" style="margin-bottom:0">
        <div class="section-header">
          <div class="section-dot"></div>
          <span class="section-title">Connect</span>
        </div>
        <div class="section-body" style="display:flex;flex-direction:column;gap:10px;">
          <a class="connect-link" href="https://github.com/Ayush45965" target="_blank">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/></svg>
            github.com/Ayush45965
          </a>
          <div style="font-size:10px;color:var(--muted);letter-spacing:1px;padding:4px 0">
            // more links coming soon
          </div>
        </div>
      </div>
    </div>

    <!-- STATS -->
    <div class="section" style="margin-top:1.5rem">
      <div class="section-header">
        <div class="section-dot"></div>
        <span class="section-title">GitHub Stats</span>
      </div>
      <div class="section-body">
        <img class="stats-img"
          src="https://github-readme-stats.vercel.app/api?username=Ayush45965&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0a1520&title_color=00ff9d&icon_color=00cfff&text_color=cde8ff"
          alt="GitHub Stats"
          onerror="this.style.display='none'"
        />
      </div>
    </div>

    <!-- FOOTER -->
    <div style="text-align:center;padding:1.5rem 0 0.5rem;font-size:10px;color:var(--muted);letter-spacing:2px;">
      MADE WITH ♥ AND TOO MUCH CAFFEINE &nbsp;—&nbsp; AYUSH © 2026
    </div>

  </div>
</div>

<script>
function copyReadme() {
  const md = `<h1 align="center">Hi 👋, I'm Ayush</h1>
<h3 align="center">Computer Science Student | Web Enthusiast | Story Writer</h3>

---

🎓 **B.Sc. Computer Science – Final Year**

I enjoy building websites, exploring programming, and writing stories. Technology and creativity somehow ended up sharing space in my brain.

---

## 💻 Skills

**Languages:** Python · SQL · HTML · CSS · JavaScript · C · C++ · Java  
**Tools:** Git · GitHub · VS Code · Jupyter · AWS · Google Cloud · Pygame  
**OS:** Linux · Windows

---

## 📚 Writing on Wattpad

- **Blue Cries** *(Completed)* — https://www.wattpad.com/story/400993521-blue-cries  
- **The Smiling Women** *(Ongoing)* — https://www.wattpad.com/story/401443594-the-smiling-women  
- **Love Me Hard, Hate Me Harder** *(Ongoing)* — https://www.wattpad.com/story/403931448-love-me-hard-hate-me-harder  
- **Error 404: Exit Not Found** *(Ongoing)* — https://www.wattpad.com/story/407216967-error-404-exit-not-found  

---

## 🚀 GitHub Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=Ayush45965&show_icons=true&theme=tokyonight)

---

## 📫 Connect

- GitHub: https://github.com/Ayush45965`;

  navigator.clipboard.writeText(md).catch(()=>{});
  const btn = document.querySelector('.copy-btn');
  btn.textContent = 'copied!';
  btn.style.color = 'var(--c)';
  btn.style.borderColor = 'var(--c)';
  setTimeout(()=>{ btn.textContent='copy raw md'; btn.style.color=''; btn.style.borderColor=''; }, 2000);
}
</script>
