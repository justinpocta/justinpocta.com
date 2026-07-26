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
/* prevent double-tap zoom on mobile without disabling pinch-zoom */
html { touch-action: manipulation; }

/* ensure parent containers don't clip the card stack */
.page__content,
.initial-content {
  overflow: visible !important;
}

.hi-stack-outer {
  position: relative;
  width: clamp(400px, 48vw, 620px);
  margin-top: 2rem;
  margin-bottom: 3rem;
  margin-left: 50%;
  transform: translateX(-50%);
  padding: 0 28px;
  box-sizing: border-box;
}

.hi-stack {
  position: relative;
  width: 100%;
  aspect-ratio: 3 / 4;
  cursor: grab;
  user-select: none;
}
.hi-stack:active { cursor: grabbing; }

.hi-card {
  position: absolute;
  top: 0; left: 0;
  width: calc(100% - 20px);
  height: 100%;
  overflow-y: auto;
  overflow-x: hidden;
  scrollbar-width: thin;
  scrollbar-color: rgba(0,0,0,0.12) transparent;
  transition: transform 0.42s cubic-bezier(0.25, 0.46, 0.45, 0.94),
              opacity 0.42s ease, box-shadow 0.42s ease;
  will-change: transform, opacity;
  background: #fff;
  border-radius: 10px;
}

@media (prefers-color-scheme: dark) { .hi-card { background: #111; } }
:root[data-theme="dark"] .hi-card { background: #111; }

/* mastodon card: center content, no inner card-within-a-card */
#hi-card-0 {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#hi-card-0 .social-widget {
  flex: 0 0 auto;
  margin: 0;
}
#hi-card-0 .mastodon-card {
  display: block;
  border: none;
  border-radius: 0;
  background: transparent;
  padding: 20px 22px;
  box-sizing: border-box;
}

/* footer is now at top -- flip border to bottom, flip margin/padding */
#hi-card-0 .mastodon-footer {
  border-top: none;
  border-bottom: 1px solid rgba(0,0,0,0.1);
  margin-top: 0;
  padding-top: 0;
  margin-bottom: 14px;
  padding-bottom: 12px;
}

