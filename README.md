<!doctype html><html><head><meta charset=utf8><meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover"><style>:root{color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}html{scroll-padding-top:env(safe-area-inset-top,0px)}body{margin:0;padding:0;font:14px -apple-system,BlinkMacSystemFont,sans-serif;background:#fff;color:#000}img{max-width:100%}[hidden]:not([hidden=until-found i]){display:none!important}</style></head><body>
<title>Okuma Defteri</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Literata:wght@500;700&display=swap">
<style>
/* Düzen: tek sütunlu defter. Üstte yıllık hedef ve 14 günlük ritim, altında sekmeli kitap listesi. Kitap kapağı, başlığın rengini taşıyan ince bir sırt gibi çalışır. */
:root {
  --bg: #F2F4F2;
  --surface: #FFFFFF;
  --ink: #18221F;
  --muted: #5D6A66;
  --line: #D9DFDC;
  --accent: #1E5B52;
  --accent-ink: #FFFFFF;
  --accent-soft: #DCEBE7;
  --warm: #A8660C;
  --danger: #B3321F;
  --spine-l: 34%;
  --spine-ink: #FFFFFF;
  --font-display: "Literata", Georgia, "Times New Roman", serif;
  --font-body: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg: #101615; --surface: #172120; --ink: #E7EEEB; --muted: #94A5A0; --line: #263230;
    --accent: #5CB5A5; --accent-ink: #0C1513; --accent-soft: #1F3A35; --warm: #E0A94B; --danger: #E57A6E;
    --spine-l: 42%; --spine-ink: #0C1513;
    color-scheme: dark;
  }
}
:root[data-theme="dark"] {
  --bg: #101615; --surface: #172120; --ink: #E7EEEB; --muted: #94A5A0; --line: #263230;
  --accent: #5CB5A5; --accent-ink: #0C1513; --accent-soft: #1F3A35; --warm: #E0A94B; --danger: #E57A6E;
  --spine-l: 42%; --spine-ink: #0C1513;
  color-scheme: dark;
}
* { box-sizing: border-box; }
body { background: var(--bg); color: var(--ink); font-family: var(--font-body); font-size: 15px; line-height: 1.5; }
.wrap {
  max-width: 760px; margin-inline: auto; padding-block: 28px 56px;
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
  display: flex; flex-direction: column; gap: 28px;
}
h1, h2, h3 { font-family: var(--font-display); margin: 0; text-wrap: balance; line-height: 1.2; }
p { margin: 0; }
button, input, select, textarea { font: inherit; color: inherit; }
button { cursor: pointer; }
:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }
.eyebrow { font-size: 12px; letter-spacing: .08em; text-transform: uppercase; color: var(--muted); font-weight: 600; }
.num { font-variant-numeric: tabular-nums; }

/* üst bölüm */
.top { display: flex; flex-direction: column; gap: 18px; }
.top h1 { font-size: clamp(30px, 7vw, 40px); font-weight: 700; }
.goal { display: flex; flex-direction: column; gap: 10px; }
.goal-row { display: flex; align-items: baseline; justify-content: space-between; gap: 12px; flex-wrap: wrap; }
.goal-big { font-family: var(--font-display); font-size: 22px; font-weight: 700; }
.goal-big small { font-family: var(--font-body); font-size: 14px; font-weight: 500; color: var(--muted); margin-left: 4px; }
.goal-edit { display: flex; align-items: center; gap: 8px; color: var(--muted); font-size: 13px; }
.goal-edit input { width: 64px; padding: 6px 8px; border: 1px solid var(--line); border-radius: 6px; background: var(--surface); text-align: center; }
.track { height: 8px; background: var(--accent-soft); border-radius: 99px; position: relative; overflow: visible; }
.track > i { display: block; height: 100%; background: var(--accent); border-radius: 99px; }
.track > b { position: absolute; top: -4px; width: 2px; height: 16px; background: var(--warm); border-radius: 1px; }
.pace { font-size: 13px; color: var(--muted); }

.stats { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 0; border-block: 1px solid var(--line); }
.stat { padding: 14px 0; display: flex; flex-direction: column; gap: 2px; min-width: 0; }
.stat + .stat { padding-left: 16px; border-left: 1px solid var(--line); }
.stat .v { font-family: var(--font-display); font-size: 24px; font-weight: 700; }
.stat .v small { font-family: var(--font-body); font-size: 13px; font-weight: 500; color: var(--muted); }
.stat .k { font-size: 12px; color: var(--muted); }

