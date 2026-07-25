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
  max-width: 100%;
  margin: 2rem 0 3rem;
  padding: 0 28px; /* arrow zone flanking the stack */
  box-sizing: border-box;
}

.hi-stack {
  position: relative;
  width: 100%;
  height: clamp(400px, 65vh, 560px);
  /* no overflow:hidden -- behind-card rotations must not be clipped */
}

.hi-card {
  position: absolute;
  top: 0;
  left: 0;
  width: calc(100% - 20px); /* narrower so behind-cards show at the offset */
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

/* ---- nav arrows: outside the card stack, in the outer padding zone ---- */
.hi-nav-btn {
  position: absolute;
  top: calc(clamp(200px, 32.5vh, 280px)); /* midpoint of stack height */
  transform: translateY(-50%);
  z-index: 10;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  background: rgba(255,255,255,0.92);
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

/* buttons live in .hi-stack-outer, in the padding zones flanking the stack */
.hi-nav-prev { left: 4px; }
.hi-nav-next { right: 4px; }

/* ---- dots ---- */
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

/* ---- book card: fills full hi-card height like a real book ---- */
.book-card {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  /* border-radius inherited from hi-card */
}

.book-cover-wrap {
  position: relative;
  flex: 1;
  min-height: 0;
  overflow: hidden;
  line-height: 0;
}

/* Actual image -- hidden until loaded, then replaces art */
.book-cover-img {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: none;
}
.book-cover-img.loaded { display: block; }

/* CSS art fallback: yellow/black matching the real cover */
.book-cover-art {
  width: 100%;
  height: 100%;
  background: #F5C200;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  padding: 28px 14px 20px;
  box-sizing: border-box;
}
.book-cover-art.hidden { display: none; }

.book-cover-art-title {
  color: #0a0a0a;
  /* em is card-relative (inherits 22px body), vw is capped so it never blows past the card */
  font-size: min(2.2em, 13.5cqw);
  font-weight: 900;
  font-family: Georgia, "Times New Roman", serif;
  font-style: normal;
  line-height: 1;
  text-align: center;
}
.book-cover-wrap {
  container-type: inline-size; /* enables cqw scaling */
}
.book-cover-art-blurb {
  color: rgba(0,0,0,0.5);
  font-size: 0.72em;
  font-style: italic;
  text-align: center;
  line-height: 1.4;
  max-width: 80%;
}
.book-cover-art-author {
  color: #0a0a0a;
  font-size: 1.0em;
  font-weight: 800;
  font-family: Georgia, "Times New Roman", serif;
  letter-spacing: 0.04em;
  text-align: center;
}

.book-meta {
  flex: 0 0 auto;
  padding: 12px 16px 14px;
  border-top: 1px solid rgba(0,0,0,0.1);
}
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
  .book-meta { border-top-color: rgba(255,255,255,0.1); }
  .book-author-line { color: #999; }
  .hi-nav-btn {
    background: rgba(28,28,28,0.92);
    color: #ddd;
    box-shadow: 0 2px 10px rgba(0,0,0,0.5);
  }
  .hi-nav-btn:hover { background: rgba(45,45,45,0.95); }
}
:root[data-theme="dark"] .book-meta { border-top-color: rgba(255,255,255,0.1); }
:root[data-theme="dark"] .book-author-line { color: #999; }
:root[data-theme="dark"] .hi-nav-btn {
  background: rgba(28,28,28,0.92);
  color: #ddd;
  box-shadow: 0 2px 10px rgba(0,0,0,0.5);
}
:root[data-theme="dark"] .hi-nav-btn:hover { background: rgba(45,45,45,0.95); }
</style>

# Hello from Brooklyn, NY

<div class="hi-stack-outer">

  <!-- arrows in the outer padding zone, flanking the stack -->
  <button class="hi-nav-btn hi-nav-prev" id="hi-prev" aria-label="Previous">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"/></svg>
  </button>
  <button class="hi-nav-btn hi-nav-next" id="hi-next" aria-label="Next">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
  </button>

  <div class="hi-stack" id="hi-stack">

    <div class="hi-card hi-card--vcenter" id="hi-card-0">
      {% include mastodon.html %}
    </div>

    <div class="hi-card" id="hi-card-1">
      {% include flickr.html %}
    </div>

    <!-- book card: no hi-card--vcenter, fills full height -->
    <div class="hi-card" id="hi-card-2">
      <div class="book-card">
        <div class="book-cover-wrap">
          <img class="book-cover-img" id="book-cover-img"
               src="/assets/img/book-martyr.jpg"
               alt="Martyr! by Kaveh Akbar">
          <div class="book-cover-art" id="book-cover-art">
            <span class="book-cover-art-title">Martyr!</span>
            <span class="book-cover-art-blurb">"A miracle of a novel"</span>
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

  </div>

  <div class="hi-dots-row">
    <div id="hi-dots" class="hi-dots"></div>
  </div>

</div>

<script>
(function () {
  /* book cover: show real image when it loads */
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
