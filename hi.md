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
              opacity 0.42s ease,
              box-shadow 0.42s ease;
  will-change: transform, opacity;
  background: #fff;
  border-radius: 10px;
}

@media (prefers-color-scheme: dark) { .hi-card { background: #111; } }
:root[data-theme="dark"] .hi-card { background: #111; }

.hi-card--vcenter {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.hi-card--active {
  z-index: 3;
  transform: rotate(0deg) translate(0, 0);
  opacity: 1;
  pointer-events: auto;
  box-shadow: 0 10px 44px rgba(0,0,0,0.17), 0 2px 10px rgba(0,0,0,0.09);
}

.hi-card--behind-1 {
  z-index: 2;
  transform: rotate(3deg) translate(10px, 10px) scale(0.985);
  opacity: 1;
  pointer-events: none;
  box-shadow: 0 5px 22px rgba(0,0,0,0.11);
}

.hi-card--behind-2 {
  z-index: 1;
  transform: rotate(-2deg) translate(20px, 20px) scale(0.97);
  opacity: 0.78;
  pointer-events: none;
  box-shadow: 0 3px 12px rgba(0,0,0,0.08);
}

.hi-card--hidden {
  z-index: 0;
  opacity: 0;
  pointer-events: none;
  box-shadow: none;
}

/* ---- nav arrows: overlaid on card left/right sides ---- */
.hi-nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 10;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: none;
  background: rgba(255,255,255,0.9);
  box-shadow: 0 2px 10px rgba(0,0,0,0.18);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #222;
  padding: 0;
  line-height: 1;
  transition: background 0.18s, transform 0.18s;
}
.hi-nav-btn svg { display: block; }
.hi-nav-btn:hover {
  background: #fff;
  transform: translateY(-50%) scale(1.1);
}

/* left edge of active card is at x=0; sit the prev button just inside */
.hi-nav-prev { left: 6px; }
/* active card right edge is at (stack-width - 20px); right:26px puts button just inside that edge */
.hi-nav-next { right: 26px; }

/* ---- dots (below the stack) ---- */
.hi-dots-row {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}
.hi-dots { display: flex; gap: 7px; align-items: center; }
.hi-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: currentColor;
  opacity: 0.2;
  transition: opacity 0.25s, transform 0.25s;
}
.hi-dot--on { opacity: 0.7; transform: scale(1.25); }

/* ---- include overrides inside cards ---- */
.hi-card .social-widget,
.hi-card .mastodon-card,
.hi-card .flickr-card {
  max-width: 100%;
  margin: 0;
  width: 100%;
}
.hi-card--vcenter .social-widget { width: 100%; }

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
.book-cover-wrap { position: relative; line-height: 0; }

/* Actual cover image -- hidden until it loads */
.book-cover-img {
  width: 100%;
  display: none;
}
.book-cover-img.loaded { display: block; }

/* CSS art fallback -- yellow/black matching the real cover */
.book-cover-art {
  width: 100%;
  aspect-ratio: 5/3;
  background: #F5C200;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 20px 28px;
  box-sizing: border-box;
}
.book-cover-art.hidden { display: none; }
.book-cover-art-title {
  color: #0a0a0a;
  font-size: 2.8em;
  font-weight: 900;
  font-family: Georgia, "Times New Roman", serif;
  font-style: normal;
  line-height: 1;
  text-align: center;
}
.book-cover-art-author {
  color: #1a1a1a;
  font-size: 0.85em;
  font-weight: 700;
  font-family: Georgia, "Times New Roman", serif;
  letter-spacing: 0.06em;
  text-align: center;
}

.book-meta { padding: 14px 16px 16px; }
.book-label {
  display: block;
  font-size: 0.72em;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #999;
  margin-bottom: 2px;
}
.book-title-line { font-weight: 600; font-size: 0.95em; margin: 0; }
.book-author-line { font-size: 0.85em; color: #888; margin: 1px 0 0; }

/* dark mode */
@media (prefers-color-scheme: dark) {
  .book-card { background: #111; border-color: #2e2e2e; }
  .book-author-line { color: #999; }
  .hi-nav-btn {
    background: rgba(28,28,28,0.9);
    color: #ddd;
    box-shadow: 0 2px 10px rgba(0,0,0,0.45);
  }
  .hi-nav-btn:hover { background: rgba(40,40,40,0.95); }
}
:root[data-theme="dark"] .book-card { background: #111; border-color: #2e2e2e; }
:root[data-theme="dark"] .book-author-line { color: #999; }
:root[data-theme="dark"] .hi-nav-btn {
  background: rgba(28,28,28,0.9);
  color: #ddd;
  box-shadow: 0 2px 10px rgba(0,0,0,0.45);
}
:root[data-theme="dark"] .hi-nav-btn:hover { background: rgba(40,40,40,0.95); }
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
        <div class="book-cover-wrap">
          <img class="book-cover-img" id="book-cover-img"
               src="/assets/img/book-martyr.jpg"
               alt="Martyr! by Kaveh Akbar">
          <div class="book-cover-art" id="book-cover-art">
            <span class="book-cover-art-title">Martyr!</span>
            <span class="book-cover-art-author">Kaveh Akbar</span>
          </div>
        </div>
        <div class="book-meta">
          <span class="book-label">Currently Reading</span>
          <p class="book-title-line">Martyr!</p>
          <p class="book-author-line">Kaveh Akbar</p>
        </div>
      </div>
    </div>

    <!-- nav arrows overlaid on card sides -->
    <button class="hi-nav-btn hi-nav-prev" id="hi-prev" aria-label="Previous">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"/></svg>
    </button>
    <button class="hi-nav-btn hi-nav-next" id="hi-next" aria-label="Next">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
    </button>

  </div>

  <div class="hi-dots-row">
    <div id="hi-dots" class="hi-dots"></div>
  </div>
</div>

<script>
(function () {
  /* book cover: show img when loaded, keep CSS art as fallback */
  var bookImg = document.getElementById('book-cover-img');
  var bookArt = document.getElementById('book-cover-art');
  if (bookImg && bookArt) {
    bookImg.addEventListener('load', function () {
      bookImg.classList.add('loaded');
      bookArt.classList.add('hidden');
    });
  }

  /* card stack */
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