/* ritim grafiği */
.rhythm { display: flex; flex-direction: column; gap: 10px; }
.rhythm-head { display: flex; justify-content: space-between; align-items: baseline; gap: 12px; flex-wrap: wrap; }
.rhythm h2 { font-size: 17px; }
.chart { display: grid; grid-template-columns: repeat(14, minmax(0, 1fr)); gap: 4px; align-items: end; height: 124px; border-bottom: 1px solid var(--line); }
.col { display: flex; flex-direction: column; align-items: center; justify-content: flex-end; height: 100%; gap: 3px; min-width: 0; }
.col .val { font-size: 10px; color: var(--muted); line-height: 1; font-variant-numeric: tabular-nums; }
.col .bar { width: 100%; max-width: 28px; background: var(--accent-soft); border-radius: 3px 3px 0 0; min-height: 2px; }
.col.today .bar { background: var(--accent); }
.col.today .val { color: var(--ink); font-weight: 600; }
.axis { display: grid; grid-template-columns: repeat(14, minmax(0, 1fr)); gap: 4px; margin-top: 6px; }
.axis span { text-align: center; font-size: 10px; color: var(--muted); }

/* liste */
.shelf { display: flex; flex-direction: column; gap: 14px; }
.bar-tools { display: flex; justify-content: space-between; align-items: center; gap: 12px; flex-wrap: wrap; }
.tabs { display: flex; gap: 4px; flex-wrap: wrap; }
.tab { border: 1px solid transparent; background: transparent; padding: 7px 12px; border-radius: 99px; color: var(--muted); font-weight: 500; }
.tab[aria-pressed="true"] { background: var(--ink); color: var(--bg); }
.tab .n { font-variant-numeric: tabular-nums; opacity: .7; margin-left: 4px; }
.btn { border: 1px solid var(--line); background: var(--surface); padding: 8px 14px; border-radius: 8px; font-weight: 500; }
.btn:hover { border-color: var(--muted); }
.btn.primary { background: var(--accent); color: var(--accent-ink); border-color: var(--accent); }
.btn.primary:hover { filter: brightness(1.06); }
.btn.ghost { border-color: transparent; background: transparent; color: var(--muted); }
.btn.danger { color: var(--danger); border-color: var(--danger); background: transparent; }
.btn.small { padding: 6px 10px; font-size: 13px; }

.form { background: var(--surface); border: 1px solid var(--line); border-radius: 12px; padding: 16px; display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 12px; }
.form .full { grid-column: 1 / -1; }
.field { display: flex; flex-direction: column; gap: 4px; min-width: 0; }
.field label { font-size: 12px; color: var(--muted); font-weight: 500; }
.field input, .field select, .field textarea { width: 100%; padding: 9px 10px; border: 1px solid var(--line); border-radius: 8px; background: var(--bg); }
.field textarea { resize: vertical; min-height: 72px; }
.form-actions { display: flex; gap: 8px; align-items: center; flex-wrap: wrap; }
.err { color: var(--danger); font-size: 13px; }
@media (max-width: 480px) { .form { grid-template-columns: minmax(0, 1fr); } }

.list { display: flex; flex-direction: column; gap: 10px; }
.book { background: var(--surface); border: 1px solid var(--line); border-radius: 12px; padding: 14px; display: grid; grid-template-columns: 48px minmax(0, 1fr); gap: 4px 14px; }
.cover { grid-row: 1 / span 2; width: 48px; height: 68px; border-radius: 3px 6px 6px 3px; background: hsl(var(--h) 38% var(--spine-l)); color: var(--spine-ink); display: grid; place-items: center; font-family: var(--font-display); font-weight: 700; font-size: 22px; box-shadow: inset 4px 0 0 rgba(0,0,0,.18); }
.info { min-width: 0; display: flex; flex-direction: column; gap: 6px; }
.book h3 { font-size: 17px; overflow-wrap: anywhere; }
.by { color: var(--muted); font-size: 13px; overflow-wrap: anywhere; }
.tag { display: inline-block; font-size: 11px; font-weight: 600; letter-spacing: .04em; text-transform: uppercase; color: var(--warm); border: 1px solid var(--warm); border-radius: 99px; padding: 0 7px; margin-left: 6px; vertical-align: middle; }
.meta { font-size: 13px; color: var(--muted); }
.meta strong { color: var(--ink); font-weight: 600; }
.acts { grid-column: 2; display: flex; align-items: center; gap: 8px; flex-wrap: wrap; margin-top: 6px; }
.logger { display: flex; gap: 6px; align-items: center; }
.logger input { width: 76px; padding: 6px 8px; border: 1px solid var(--line); border-radius: 8px; background: var(--bg); text-align: center; }
.stars { display: inline-flex; gap: 0; }
.star { border: 0; background: transparent; padding: 2px 3px; font-size: 20px; line-height: 1; color: var(--line); }
.star.on { color: var(--warm); }
.edit { grid-column: 1 / -1; margin-top: 10px; padding-top: 14px; border-top: 1px solid var(--line); display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 12px; }
.edit .full { grid-column: 1 / -1; }
.edit-actions { display: flex; gap: 8px; justify-content: space-between; flex-wrap: wrap; align-items: center; }
@media (max-width: 480px) { .edit { grid-template-columns: minmax(0, 1fr); } }

