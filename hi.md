---
layout: default
name: Let's Connect
toc: false
title: null
permalink: /hi/
content-type: eg
hide_footer: true
---

<style>
/* ---- card stack ---- */
.hi-stack-outer {
  position: relative;
  max-width: 480px;
  margin: 2rem 0 3rem;
}

.hi-stack {
  position: relative;
  width: 100%;
  height: clamp(400px, 65vh, 560px);
  overflow: hidden;
}

/* Cards: slightly narrower than stack so behind-cards fit when offset */
.hi-card {
  position: absolute;
  top: 0;
  left: 0;
  width: calc(100% - 20px);
  height: 100%;
  overflow-y: auto;
  overflow-x: hidden;
  scrollbar-width: thin;
  scrollbar-color: rgba(0,0,0,0.12) transparent;
  transition: transform 0.42s cubic-bezier(0.25, 0.46, 0.45, 0.94),
              opacity 0.42s ease;
  will-change: transform, opacity;
}

/* Vertical centering variant (mastodon + book) */
.hi-card--vcenter {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.hi-card--active {
  z-index: 3;
  transform: translate(0, 0);
  opacity: 1;
  pointer-events: auto;
}

.hi-card--behind-1 {
  z-index: 2;
  transform: translate(10px, 10px) scale(0.985);
  opacity: 1;
  pointer-events: none;
}

.hi-card--behind-2 {
  z-index: 1;
  transform: translate(20px, 20px) scale(0.97);
  opacity: 0.65;
  pointer-events: none;
}

.hi-card--hidden {
  z-index: 0;
  opacity: 0;
  pointer-events: none;
}

/* ---- nav: compact, centered below card ---- */
.hi-nav {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  margin-top: 10px;
}

.hi-nav-btn {
  background: none;
  border: none;
  cursor: pointer;
  color: inherit;
  padding: 4px;
  line-height: 1;
  opacity: 0.4;
  transition: opacity 0.2s;
}
.hi-nav-btn:hover { opacity: 1; }
.hi-nav-btn svg { display: block; }

.hi-dots {
  display: flex;
  gap: 7px;
  align-items: center;
}
.hi-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: currentColor;
  opacity: 0.2;
  transition: opacity 0.25s, transform 0.25s;
}
.hi-dot--on {
  opacity: 0.7;
  transform: scale(1.25);
}

/* ---- includes override inside cards ---- */
.hi-card .social-widget,
.hi-card .mastodon-card,
.hi-card .flickr-card {
  max-width: 100%;
  margin: 0;
  width: 100%;
}

/* Mastodon card fills the flex column when vertically centering */
.hi-card--vcenter .social-widget {
  width: 100%;
}

/* ---- book card ---- */
.book-card {
  border: 1px solid #ddd;
  border-radius: 10px;
  overflow: hidden;
  background: #fff;
  display: block;
  text-decoration: none;
  color: inherit;
}
.book-cover-art {
  width: 100%;
  aspect-ratio: 5/3;
  background: linear-gradient(148deg, #0a0e1e 0%, #182040 55%, #1e3060 100%);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 32px;
  box-sizing: border-box;
}
.book-cover-art-title {
  color: #e8d9b0;
  font-size: 2.2em;
  font-weight: 800;
  letter-spacing: 0.03em;
  line-height: 1;
  text-align: center;
  font-style: italic;
}
.book-cover-art-author {
  color: #8a9fc0;
  font-size: 0.8em;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  text-align: center;
}
.book-meta {
  padding: 14px 16px 16px;
}
.book-label {
  display: block;
  font-size: 0.72em;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #999;
  margin-bottom: 2px;
}
.book-title-line {
  font-weight: 600;
  font-size: 0.95em;
  margin: 0;
}
.book-author-line {
  font-size: 0.85em;
  color: #888;
  margin: 1px 0 0;
}

/* dark mode */
@media (prefers-color-scheme: dark) {
  .book-card { background: #111; border-color: #2e2e2e; }
  .book-author-line { color: #999; }
}
:root[data-theme="dark"] .book-card { background: #111; border-color: #2e2e2e; }
:root[data-theme="dark"] .book-author-line { color: #999; }
</style>

# Hello from Brooklyn, NY

<div class="hi-stack-outer">
  <div class="hi-stack" id="hi-stack">

    <div class="hi-card hi-card--vcenter" id="hi-card-0">
      {% include mastodon.html %}
    </div>

    <div class="hi-card" id="hi-card-1">
      {% include flickr.html %}
    </div>

    <div class="hi-card hi-card--vcenter" id="hi-card-2">
      <div class="book-card">
        <div class="book-cover-art">
          <span class="book-cover-art-title">Martyr!</span>
          <span class="book-cover-art-author">Kaveh Akbar</span>
        </div>
        <div class="book-meta">
          <span class="book-label">Currently Reading</span>
          <p class="book-title-line">Martyr!</p>
          <p class="book-author-line">Kaveh Akbar</p>
        </div>
      </div>
    </div>

  </div>

  <nav class="hi-nav">
    <button class="hi-nav-btn" id="hi-prev" aria-label="Previous">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"/></svg>
    </button>
    <div class="hi-dots" id="hi-dots"></div>
    <button class="hi-nav-btn" id="hi-next" aria-label="Next">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
    </button>
  </nav>
</div>

<script>
(function () {
  var cards = Array.from(document.querySelectorAll('.hi-card'));
  var stack = document.getElementById('hi-stack');
  var dotsEl = document.getElementById('hi-dots');
  var total = cards.length;
  var current = 0;
  var STACK_CLASSES = ['hi-card--active', 'hi-card--behind-1', 'hi-card--behind-2', 'hi-card--hidden'];

  cards.forEach(function () {
    var d = document.createElement('span');
    d.className = 'hi-dot';
    dotsEl.appendChild(d);
  });

  function mod(n, m) { return ((n % m) + m) % m; }

  function updateStack() {
    var dots = dotsEl.querySelectorAll('.hi-dot');
    cards.forEach(function (card, i) {
      STACK_CLASSES.forEach(function (cls) { card.classList.remove(cls); });
      var dist = mod(i - current, total);
      card.classList.add(
        dist === 0 ? 'hi-card--active' :
        dist === 1 ? 'hi-card--behind-1' :
        dist === 2 ? 'hi-card--behind-2' :
                     'hi-card--hidden'
      );
      if (dist === 0) card.scrollTop = 0;
    });
    dots.forEach(function (d, i) {
      d.className = 'hi-dot' + (i === current ? ' hi-dot--on' : '');
    });
  }

  function go(dir) {
    current = mod(current + dir, total);
    updateStack();
  }

  document.getElementById('hi-prev').addEventListener('click', function () { go(-1); });
  document.getElementById('hi-next').addEventListener('click', function () { go(1); });

  var tx = 0;
  stack.addEventListener('touchstart', function (e) { tx = e.touches[0].clientX; }, { passive: true });
  stack.addEventListener('touchend', function (e) {
    var dx = e.changedTouches[0].clientX - tx;
    if (Math.abs(dx) > 44) go(dx < 0 ? 1 : -1);
  }, { passive: true });

  updateStack();
})();
</script>
