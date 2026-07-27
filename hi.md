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
/* prevent double-tap zoom; block horizontal scroll so swipe stays on the card */
html { touch-action: manipulation; }
body { overflow-x: hidden; }


/* dark mode page background + reverse out text on dark bg */
@media (prefers-color-scheme: dark) {
  html { background: linear-gradient(to bottom, #1a1a1a, #383838) fixed !important; }
  body { background: transparent !important; }
  html body .masthead .site-title,
  html body .masthead .site-title:visited,
  html body .masthead .greedy-nav a { color: #f0f0f0 !important; }
  .site-title::before { filter: invert(1); }
  h1, h2, h3, p { color: #e8e8e8; }
}
html[data-theme="dark"] { background: linear-gradient(to bottom, #1a1a1a, #383838) fixed !important; }
html[data-theme="dark"] body { background: transparent !important; }
html[data-theme="dark"] .masthead .site-title,
html[data-theme="dark"] .masthead .site-title:visited,
html[data-theme="dark"] .masthead .greedy-nav a { color: #f0f0f0 !important; }
html[data-theme="dark"] .site-title::before { filter: invert(1); }
html[data-theme="dark"] h1,
html[data-theme="dark"] h2,
html[data-theme="dark"] h3,
html[data-theme="dark"] p { color: #e8e8e8; }

/* ensure parent containers don't clip the card stack */
.page__content,
.initial-content {
  overflow: visible !important;
}

.hi-stack-outer {
  position: relative;
  width: min(620px, calc(100vw - 2rem));
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
  touch-action: pan-y;
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
  justify-content: flex-start;
  overflow-y: auto;
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
  padding: 20px 22px 0;
  box-sizing: border-box;
}
/* Browser pushes post text outside the <a> tag; match card padding */
#hi-card-0 .social-post-text {
  padding: 8px 22px 20px;
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
  box-shadow: 0 24px 64px rgba(0,0,0,0.38), 0 6px 20px rgba(0,0,0,0.22);
}
.hi-card--behind-1 {
  z-index: 2;
  transform: rotate(3deg) translate(10px, 10px) scale(0.985);
  opacity: 1; pointer-events: none;
  box-shadow: 0 14px 36px rgba(0,0,0,0.26);
}
.hi-card--behind-2 {
  z-index: 1;
  transform: rotate(-2deg) translate(20px, 20px) scale(0.97);
  opacity: 0.85; pointer-events: none;
  box-shadow: 0 8px 22px rgba(0,0,0,0.18);
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
  color: #555;
  display: block;
  text-align: center;
}
@media (prefers-color-scheme: dark) { .book-card-label { color: #bbb; } }
:root[data-theme="dark"] .book-card-label { color: #bbb; }
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

/* music card */
.music-card {
  width: 100%; height: 100%;
  display: flex; flex-direction: column;
  overflow: hidden;
  border-radius: 10px;
}
.music-card-header {
  flex: 0 0 auto;
  padding: 12px 14px 10px;
  border-bottom: 1px solid rgba(0,0,0,0.1);
}
.music-card-label {
  font-size: 0.72em;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #555;
  display: block;
  text-align: center;
}
.music-cover-fill {
  flex: 1; min-height: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 28px 24px;
  box-sizing: border-box;
  background: #f0ede8;
}
.music-cover-img {
  width: 100%;
  aspect-ratio: 1 / 1;
  object-fit: cover;
  border-radius: 4px;
  opacity: 0; transition: opacity 0.3s;
  box-shadow:
    0 12px 32px rgba(0,0,0,0.32),
    0 4px 12px rgba(0,0,0,0.18),
    0 1px 3px rgba(0,0,0,0.10);
}
.music-cover-img.loaded { opacity: 1; }
.music-card-footer {
  flex: 0 0 auto;
  padding: 10px 14px 14px;
  border-top: 1px solid rgba(0,0,0,0.1);
  display: flex; flex-direction: column;
  gap: 2px;
}
.music-album-name {
  font-weight: 700;
  font-size: 0.95em;
  line-height: 1.2;
}
.music-artist-name {
  font-size: 0.85em;
  color: #666;
}
.music-fav-track {
  font-size: 0.82em;
  color: #888;
  margin-top: 3px;
}
@media (prefers-color-scheme: dark) {
  .music-card-header { border-bottom-color: rgba(255,255,255,0.1); }
  .music-card-footer { border-top-color: rgba(255,255,255,0.1); }
  .music-card-label { color: #bbb; }
  .music-artist-name { color: #aaa; }
  .music-fav-track { color: #777; }
  .music-cover-fill { background: #1e1c1a; }
}
:root[data-theme="dark"] .music-card-header { border-bottom-color: rgba(255,255,255,0.1); }
:root[data-theme="dark"] .music-card-footer { border-top-color: rgba(255,255,255,0.1); }
:root[data-theme="dark"] .music-card-label { color: #bbb; }
:root[data-theme="dark"] .music-artist-name { color: #aaa; }
:root[data-theme="dark"] .music-fav-track { color: #777; }
:root[data-theme="dark"] .music-cover-fill { background: #1e1c1a; }
</style>

<h1 style="text-align: center;">Hello from Brooklyn, NY!</h1>

<p style="font-family: Georgia, serif; font-style: italic; opacity: 0.5; margin-top: -0.6em; margin-bottom: 1.5em; font-size: 1.05em; text-align: center;">A snapshot of my life outside of work</p>

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

    <div class="hi-card" id="hi-card-3">
      <div class="music-card">
        <div class="music-card-header">
          <span class="music-card-label">Currently Listening</span>
        </div>
        <div class="music-cover-fill">
          <img class="music-cover-img" id="music-cover-img" alt="Any Light by Loving">
        </div>
        <div class="music-card-footer">
          <span class="music-album-name">Any Light</span>
          <span class="music-artist-name">Loving</span>
          <span class="music-fav-track">&#9834; Medicine</span>
        </div>
      </div>
    </div>

    <div class="hi-card" id="hi-card-4">
      {% include strava.html %}
    </div>

    <div class="hi-card" id="hi-card-5">
      {% include duolingo.html %}
    </div>

  </div>

</div>

<script>
(function () {
  /* book cover: handle both cached (already complete) and fresh loads */
  var bookImg = document.getElementById('book-cover-img');
  if (bookImg) {
    if (bookImg.complete && bookImg.naturalWidth) {
      bookImg.classList.add('loaded');
    } else {
      bookImg.addEventListener('load', function () { bookImg.classList.add('loaded'); });
    }
  }

  /* music card: fetch album art from iTunes Search API */
  (function () {
    var MUSIC_ARTIST = 'Loving';
    var MUSIC_ALBUM  = 'Any Light';
    fetch('https://itunes.apple.com/search?term=' + encodeURIComponent(MUSIC_ARTIST + ' ' + MUSIC_ALBUM) + '&entity=album&limit=5')
      .then(function (res) { return res.json(); })
      .then(function (data) {
        var img = document.getElementById('music-cover-img');
        if (!img) return;
        var results = data.results || [];
        var match = null;
        for (var i = 0; i < results.length; i++) {
          if (results[i].artworkUrl100) { match = results[i]; break; }
        }
        if (!match) return;
        img.src = match.artworkUrl100.replace('100x100bb', '600x600bb');
        if (img.complete && img.naturalWidth) {
          img.classList.add('loaded');
        } else {
          img.addEventListener('load', function () { img.classList.add('loaded'); });
        }
      })
      .catch(function () {});
  })();


  var cards = Array.from(document.querySelectorAll('.hi-card'));
  var stack = document.getElementById('hi-stack');
  var total = cards.length;
  var current = Math.floor(Math.random() * total);
  var STACK_CLASSES = ['hi-card--active', 'hi-card--behind-1', 'hi-card--behind-2', 'hi-card--hidden'];

  function mod(n, m) { return ((n % m) + m) % m; }

  function updateStack() {
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

  var animating = false;

  function flyOff(card, dx, cb) {
    animating = true;
    card.style.transition = 'transform 0.28s ease, opacity 0.22s ease';
    card.style.transform = 'rotate(' + (dx < 0 ? -30 : 30) + 'deg) translate(' + (dx < 0 ? -120 : 120) + '%, 10px)';
    card.style.opacity = '0';
    setTimeout(function () {
      card.style.transition = 'none';
      card.style.transform = '';
      card.style.opacity = '';
      cb();
      requestAnimationFrame(function () { card.style.transition = ''; animating = false; });
    }, 290);
  }

  /* block link clicks that are actually the tail of a drag */
  var didDrag = false;
  stack.addEventListener('click', function (e) {
    if (didDrag) { e.preventDefault(); e.stopPropagation(); didDrag = false; }
  }, true);

  /* mouse drag */
  var dragging = false, msx = 0, msy = 0;
  stack.addEventListener('mousedown', function (e) {
    if (e.button !== 0 || animating) return;
    dragging = true; didDrag = false;
    msx = e.clientX; msy = e.clientY;
    e.preventDefault();
  }, false);
  document.addEventListener('mousemove', function (e) {
    if (!dragging) return;
    var dx = e.clientX - msx;
    if (Math.abs(dx) > 4) didDrag = true;
    var card = getActiveCard();
    if (card) applyDrag(card, dx);
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
      setTimeout(function () { didDrag = false; }, 0);
    }
  }, false);

  /* touch drag */
  var tsx = 0, tsy = 0, touchLocked = false;
  stack.addEventListener('touchstart', function (e) {
    if (animating) return;
    tsx = e.touches[0].clientX; tsy = e.touches[0].clientY;
    touchLocked = false; didDrag = false;
  }, { passive: true });
  stack.addEventListener('touchmove', function (e) {
    var dx = e.touches[0].clientX - tsx;
    var dy = e.touches[0].clientY - tsy;
    if (!touchLocked && Math.abs(dy) > Math.abs(dx)) return;
    touchLocked = true;
    if (Math.abs(dx) > 4) didDrag = true;
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
      setTimeout(function () { didDrag = false; }, 50);
    }
  }, { passive: true });

  updateStack();
})();
</script>