.empty { border: 1px dashed var(--line); border-radius: 12px; padding: 28px 18px; display: flex; flex-direction: column; gap: 10px; align-items: flex-start; }
.empty h3 { font-size: 18px; }
.empty p { color: var(--muted); max-width: 52ch; }
.empty .row { display: flex; gap: 8px; flex-wrap: wrap; margin-top: 4px; }
.foot { display: flex; justify-content: space-between; gap: 12px; flex-wrap: wrap; font-size: 12px; color: var(--muted); }
.link { border: 0; background: none; color: var(--muted); text-decoration: underline; padding: 0; font-size: 12px; }
#msg { min-height: 18px; font-size: 13px; color: var(--danger); }
@media (prefers-reduced-motion: no-preference) { .track > i, .col .bar { transition: height .3s ease, width .3s ease; } }
</style>

<main class="wrap">
  <header class="top">
    <div>
      <p class="eyebrow" id="year">Okuma yılı</p>
      <h1>Okuma Defteri</h1>
    </div>
    <section class="goal" aria-label="Yıllık hedef">
      <div class="goal-row">
        <p class="goal-big num" id="goalBig">0 / 24<small>kitap</small></p>
        <label class="goal-edit" for="goalIn">Yıllık hedef <input id="goalIn" type="number" min="1" max="999" inputmode="numeric"></label>
      </div>
      <div class="track" id="goalTrack"><i style="width:0%"></i><b style="left:0%" title="Bugün olması gereken nokta"></b></div>
      <p class="pace" id="pace"></p>
    </section>
    <div class="stats" id="stats"></div>
  </header>

  <section class="rhythm" aria-label="Son 14 gün">
    <div class="rhythm-head">
      <h2>Son 14 günde okunan sayfa</h2>
      <p class="meta num" id="chartNote"></p>
    </div>
    <div class="chart" id="chart" role="img" aria-label="Son 14 günün günlük sayfa sayıları"></div>
    <div class="axis" id="axis"></div>
  </section>

  <section class="shelf">
    <div class="bar-tools">
      <div class="tabs" id="tabs" role="group" aria-label="Kitap durumu"></div>
      <button class="btn primary" id="toggleAdd" type="button" aria-expanded="false" aria-controls="addForm">Kitap ekle</button>
    </div>

    <form class="form" id="addForm" hidden novalidate>
      <div class="field full"><label for="f-title">Kitap adı</label><input id="f-title" autocomplete="off" required></div>
      <div class="field"><label for="f-author">Yazar</label><input id="f-author" autocomplete="off"></div>
      <div class="field"><label for="f-pages">Sayfa sayısı</label><input id="f-pages" type="number" min="1" max="9999" inputmode="numeric" required></div>
      <div class="field"><label for="f-status">Durum</label>
        <select id="f-status"><option value="reading">Okunuyor</option><option value="want">Okunacak</option><option value="done">Okundu</option></select></div>
      <div class="field"><label for="f-current">Şu an kaçıncı sayfadasın</label><input id="f-current" type="number" min="0" max="9999" inputmode="numeric" placeholder="0"></div>
      <div class="form-actions full">
        <button class="btn primary" type="submit">Kaydet</button>
        <button class="btn ghost" type="button" id="cancelAdd">Vazgeç</button>
        <span class="err" id="formErr" role="alert"></span>
      </div>
    </form>

    <div class="list" id="list"></div>
    <p id="msg" role="status"></p>
  </section>

  <footer class="foot">
    <span id="where"></span>
    <span id="sampleCtl"></span>
  </footer>
</main>