@media (prefers-color-scheme: dark) {
  #hi-card-0 .mastodon-footer { border-bottom-color: #444; }
  .hi-card .mastodon-date { color: #aaa; }
}
:root[data-theme="dark"] #hi-card-0 .mastodon-footer { border-bottom-color: #444; }
:root[data-theme="dark"] .hi-card .mastodon-date { color: #aaa; }

.hi-card--active {
  z-index: 3;
  transform: rotate(0deg) translate(0, 0);
  opacity: 1; pointer-events: auto;
  box-shadow: 0 10px 44px rgba(0,0,0,0.17), 0 2px 10px rgba(0,0,0,0.09);
}
.hi-card--behind-1 {
  z-index: 2;
  transform: rotate(3deg) translate(10px, 10px) scale(0.985);
  opacity: 1; pointer-events: none;
  box-shadow: 0 5px 22px rgba(0,0,0,0.11);
}
.hi-card--behind-2 {
  z-index: 1;
  transform: rotate(-2deg) translate(20px, 20px) scale(0.97);
  opacity: 0.78; pointer-events: none;
  box-shadow: 0 3px 12px rgba(0,0,0,0.08);
}
.hi-card--hidden {
  z-index: 0; opacity: 0; pointer-events: none; box-shadow: none;
}

/* arrows inside .hi-stack -- top:50% centers on the aspect-ratio-derived height */
.hi-nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 10;
  width: 36px; height: 36px; border-radius: 50%;
  border: none;
  background: rgba(255,255,255,0.92);
  box-shadow: 0 2px 10px rgba(0,0,0,0.18);
  cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  color: #222; padding: 0; line-height: 1;
  transition: background 0.18s, transform 0.18s;
}
.hi-nav-btn svg { display: block; }
.hi-nav-btn:hover { background: #fff; transform: translateY(-50%) scale(1.1); }
/* -24px mirrors the 28px outer padding minus the original 4px inset */
.hi-nav-prev { left: -24px; }
.hi-nav-next { right: -24px; }

.hi-dots-row { display: flex; justify-content: center; margin-top: 10px; }
.hi-dots { display: flex; gap: 7px; align-items: center; }
.hi-dot {
  width: 6px; height: 6px; border-radius: 50%;
  background: currentColor; opacity: 0.2;
  transition: opacity 0.25s, transform 0.25s;
}
.hi-dot--on { opacity: 0.7; transform: scale(1.25); }

.hi-card .social-widget,
.hi-card .mastodon-card,
.hi-card .flickr-card {
  max-width: 100%; margin: 0; width: 100%;
}

/* book card */
.book-card {
  width: 100%; height: 100%;
  display: flex; flex-direction: column;
  overflow: hidden;
  border-radius: 10px;
}
.book-card-header {
  flex: 0 0 auto;
  padding: 12px 14px 10px;
  border-bottom: 1px solid rgba(0,0,0,0.1);
}
.book-card-label {
  font-size: 0.72em;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #999;
  display: block;
}
.book-cover-fill {
  flex: 1; min-height: 0;
  position: relative;
  overflow: hidden;
  background: #f8cd54;
  container-type: inline-size;
}
/* CSS art: shows when real image is absent */
.book-cover-art {
  position: absolute; inset: 0;
  display: flex; flex-direction: column;
  align-items: center; justify-content: space-between;
  padding: 28px 14px 20px; box-sizing: border-box;
}
.book-cover-art-title {
  color: #0a0a0a;
  font-size: min(2.2em, 13.5cqw);
  font-weight: 900;
  font-family: Georgia, "Times New Roman", serif;
  line-height: 1; text-align: center;
}
.book-cover-art-blurb {
  color: rgba(0,0,0,0.5); font-size: 0.72em; font-style: italic;
  text-align: center; line-height: 1.4; max-width: 80%;
}
.book-cover-art-author {
  color: #0a0a0a; font-size: 1.0em; font-weight: 800;
  font-family: Georgia, "Times New Roman", serif;
  letter-spacing: 0.04em; text-align: center;
}
/* real image overlays CSS art when loaded */
.book-cover-img {
  position: absolute; inset: 0;
  width: 100%; height: 100%;
  object-fit: contain; object-position: center center;
  opacity: 0; transition: opacity 0.3s;
}
.book-cover-img.loaded { opacity: 1; }

@media (prefers-color-scheme: dark) {
  .book-card-header { border-bottom-color: rgba(255,255,255,0.1); }
  .hi-nav-btn { background: rgba(28,28,28,0.92); color: #ddd; box-shadow: 0 2px 10px rgba(0,0,0,0.5); }
  .hi-nav-btn:hover { background: rgba(45,45,45,0.95); }
}
:root[data-theme="dark"] .book-card-header { border-bottom-color: rgba(255,255,255,0.1); }
:root[data-theme="dark"] .hi-nav-btn { background: rgba(28,28,28,0.92); color: #ddd; box-shadow: 0 2px 10px rgba(0,0,0,0.5); }
:root[data-theme="dark"] .hi-nav-btn:hover { background: rgba(45,45,45,0.95); }
</style>

# Hello from Brooklyn, NY

<div class="hi-stack-outer">

  <div class="hi-stack" id="hi-stack">

    <button class="hi-nav-btn hi-nav-prev" id="hi-prev" aria-label="Previous">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"/></svg>
    </button>
    <button class="hi-nav-btn hi-nav-next" id="hi-next" aria-label="Next">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
    </button>

    <div class="hi-card" id="hi-card-0">
      {% include mastodon.html %}
    </div>

    <div class="hi-card" id="hi-card-1">
      {% include flickr.html %}
    </div>

    <div class="hi-card" id="hi-card-2">
      <div class="book-card">
        <div class="book-card-header">
          <span class="book-card-label">Currently Reading</span>
        </div>
        <div class="book-cover-fill">
          <div class="book-cover-art">
            <span class="book-cover-art-title">Martyr!</span>
            <span class="book-cover-art-blurb">"A miracle of a novel"</span>
            <span class="book-cover-art-author">Kaveh Akbar</span>
          </div>
          <img class="book-cover-img" id="book-cover-img"
               src="/assets/img/book-martyr.jpg"
               alt="Martyr! by Kaveh Akbar">
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
  /* book cover: real image fades in over CSS art when it loads */
  var bookImg = document.getElementById('book-cover-img');
  if (bookImg) {
    bookImg.addEventListener('load', function () { bookImg.classList.add('loaded'); });
  }

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

  function getActiveCard() {
    for (var i = 0; i < cards.length; i++) {
      if (cards[i].classList.contains('hi-card--active')) return cards[i];
    }
    return null;
  }

  function applyDrag(card, dx) {
    card.style.transition = 'none';
    card.style.transform = 'rotate(' + (dx / 20) + 'deg) translate(' + dx + 'px, 0)';
  }

  function snapBack(card) {
    card.style.transition = '';
    card.style.transform = '';
  }

  function flyOff(card, dx, cb) {
    card.style.transition = 'transform 0.28s ease, opacity 0.22s ease';
    card.style.transform = 'rotate(' + (dx < 0 ? -30 : 30) + 'deg) translate(' + (dx < 0 ? -120 : 120) + '%, 10px)';
    card.style.opacity = '0';
    setTimeout(function () {
      card.style.transition = 'none';
      card.style.transform = '';
      card.style.opacity = '';
      cb();
      /* re-enable transitions next frame so the new active card animates in */
      requestAnimationFrame(function () { card.style.transition = ''; });
    }, 290);
  }

  /* mouse drag */
  var dragging = false, msx = 0, msy = 0;
  stack.addEventListener('mousedown', function (e) {
    if (e.button !== 0) return;
    dragging = true;
    msx = e.clientX; msy = e.clientY;
    e.preventDefault();
  }, false);
  document.addEventListener('mousemove', function (e) {
    if (!dragging) return;
    var card = getActiveCard();
    if (card) applyDrag(card, e.clientX - msx);
  }, false);
  document.addEventListener('mouseup', function (e) {
    if (!dragging) return;
    dragging = false;
    var dx = e.clientX - msx, dy = e.clientY - msy;
    var card = getActiveCard();
    if (Math.abs(dx) > 40 && Math.abs(dx) > Math.abs(dy)) {
      var dir = dx < 0 ? 1 : -1;
      flyOff(card, dx, function () { go(dir); });
    } else {
      snapBack(card);
    }
  }, false);

  /* touch drag */
  var tsx = 0, tsy = 0, touchLocked = false;
  stack.addEventListener('touchstart', function (e) {
    tsx = e.touches[0].clientX; tsy = e.touches[0].clientY;
    touchLocked = false;
  }, { passive: true });
  stack.addEventListener('touchmove', function (e) {
    var dx = e.touches[0].clientX - tsx;
    var dy = e.touches[0].clientY - tsy;
    if (!touchLocked && Math.abs(dy) > Math.abs(dx)) return;
    touchLocked = true;
    var card = getActiveCard();
    if (card) applyDrag(card, dx);
  }, { passive: true });
  stack.addEventListener('touchend', function (e) {
    var dx = e.changedTouches[0].clientX - tsx;
    var dy = e.changedTouches[0].clientY - tsy;
    var card = getActiveCard();
    if (Math.abs(dx) > 44 && Math.abs(dx) > Math.abs(dy)) {
      var dir = dx < 0 ? 1 : -1;
      flyOff(card, dx, function () { go(dir); });
    } else {
      snapBack(card);
    }
  }, { passive: true });

  updateStack();
})();
</script>