<script>
(function () {
  "use strict";
  var $ = function (s) { return document.querySelector(s); };
  var LS = "okuma-defteri-v1";
  var DAY = ["Paz", "Pzt", "Sal", "Çar", "Per", "Cum", "Cmt"];
  var state = { books: [], goal: 24, loaded: false, mode: "local", tab: "reading", open: null, confirmDel: null, addOpen: false };
  var col = null, drafts = {}, chains = {};

  /* ---------- yardımcılar ---------- */
  function z(n) { return String(n).padStart(2, "0"); }
  function ymd(d) { return d.getFullYear() + "-" + z(d.getMonth() + 1) + "-" + z(d.getDate()); }
  function today() { return ymd(new Date()); }
  function daysAgo(n) { var d = new Date(); d.setDate(d.getDate() - n); return ymd(d); }
  function esc(s) { return String(s == null ? "" : s).replace(/[&<>"']/g, function (c) { return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c]; }); }
  function clamp(n, a, b) { return Math.max(a, Math.min(b, n)); }
  function fmtDate(s) { try { return new Date(s + "T00:00:00").toLocaleDateString("tr-TR", { day: "numeric", month: "long" }); } catch (e) { return s; } }
  function hue(t) { var h = 0; for (var i = 0; i < t.length; i++) h = (h * 31 + t.charCodeAt(i)) % 360; return h; }
  function newId() { return "b" + Date.now().toString(36) + Math.random().toString(36).slice(2, 6); }
  function showMsg(t) { $("#msg").textContent = t || ""; }

  /* ---------- depolama ---------- */
  function lsLoad() {
    try { var r = JSON.parse(localStorage.getItem(LS) || "null"); if (r) { state.books = r.books || []; state.goal = r.goal || 24; } } catch (e) {}
  }
  function lsSave() { try { localStorage.setItem(LS, JSON.stringify({ books: state.books, goal: state.goal })); } catch (e) {} }
  function errText(e) {
    var c = e && e.code;
    if (c === "quota_exceeded") return "Depolama dolu. Kullanmadığın kitapları silip tekrar dene.";
    if (c === "invalid_argument") return "Bu defteri değiştirme iznin yok.";
    return "Kaydedilemedi. Bağlantını kontrol edip tekrar dene.";
  }
  function enqueue(key, fn) {
    chains[key] = (chains[key] || Promise.resolve()).then(fn).catch(function (e) { showMsg(errText(e)); });
    return chains[key];
  }
  function persistBook(b) {
    if (state.mode === "db" && col) {
      var data = JSON.parse(JSON.stringify(b)); delete data.id; data.kind = "book";
      return enqueue(b.id, function () { return col.doc(b.id).set(data); });
    }
    lsSave();
  }
  function persistDelete(id) {
    if (state.mode === "db" && col) return enqueue(id, function () { return col.doc(id).delete(); });
    lsSave();
  }
  function persistGoal() {
    if (state.mode === "db" && col) return enqueue("_goal", function () { return col.doc("_goal").set({ kind: "goal", value: state.goal }); });
    lsSave();
  }

  /* ---------- kitap işlemleri ---------- */
  function mutate(id, fn) {
    var i = state.books.findIndex(function (b) { return b.id === id; });
    if (i < 0) return;
    var b = JSON.parse(JSON.stringify(state.books[i]));
    fn(b);
    state.books[i] = b;
    showMsg("");
    render();
    persistBook(b);
  }
  function addLog(b, n) {
    var t = today(); b.log = b.log || [];
    var e = b.log.find(function (x) { return x.d === t; });
    if (e) e.n += n; else b.log.push({ d: t, n: n });
    if (b.log.length > 400) b.log = b.log.slice(-400);
  }
  function setPage(b, p) {
    p = clamp(Math.round(p) || 0, 0, b.pages);
    var diff = p - b.current;
    if (diff > 0) addLog(b, diff);
    b.current = p;
    if (p >= b.pages) { b.status = "done"; b.finished = b.finished || today(); b.current = b.pages; }
    else {
      if (b.status === "done") { b.status = "reading"; b.finished = null; }
      if (b.status === "want" && p > 0) { b.status = "reading"; b.started = b.started || today(); }
    }
  }
  function setStatus(b, s) {
    if (s === b.status) return;
    b.status = s;
    if (s === "reading") { b.started = b.started || today(); b.finished = null; if (b.current >= b.pages) b.current = Math.max(0, b.pages - 1); }
    if (s === "done") { b.current = b.pages; b.finished = b.finished || today(); }
    if (s === "want") { b.finished = null; }
  }
  function addBook(o) {
    var b = { id: newId(), kind: "book", title: o.title, author: o.author, pages: o.pages, current: 0, status: o.status, rating: 0, note: "", added: Date.now(), started: null, finished: null, log: [] };
    if (o.sample) b.sample = true;
    if (o.log) b.log = o.log;
    if (o.rating) b.rating = o.rating;
    if (o.note) b.note = o.note;
    if (b.status === "reading") b.started = today();
    state.books.push(b);
    if (o.current > 0) { var tmp = b; setPage(tmp, o.current); if (tmp.log.length && !o.log) tmp.log = []; }
    render();
    persistBook(b);
    return b;
  }
  function removeBook(id) {
    state.books = state.books.filter(function (b) { return b.id !== id; });
    state.open = null; state.confirmDel = null;
    render(); persistDelete(id);
  }

  /* ---------- istatistik ---------- */
  function pagesOn(date) {
    var t = 0;
    state.books.forEach(function (b) { (b.log || []).forEach(function (l) { if (l.d === date) t += l.n; }); });
    return t;
  }
  function computeStats() {
    var yr = String(new Date().getFullYear());
    var done = state.books.filter(function (b) { return b.status === "done" && b.finished && b.finished.slice(0, 4) === yr; }).length;
    var last14 = [], i;
    for (i = 13; i >= 0; i--) { var d = daysAgo(i); last14.push({ d: d, n: pagesOn(d), date: new Date(d + "T00:00:00") }); }
    var p30 = 0; for (i = 0; i < 30; i++) p30 += pagesOn(daysAgo(i));
    var sum14 = last14.reduce(function (a, x) { return a + x.n; }, 0);
    var streak = 0; i = pagesOn(today()) > 0 ? 0 : 1;
    while (i < 1000 && pagesOn(daysAgo(i)) > 0) { streak++; i++; }
    return { done: done, last14: last14, p30: p30, avg: Math.round(sum14 / 14), streak: streak, yr: yr };
  }
  function bookEstimate(b) {
    if (b.status !== "reading") return "";
    var s = 0, i, set = {};
    for (i = 0; i < 14; i++) set[daysAgo(i)] = 1;
    (b.log || []).forEach(function (l) { if (set[l.d]) s += l.n; });
    if (s <= 0) return "";
    var days = Math.ceil((b.pages - b.current) / (s / 14));
    return days <= 1 ? "bu hızla yarın biter" : "bu hızla yaklaşık " + days + " günde biter";
  }

  /* ---------- çizim ---------- */
  function renderTop(st) {
    $("#year").textContent = st.yr + " okuma yılı";
    var g = state.goal;
    $("#goalBig").innerHTML = st.done + " / " + g + "<small>kitap okundu</small>";
    var now = new Date(), start = new Date(now.getFullYear(), 0, 0);
    var doy = Math.floor((now - start) / 86400000);
    var expected = g * doy / 365;
    var diff = st.done - expected, r = Math.round(Math.abs(diff));
    var txt = r === 0 ? "Hedef tempondasın." : diff > 0 ? "Hedef tempondan yaklaşık " + r + " kitap öndesin." : "Hedef tempoya göre yaklaşık " + r + " kitap gerideysin.";
    $("#pace").textContent = txt + " Çizgi, bugün olman gereken noktayı gösterir.";
    var tr = $("#goalTrack");
    tr.firstElementChild.style.width = clamp(st.done / g * 100, 0, 100) + "%";
    tr.lastElementChild.style.left = clamp(expected / g * 100, 0, 100) + "%";
    var gi = $("#goalIn"); if (document.activeElement !== gi) gi.value = g;
    $("#stats").innerHTML =
      '<div class="stat"><span class="v num">' + st.p30 + ' <small>sayfa</small></span><span class="k">son 30 gün</span></div>' +
      '<div class="stat"><span class="v num">' + st.streak + ' <small>gün</small></span><span class="k">üst üste okuma</span></div>' +
      '<div class="stat"><span class="v num">' + st.avg + ' <small>sayfa</small></span><span class="k">günlük ortalama (14 gün)</span></div>';
    var max = Math.max.apply(null, st.last14.map(function (x) { return x.n; }).concat([0]));
    $("#chartNote").textContent = max > 0 ? "En çok " + max + " sayfa" : "Henüz kayıt yok";
    var scale = max > 0 ? 84 / max : 0;
    $("#chart").innerHTML = st.last14.map(function (x, i) {
      return '<div class="col' + (i === 13 ? " today" : "") + '"><span class="val">' + (x.n > 0 ? x.n : "") + '</span><div class="bar" style="height:' + Math.round(x.n * scale) + 'px"></div></div>';
    }).join("");
    $("#axis").innerHTML = st.last14.map(function (x) { return "<span>" + DAY[x.date.getDay()] + "</span>"; }).join("");
  }

  var TABS = [["reading", "Okunuyor"], ["want", "Okunacak"], ["done", "Okundu"], ["all", "Tümü"]];
  function filtered() {
    var arr = state.books.filter(function (b) { return state.tab === "all" || b.status === state.tab; });
    function last(b) { var l = b.log || []; return l.length ? l[l.length - 1].d : ""; }
    arr.sort(function (a, b) {
      if (state.tab === "done") return (b.finished || "").localeCompare(a.finished || "");
      if (state.tab === "reading") return last(b).localeCompare(last(a)) || b.added - a.added;
      return b.added - a.added;
    });
    return arr;
  }
  function renderTabs() {
    $("#tabs").innerHTML = TABS.map(function (t) {
      var n = state.books.filter(function (b) { return t[0] === "all" || b.status === t[0]; }).length;
      return '<button class="tab" type="button" data-act="tab" data-id="' + t[0] + '" aria-pressed="' + (state.tab === t[0]) + '">' + t[1] + '<span class="n">' + n + "</span></button>";
    }).join("");
  }
  function draft(id, fallback) { return Object.prototype.hasOwnProperty.call(drafts, id) ? drafts[id] : fallback; }
  function stars(b) {
    var s = "";
    for (var i = 1; i <= 5; i++) s += '<button class="star' + (i <= (b.rating || 0) ? " on" : "") + '" type="button" data-act="rate" data-id="' + b.id + '" data-n="' + i + '" aria-label="' + i + ' yıldız">★</button>';
    return '<span class="stars" role="group" aria-label="Puan">' + s + "</span>";
  }
  function bookHTML(b) {
    var pct = b.pages ? Math.round(b.current / b.pages * 100) : 0;
    var meta, acts = "";
    if (b.status === "reading") {
      var est = bookEstimate(b);
      meta = "Sayfa <strong class='num'>" + b.current + "</strong> / " + b.pages + " · %" + pct + (est ? " · " + est : "");
      acts = '<div class="logger"><label class="meta" for="lg-' + b.id + '">Kaldığın sayfa</label><input id="lg-' + b.id + '" data-draft="1" type="number" min="0" max="' + b.pages + '" inputmode="numeric" placeholder="sayfa" aria-label="Kaldığın sayfa" value="' + esc(draft("lg-" + b.id, b.current)) + '"><button class="btn small primary" type="button" data-act="log" data-id="' + b.id + '">Güncelle</button></div><button class="btn small" type="button" data-act="markdone" data-id="' + b.id + '">Okundu</button>';
    } else if (b.status === "want") {
      meta = b.pages + " sayfa";
      acts = '<button class="btn small primary" type="button" data-act="start" data-id="' + b.id + '">Okumaya başla</button><button class="btn small" type="button" data-act="markdone" data-id="' + b.id + '">Okundu</button>';
    } else {
      meta = b.pages + " sayfa" + (b.finished ? " · " + fmtDate(b.finished) + " tarihinde okundu" : "");
      acts = stars(b);
    }
    var bar = b.status === "reading" ? '<div class="track" aria-hidden="true"><i style="width:' + pct + '%"></i></div>' : "";
    var open = state.open === b.id;
    var edit = "";
    if (open) {
      edit = '<div class="edit">' +
        '<div class="field"><label for="st-' + b.id + '">Durum</label><select id="st-' + b.id + '" data-field="status" data-id="' + b.id + '">' +
        [["want", "Okunacak"], ["reading", "Okunuyor"], ["done", "Okundu"]].map(function (o) { return '<option value="' + o[0] + '"' + (o[0] === b.status ? " selected" : "") + ">" + o[1] + "</option>"; }).join("") + "</select></div>" +
        '<div class="field"><label for="pg-' + b.id + '">Kaldığın sayfa</label><input id="pg-' + b.id + '" data-field="page" data-draft="1" data-id="' + b.id + '" type="number" min="0" max="' + b.pages + '" inputmode="numeric" value="' + esc(draft("pg-" + b.id, b.current)) + '"></div>' +
        '<div class="field full"><label for="nt-' + b.id + '">Not</label><textarea id="nt-' + b.id + '" data-field="note" data-draft="1" data-id="' + b.id + '" placeholder="Beğendiğin bir bölüm, bir alıntının sayfası, kısa bir yorum">' + esc(draft("nt-" + b.id, b.note || "")) + "</textarea></div>" +
        (b.status === "done" ? '<div class="field full"><label>Puan</label>' + stars(b) + "</div>" : "") +
        '<div class="edit-actions full"><button class="btn small ghost" type="button" data-act="edit" data-id="' + b.id + '">Kapat</button>' +
        (state.confirmDel === b.id
          ? '<span><button class="btn small danger" type="button" data-act="del" data-id="' + b.id + '">Evet, sil</button> <button class="btn small ghost" type="button" data-act="nodel" data-id="' + b.id + '">Vazgeç</button></span>'
          : '<button class="btn small danger" type="button" data-act="askdel" data-id="' + b.id + '">Sil</button>') + "</div></div>";
    }
    var init = (b.title.trim().charAt(0) || "?").toLocaleUpperCase("tr-TR");
    return '<article class="book" style="--h:' + hue(b.title) + '"><div class="cover" aria-hidden="true">' + esc(init) + "</div>" +
      '<div class="info"><h3>' + esc(b.title) + (b.sample ? '<span class="tag">örnek</span>' : "") + "</h3>" +
      (b.author ? '<p class="by">' + esc(b.author) + "</p>" : "") + bar + '<p class="meta num">' + meta + "</p>" +
      (b.note && !open ? '<p class="meta">“' + esc(b.note.length > 140 ? b.note.slice(0, 140) + "…" : b.note) + "”</p>" : "") + "</div>" +
      '<div class="acts">' + acts + '<button class="btn small ghost" type="button" data-act="edit" data-id="' + b.id + '" aria-expanded="' + open + '">' + (open ? "Ayrıntıyı kapat" : "Ayrıntı") + "</button></div>" + edit + "</article>";
  }
  var EMPTY = {
    reading: ["Şu an okuduğun kitap yok", "Okumaya başladığın bir kitap ekle, her gün kaç sayfa okuduğunu buradan işle."],
    want: ["Okunacak listen boş", "Sırada bekleyen kitapları ekle, sırası gelince tek dokunuşla okumaya başla."],
    done: ["Henüz okuduğun kitap yok", "Bir kitabı okundu olarak işaretlediğinde ya da son sayfasına ulaştığında burada görünür ve yıllık hedefe sayılır."],
    all: ["Henüz kitap yok", "İlk kitabını ekleyerek başla. Sayfa sayısını girince ilerlemeni, günlük ritmini ve bitiş tahminini görürsün."]
  };
  function renderList() {
    var el = $("#list");
    if (!state.loaded) { el.innerHTML = '<p class="meta">Defterin yükleniyor…</p>'; return; }
    var arr = filtered();
    if (!arr.length) {
      var e = EMPTY[state.tab];
      el.innerHTML = '<div class="empty"><h3>' + e[0] + "</h3><p>" + e[1] + '</p><div class="row"><button class="btn primary" type="button" data-act="addopen">Kitap ekle</button>' +
        (state.books.length === 0 ? '<button class="btn" type="button" data-act="sample">Örnek verilerle dene</button>' : "") + "</div></div>";
      return;
    }
    el.innerHTML = arr.map(bookHTML).join("");
  }
  function renderFoot() {
    $("#where").textContent = state.mode === "db" ? "Kayıtların hesabına bağlı ve yalnızca sana görünür." : "Kayıtlar bu tarayıcıda saklanıyor. Başka cihazda görünmez.";
    var has = state.books.some(function (b) { return b.sample; });
    $("#sampleCtl").innerHTML = has ? '<button class="link" type="button" data-act="clearsample">Örnek kitapları sil</button>' : "";
  }
  function render() {
    var ae = document.activeElement, key = ae && ae.id, ss = null, se = null;
    if (ae && ae.selectionStart != null) { try { ss = ae.selectionStart; se = ae.selectionEnd; } catch (e) {} }
    renderTop(computeStats());
    renderTabs(); renderList(); renderFoot();
    if (key && key !== "goalIn") {
      var n = document.getElementById(key);
      if (n && n !== document.activeElement) { n.focus(); if (ss != null) { try { n.setSelectionRange(ss, se); } catch (e) {} } }
    }
  }

  /* ---------- olaylar ---------- */
  function intVal(v) { var n = parseInt(v, 10); return isNaN(n) ? 0 : n; }
  function act(a, id, t) {
    if (a === "tab") { state.tab = id; state.open = null; render(); }
    else if (a === "addopen") { setAdd(true); }
    else if (a === "sample") { addSamples(); }
    else if (a === "clearsample") { state.books.filter(function (b) { return b.sample; }).forEach(function (b) { removeBook(b.id); }); }
    else if (a === "start") { mutate(id, function (b) { setStatus(b, "reading"); }); state.tab = "reading"; render(); }
    else if (a === "markdone") { mutate(id, function (b) { setStatus(b, "done"); }); }
    else if (a === "log") {
      var inp = document.getElementById("lg-" + id), n = intVal(inp && inp.value), empty = !inp || inp.value.trim() === "";
      if (empty || n < 0) { showMsg("Kaldığın sayfayı yaz."); if (inp) inp.focus(); return; }
      delete drafts["lg-" + id];
      mutate(id, function (b) { setPage(b, n); });
    }
    else if (a === "edit") { state.open = state.open === id ? null : id; state.confirmDel = null; render(); }
    else if (a === "rate") { var r = intVal(t.dataset.n); mutate(id, function (b) { b.rating = b.rating === r ? 0 : r; }); }
    else if (a === "askdel") { state.confirmDel = id; render(); }
    else if (a === "nodel") { state.confirmDel = null; render(); }
    else if (a === "del") { removeBook(id); }
  }
  $("#list").addEventListener("click", function (e) {
    var t = e.target.closest("[data-act]"); if (t) act(t.dataset.act, t.dataset.id, t);
  });
  $("#tabs").addEventListener("click", function (e) {
    var t = e.target.closest("[data-act]"); if (t) act(t.dataset.act, t.dataset.id, t);
  });
  $("#list").addEventListener("input", function (e) {
    var t = e.target; if (t.dataset && t.dataset.draft) drafts[t.id] = t.value;
  });
  $("#list").addEventListener("keydown", function (e) {
    if (e.key === "Enter" && e.target.id && e.target.id.indexOf("lg-") === 0) { e.preventDefault(); act("log", e.target.id.slice(3)); }
  });
  $("#list").addEventListener("change", function (e) {
    var t = e.target, f = t.dataset && t.dataset.field, id = t.dataset && t.dataset.id;
    if (!f) return;
    delete drafts[t.id];
    if (f === "status") mutate(id, function (b) { setStatus(b, t.value); });
    if (f === "page") mutate(id, function (b) { setPage(b, intVal(t.value)); });
    if (f === "note") mutate(id, function (b) { b.note = t.value.trim().slice(0, 2000); });
  });
  $("#goalIn").addEventListener("change", function (e) {
    var v = clamp(intVal(e.target.value), 1, 999) || 24;
    state.goal = v; e.target.value = v; render(); persistGoal();
  });

  function setAdd(open) {
    state.addOpen = open;
    $("#addForm").hidden = !open;
    $("#toggleAdd").setAttribute("aria-expanded", String(open));
    if (open) { $("#f-title").focus(); $("#addForm").scrollIntoView({ block: "nearest" }); }
  }
  $("#toggleAdd").addEventListener("click", function () { setAdd(!state.addOpen); });
  $("#cancelAdd").addEventListener("click", function () { $("#addForm").reset(); $("#formErr").textContent = ""; setAdd(false); });
  $("#addForm").addEventListener("submit", function (e) {
    e.preventDefault();
    var title = $("#f-title").value.trim(), pages = intVal($("#f-pages").value), cur = intVal($("#f-current").value), err = $("#formErr");
    if (!title) { err.textContent = "Kitabın adını yaz."; $("#f-title").focus(); return; }
    if (pages < 1) { err.textContent = "Sayfa sayısı en az 1 olmalı."; $("#f-pages").focus(); return; }
    var status = $("#f-status").value;
    if (cur > 0 && status === "want") status = "reading";
    if (status === "done") cur = pages;
    err.textContent = "";
    addBook({ title: title.slice(0, 200), author: $("#f-author").value.trim().slice(0, 120), pages: pages, status: status, current: Math.min(cur, pages) });
    state.tab = status === "want" ? "want" : status === "done" ? "done" : "reading";
    $("#addForm").reset(); setAdd(false); render();
  });

  function addSamples() {
    function mk(pattern) { var out = []; pattern.forEach(function (n, i) { if (n > 0) out.push({ d: daysAgo(pattern.length - 1 - i), n: n }); }); return out; }
    var a = addBook({ title: "Tutunamayanlar", author: "Oğuz Atay", pages: 724, status: "reading", sample: true, log: mk([0, 0, 0, 0, 0, 0, 0, 0, 18, 25, 0, 30, 22, 28]) });
    mutate(a.id, function (b) { b.current = 143; });
    var c = addBook({ title: "Küçük Prens", author: "Antoine de Saint-Exupéry", pages: 96, status: "done", sample: true, rating: 5, log: mk([0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]) });
    mutate(c.id, function (b) { b.current = b.pages; b.finished = daysAgo(12); b.note = "Bir oturuşta bitti, tekrar okunacak."; });
    addBook({ title: "Dune", author: "Frank Herbert", pages: 612, status: "want", sample: true });
    state.tab = "reading"; render();
  }

  /* ---------- başlangıç ---------- */
  function startLocal() { state.mode = "local"; lsLoad(); state.loaded = true; render(); }
  async function init() {
    render();
    var db = null, user = null;
    try {
      if (window.claude && window.claude.use) {
        var r = await Promise.all([window.claude.use("db"), window.claude.use("user")]);
        db = r[0]; user = r[1];
      }
    } catch (e) {}
    var uid = null;
    try { uid = user ? await user.id() : null; } catch (e) {}
    if (!db || !uid) { startLocal(); return; }
    state.mode = "db";
    col = db.collection("data/users/" + uid);
    var timer = setTimeout(function () { if (!state.loaded) showMsg("Defterine şu an ulaşılamıyor. Bağlantı gelince otomatik yüklenecek."); }, 10000);
    try {
      col.onSnapshot(function (snap) {
        var books = [];
        snap.docs.forEach(function (d) {
          var v = d.data() || {};
          if (v.kind === "goal") { if (typeof v.value === "number" && v.value > 0) state.goal = v.value; }
          else if (v.kind === "book") { var o = JSON.parse(JSON.stringify(v)); o.id = d.id; books.push(o); }
        });
        state.books = books;
        if (!snap.metadata.fromCache) { clearTimeout(timer); showMsg(""); }
        state.loaded = true;
        render();
      }, function () { clearTimeout(timer); startLocal(); });
    } catch (e) { clearTimeout(timer); startLocal(); }
  }
  init();
})();
</script>

</body></html>
