<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GIRS Internacional — Experiencias Innovadoras · ONU-Hábitat</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --ink:#0D1117;--muted:#6B7280;--muted2:#9CA3AF;
  --paper:#F8F6F1;--white:#FFFFFF;
  --az:#1A3A5C;--az2:#2E75B6;--az3:#DBEAFE;
  --ve:#0F5132;--ve2:#DCFCE7;
  --na:#C55A11;--na2:#FEF3C7;
  --ro:#991B1B;--ro2:#FEE2E2;
  --am:#92400E;--am2:#FEF9C3;
  --gold:#D4A017;--accent:#E63946;
  --r:.75rem;--r2:1.25rem;
  --sh:0 2px 12px rgba(0,0,0,.08);--sh2:0 8px 40px rgba(0,0,0,.14)
}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;background:var(--paper);color:var(--ink);line-height:1.65;overflow-x:hidden}
::-webkit-scrollbar{width:6px}
::-webkit-scrollbar-track{background:var(--paper)}
::-webkit-scrollbar-thumb{background:var(--az2);border-radius:3px}

/* HERO */
.hero{min-height:100vh;background:var(--ink);position:relative;display:flex;flex-direction:column;justify-content:center;padding:6rem 4vw 4rem;overflow:hidden}

/* ══════════════════════════════════════════════════════════════════════════
   FOTO DE FONDO DEL HERO
   ══════════════════════════════════════════════════════════════════════════
   Para poner tu foto de fondo:
   1. Guarda tu imagen como  hero-bg.jpg  en la misma carpeta que index.html
      (también acepta .png o .webp — solo cambia el nombre en el CSS de abajo)
   2. La foto aparece automáticamente con el overlay oscuro que protege el texto
   3. Si quieres más transparencia (ver más la foto), baja los números del overlay:
        .90 → .65  para ver bastante la foto
        .75 → .50  para verla mucho
   ══════════════════════════════════════════════════════════════════════════ */
.hero-bg-photo{
  position:absolute;inset:0;z-index:0;
  background-image:url('hero-bg.jpg'); /* ← CAMBIA ESTE NOMBRE SI TU FOTO TIENE OTRO */
  background-size:cover;
  background-position:center top;
  opacity:0;
  transition:opacity 1s ease
}
.hero-bg-photo.loaded{opacity:1}
/* Overlay oscuro — el gradiente protege la legibilidad del texto blanco */
.hero-bg-overlay{
  position:absolute;inset:0;z-index:1;
  background:linear-gradient(
    135deg,
    rgba(13,17,23,.90) 0%,
    rgba(13,17,23,.78) 50%,
    rgba(13,17,23,.62) 100%
  )
}
/* Todo el contenido del hero va por encima de la foto y el overlay */
.hero>*:not(.hero-bg-photo):not(.hero-bg-overlay){position:relative;z-index:2}

.hero-grid{position:absolute;inset:0;z-index:0;background-image:linear-gradient(rgba(46,117,182,.05) 1px,transparent 1px),linear-gradient(90deg,rgba(46,117,182,.05) 1px,transparent 1px);background-size:60px 60px}
.hero-accent{position:absolute;top:-120px;right:-120px;width:600px;height:600px;border-radius:50%;background:radial-gradient(circle,rgba(46,117,182,.15) 0%,transparent 70%);pointer-events:none}
.hero-badge{display:inline-flex;align-items:center;gap:.5rem;background:rgba(46,117,182,.2);border:1px solid rgba(46,117,182,.4);color:#93C5FD;font-size:.75rem;font-weight:600;letter-spacing:.1em;padding:.35rem .9rem;border-radius:100px;margin-bottom:2rem;text-transform:uppercase;width:fit-content}
.hero h1{font-family:'Playfair Display',serif;font-size:clamp(2.8rem,6vw,5.5rem);font-weight:900;color:var(--white);line-height:1.05;max-width:900px;margin-bottom:1.5rem}
.hero h1 em{color:var(--gold);font-style:italic}
.hero-sub{color:#9CA3AF;font-size:1.1rem;max-width:560px;margin-bottom:2.5rem;line-height:1.7}
.hero-stats{display:flex;gap:2.5rem;flex-wrap:wrap;margin-bottom:3rem}
.hero-stat-num{font-family:'Playfair Display',serif;font-size:2.8rem;font-weight:700;color:var(--gold);display:block;line-height:1}
.hero-stat-label{font-size:.8rem;color:#6B7280;margin-top:.25rem;letter-spacing:.06em}
.hero-ctas{display:flex;gap:1rem;flex-wrap:wrap}
.btn{display:inline-flex;align-items:center;gap:.5rem;padding:.8rem 1.8rem;border-radius:100px;font-size:.9rem;font-weight:600;cursor:pointer;text-decoration:none;transition:all .2s;border:none}
.btn-primary{background:var(--az2);color:var(--white)}
.btn-primary:hover{background:#1E5FA0;transform:translateY(-1px);box-shadow:0 6px 20px rgba(46,117,182,.4)}
.btn-ghost{background:transparent;color:#9CA3AF;border:1px solid #374151}
.btn-ghost:hover{border-color:var(--az2);color:var(--az2)}

/* NAV */
nav{position:sticky;top:0;z-index:200;background:rgba(13,17,23,.95);backdrop-filter:blur(12px);border-bottom:1px solid #1F2937;display:flex;align-items:center;justify-content:space-between;padding:.9rem 4vw;gap:1rem}
.nav-logo{font-family:'Playfair Display',serif;font-size:1.1rem;color:var(--white);font-weight:700}
.nav-logo span{color:var(--gold)}
.nav-links{display:flex;gap:.25rem}
.nav-link{color:#6B7280;font-size:.82rem;font-weight:500;padding:.4rem .85rem;border-radius:100px;cursor:pointer;transition:all .2s;text-decoration:none;white-space:nowrap}
.nav-link:hover,.nav-link.active{background:rgba(46,117,182,.2);color:#93C5FD}

/* SECTIONS */
section{padding:5rem 4vw}
.section-eyebrow{font-size:.72rem;font-weight:700;letter-spacing:.15em;text-transform:uppercase;color:var(--az2);margin-bottom:.6rem}
.section-title{font-family:'Playfair Display',serif;font-size:clamp(1.8rem,3.5vw,2.8rem);font-weight:700;color:var(--ink);line-height:1.15}
.section-title em{color:var(--az2);font-style:italic}
.section-desc{color:var(--muted);max-width:560px;margin-top:.75rem;font-size:.95rem}
.section-header{margin-bottom:3rem}

/* MAP */
#map-section{background:var(--ink);padding:5rem 0 0}
#map-section .section-eyebrow{color:#93C5FD}
#map-section .section-title{color:var(--white)}
#map-section .section-desc{color:#9CA3AF}
.map-header{padding:0 4vw 2rem}
.map-container{width:100%;height:520px;position:relative;background:#0D1117}
.world-map-svg{width:100%;height:100%;display:block}
.map-pin{cursor:pointer;transition:transform .2s;transform-origin:center}
.map-pin:hover{transform:scale(1.3)}
.map-pin circle.outer{fill:rgba(46,117,182,.25);animation:pp 2.5s ease-in-out infinite}
.map-pin.tb circle.outer{fill:rgba(15,81,50,.3);animation:ppg 2.5s ease-in-out infinite}
@keyframes pp{0%,100%{r:18;opacity:.6}50%{r:26;opacity:.2}}
@keyframes ppg{0%,100%{r:18;opacity:.6}50%{r:26;opacity:.2}}
.map-tooltip{position:absolute;background:var(--white);border-radius:var(--r2);padding:1rem 1.25rem;box-shadow:var(--sh2);min-width:200px;pointer-events:none;opacity:0;transition:opacity .2s;z-index:50}
.map-tooltip.visible{opacity:1}
.mt-num{font-family:'DM Mono',monospace;font-size:.7rem;color:var(--az2);font-weight:500}
.mt-name{font-weight:700;font-size:.9rem;color:var(--ink);margin:.15rem 0}
.mt-country{font-size:.78rem;color:var(--muted)}
.map-legend{display:flex;gap:1.5rem;padding:1.25rem 4vw;background:#111827;border-top:1px solid #1F2937;flex-wrap:wrap}
.ml-item{display:flex;align-items:center;gap:.5rem}
.ml-dot{width:10px;height:10px;border-radius:50%}
.ml-label{font-size:.78rem;color:#9CA3AF}

/* INDEX */
#index-section{background:var(--white)}
.filter-btn{padding:.45rem 1.1rem;border-radius:100px;border:1.5px solid #E5E7EB;background:var(--white);color:var(--muted);font-size:.82rem;font-weight:600;cursor:pointer;transition:all .18s}
.filter-btn:hover{border-color:var(--az2);color:var(--az2)}
.filter-btn.active{background:var(--az2);border-color:var(--az2);color:var(--white)}
.index-controls{display:flex;gap:.75rem;margin-bottom:2rem;flex-wrap:wrap}
.index-table-wrap{overflow-x:auto;border-radius:var(--r2);box-shadow:var(--sh)}
table{width:100%;border-collapse:collapse}
thead tr{background:var(--ink)}
thead th{padding:.9rem 1rem;text-align:left;font-size:.72rem;font-weight:700;letter-spacing:.08em;color:#9CA3AF;text-transform:uppercase;white-space:nowrap}
thead th:first-child{border-radius:var(--r2) 0 0 0}
thead th:last-child{border-radius:0 var(--r2) 0 0}
tbody tr{border-bottom:1px solid #F3F4F6;transition:background .15s;cursor:pointer}
tbody tr:hover{background:var(--az3)}
tbody tr:last-child{border-bottom:none}
td{padding:.8rem 1rem;font-size:.88rem;vertical-align:middle}
.td-num{font-family:'DM Mono',monospace;font-size:.72rem;color:var(--az2);font-weight:600}
.td-name{font-weight:700;color:var(--ink)}
.td-c{color:var(--muted);font-size:.8rem}
.dim-score{display:inline-flex;align-items:center;justify-content:center;width:28px;height:28px;border-radius:6px;font-family:'DM Mono',monospace;font-size:.82rem;font-weight:700}
.ds-h{background:var(--ve2);color:var(--ve)}
.ds-m{background:var(--am2);color:var(--am)}
.ds-l{background:var(--ro2);color:var(--ro)}
.total-b{font-family:'Playfair Display',serif;font-size:1.2rem;font-weight:900}
.niv{padding:.3rem .8rem;border-radius:100px;font-size:.72rem;font-weight:700;letter-spacing:.06em;text-transform:uppercase;white-space:nowrap}
.niv-a{background:var(--ve2);color:var(--ve)}
.niv-m{background:var(--na2);color:var(--na)}
.dim-legend{display:flex;gap:.75rem;margin-bottom:1.5rem;flex-wrap:wrap}
.dim-chip{padding:.3rem .75rem;border-radius:100px;font-size:.72rem;font-weight:600}

/* FICHAS */
#fichas-section{background:var(--paper)}
.fichas-filters{display:flex;gap:.5rem;margin-bottom:2.5rem;flex-wrap:wrap}
.fichas-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(340px,1fr));gap:1.75rem}
.ficha-card{background:var(--white);border-radius:var(--r2);box-shadow:var(--sh);overflow:hidden;cursor:pointer;transition:all .25s;display:flex;flex-direction:column}
.ficha-card:hover{transform:translateY(-4px);box-shadow:var(--sh2)}
.ficha-card.hidden{display:none}
.fc-stripe{height:6px;width:100%}
.fc-header{padding:1.25rem 1.5rem .75rem;display:flex;align-items:flex-start;justify-content:space-between;gap:1rem}
.fc-num-wrap{display:flex;align-items:center;gap:.75rem}
.fc-num{font-family:'DM Mono',monospace;font-size:.65rem;font-weight:700;color:var(--muted);letter-spacing:.1em}
.fc-tema{font-size:.68rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;padding:.22rem .65rem;border-radius:100px;white-space:nowrap}
.ta{background:var(--az3);color:var(--az)}
.tb2{background:var(--ve2);color:var(--ve)}
.fc-title{font-family:'Playfair Display',serif;font-size:1.15rem;font-weight:700;color:var(--ink);padding:0 1.5rem;line-height:1.25;margin-bottom:.3rem}
.fc-loc{padding:0 1.5rem;font-size:.8rem;color:var(--muted);margin-bottom:.9rem;display:flex;align-items:center;gap:.35rem}

/* ══════════════════════════════════════════════════════════════════════════
   FOTO EN TARJETA DE FICHA
   ══════════════════════════════════════════════════════════════════════════
   Aparece entre la ubicación y el resumen.
   Si la foto no existe o no carga, la sección se oculta sola.
   ══════════════════════════════════════════════════════════════════════════ */
.fc-photo-wrap{width:100%;height:180px;overflow:hidden;background:#F3F4F6;position:relative}
.fc-photo{width:100%;height:100%;object-fit:cover;display:block;transition:transform .4s}
.ficha-card:hover .fc-photo{transform:scale(1.04)}
.fc-photo-wrap::after{content:'';position:absolute;bottom:0;left:0;right:0;height:50px;background:linear-gradient(transparent,rgba(255,255,255,.55));pointer-events:none}

.fc-desc{padding:0 1.5rem;font-size:.85rem;color:#4B5563;line-height:1.6;flex:1;margin-bottom:1rem}
.fc-scores{padding:.9rem 1.5rem;background:var(--paper);border-top:1px solid #F3F4F6}
.fc-score-row{display:flex;align-items:center;justify-content:space-between;margin-bottom:.45rem}
.fc-score-label{font-size:.72rem;color:var(--muted);font-weight:500}
.fc-score-bar-wrap{flex:1;height:6px;background:#E5E7EB;border-radius:3px;margin:0 .75rem;overflow:hidden}
.fc-score-bar{height:100%;border-radius:3px;transition:width .6s ease}
.fc-score-val{font-family:'DM Mono',monospace;font-size:.72rem;font-weight:700}
.fc-footer{padding:1rem 1.5rem;display:flex;align-items:center;justify-content:space-between;border-top:1px solid #F3F4F6}
.fc-total{font-family:'Playfair Display',serif;font-size:1.5rem;font-weight:900}
.fc-btn{background:none;border:none;color:var(--az2);font-size:.82rem;font-weight:600;cursor:pointer}

/* MODAL */
.modal-overlay{position:fixed;inset:0;z-index:1000;background:rgba(0,0,0,.7);backdrop-filter:blur(4px);display:flex;align-items:center;justify-content:center;padding:1.5rem;opacity:0;pointer-events:none;transition:opacity .25s}
.modal-overlay.open{opacity:1;pointer-events:all}
.modal{background:var(--white);border-radius:var(--r2);width:100%;max-width:800px;max-height:90vh;overflow-y:auto;position:relative;transform:translateY(20px);transition:transform .3s;box-shadow:0 24px 80px rgba(0,0,0,.3)}
.modal-overlay.open .modal{transform:translateY(0)}
.modal-stripe{height:8px;width:100%;border-radius:var(--r2) var(--r2) 0 0}
.modal-header{padding:2rem 2rem 1rem}
.modal-close{position:absolute;top:1.25rem;right:1.25rem;width:36px;height:36px;border-radius:50%;background:#F3F4F6;border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:1rem;color:var(--muted);transition:all .15s}
.modal-close:hover{background:var(--accent);color:var(--white)}
.modal-num{font-family:'DM Mono',monospace;font-size:.7rem;color:var(--az2);font-weight:600}
.modal-title{font-family:'Playfair Display',serif;font-size:1.7rem;font-weight:700;color:var(--ink);line-height:1.2;margin:.4rem 0 .5rem}
.modal-meta{display:flex;gap:.75rem;flex-wrap:wrap;align-items:center}
.modal-body{padding:0 2rem 2rem}
.modal-st{font-size:.7rem;font-weight:800;letter-spacing:.14em;text-transform:uppercase;color:var(--az2);margin:1.5rem 0 .6rem;display:flex;align-items:center;gap:.5rem}
.modal-st::after{content:'';flex:1;height:1px;background:var(--az3)}
.modal-text{font-size:.9rem;color:#374151;line-height:1.7}
.modal-tags{display:flex;gap:.5rem;flex-wrap:wrap;margin-top:.75rem}
.modal-sg{display:grid;grid-template-columns:1fr 1fr;gap:.75rem;margin-top:.75rem}
.msi{background:var(--paper);border-radius:var(--r);padding:.75rem}
.msi-l{font-size:.72rem;color:var(--muted);margin-bottom:.35rem;font-weight:500}
.msi-bw{height:8px;background:#E5E7EB;border-radius:4px;overflow:hidden;margin-bottom:.3rem}
.msi-b{height:100%;border-radius:4px}
.msi-v{font-family:'DM Mono',monospace;font-size:.85rem;font-weight:700}
.modal-tr{display:flex;align-items:center;justify-content:space-between;background:var(--ink);border-radius:var(--r2);padding:1.25rem 1.5rem;margin-top:1rem}
.mtr-l{font-size:.75rem;color:#9CA3AF;font-weight:600;letter-spacing:.06em;text-transform:uppercase}
.mtr-t{font-family:'Playfair Display',serif;font-size:2.4rem;font-weight:900}
.ods-tag{padding:.28rem .65rem;border-radius:6px;font-size:.7rem;font-weight:700;color:var(--white)}
.lecneg{background:var(--ro2);border:1px solid #FCA5A5;border-radius:var(--r);padding:.75rem 1rem;margin:.75rem 0;font-size:.85rem;color:var(--ro);display:flex;gap:.5rem}
.radar-wrap{display:flex;justify-content:center;margin:2rem 0}
.radar-svg{max-width:340px;width:100%}

/* ══════════════════════════════════════════════════════════════════════════
   GALERÍA DE FOTOS EN EL MODAL
   ══════════════════════════════════════════════════════════════════════════
   Aparece al hacer clic en una tarjeta. Muestra todas las fotos del array.
   Haz clic en una foto para ampliarla (lightbox).
   ══════════════════════════════════════════════════════════════════════════ */
.modal-gallery{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:.75rem;margin:.75rem 0}
.modal-gallery img{width:100%;height:160px;object-fit:cover;border-radius:8px;display:block;cursor:zoom-in;transition:transform .2s,box-shadow .2s}
.modal-gallery img:hover{transform:scale(1.03);box-shadow:0 8px 24px rgba(0,0,0,.18)}

/* ══════════════════════════════════════════════════════════════════════════
   LIGHTBOX — Se abre al hacer clic en una foto del modal
   Haz clic en cualquier lugar o presiona Escape para cerrar
   ══════════════════════════════════════════════════════════════════════════ */
.lightbox{position:fixed;inset:0;z-index:2000;background:rgba(0,0,0,.93);display:flex;align-items:center;justify-content:center;cursor:zoom-out;opacity:0;pointer-events:none;transition:opacity .2s}
.lightbox.open{opacity:1;pointer-events:all}
.lightbox img{max-width:92vw;max-height:88vh;border-radius:8px;box-shadow:0 24px 80px rgba(0,0,0,.6);object-fit:contain;cursor:default}
.lb-caption{position:absolute;bottom:1.5rem;left:50%;transform:translateX(-50%);background:rgba(0,0,0,.7);color:#fff;padding:.4rem 1.2rem;border-radius:100px;font-size:.82rem;white-space:nowrap;font-family:'DM Sans',sans-serif}
.lb-close{position:absolute;top:1.2rem;right:1.5rem;background:rgba(255,255,255,.15);border:none;color:white;width:40px;height:40px;border-radius:50%;font-size:1.2rem;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:background .2s;z-index:1}
.lb-close:hover{background:rgba(255,255,255,.3)}

/* METHODOLOGY */
#method-section{background:var(--ink);color:var(--white)}
#method-section .section-eyebrow{color:#93C5FD}
#method-section .section-title{color:var(--white)}
.method-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:1.25rem;margin-top:2.5rem}
.method-card{background:#111827;border:1px solid #1F2937;border-radius:var(--r2);padding:1.5rem}
.mc-num{font-family:'DM Mono',monospace;font-size:.7rem;color:var(--az2);font-weight:700;letter-spacing:.1em;margin-bottom:.75rem}
.mc-title{font-weight:700;font-size:1rem;color:var(--white);margin-bottom:.5rem}
.mc-desc{font-size:.85rem;color:#9CA3AF;line-height:1.6}
.mc-new{border-color:rgba(91,33,182,.4);background:rgba(91,33,182,.08)}
.mc-new .mc-num{color:#A78BFA}
footer{background:#060A10;padding:3rem 4vw;display:flex;align-items:center;justify-content:space-between;gap:2rem;flex-wrap:wrap;border-top:1px solid #111827}
.footer-logo{font-family:'Playfair Display',serif;color:var(--white);font-size:1.1rem;font-weight:700}
.footer-logo span{color:var(--gold)}
.footer-text{font-size:.8rem;color:#4B5563}
.fade-in{opacity:0;transform:translateY(24px);transition:opacity .6s ease,transform .6s ease}
.fade-in.visible{opacity:1;transform:translateY(0)}
</style>
</head>
<body>

<!-- HERO -->
<div class="hero" id="top">
  <!-- Para poner foto de fondo: guarda tu imagen como hero-bg.jpg en la misma carpeta -->
  <div class="hero-bg-photo" id="hero-bg"></div>
  <div class="hero-bg-overlay"></div>
  <div class="hero-grid"></div>
  <div class="hero-accent"></div>
  <div class="hero-badge"><svg width="10" height="10" viewBox="0 0 10 10"><circle cx="5" cy="5" r="5" fill="#93C5FD"/></svg>ONU-Hábitat · GIRS Bolivia y Bogotá Circular · 2026</div>
  <h1>Experiencias <em>internacionales</em> innovadoras en Gestión de Residuos</h1>
  <p class="hero-sub">8 casos analizados en 4 continentes — índice ampliado de transferibilidad de 8 dimensiones para contextos andinos.</p>
  <div class="hero-stats">
    <div><span class="hero-stat-num">8</span><span class="hero-stat-label">Experiencias</span></div>
    <div><span class="hero-stat-num">8</span><span class="hero-stat-label">Dimensiones</span></div>
    <div><span class="hero-stat-num">80</span><span class="hero-stat-label">Puntaje máximo</span></div>
    <div><span class="hero-stat-num">5</span><span class="hero-stat-label">Casos ALTA</span></div>
  </div>
  <div class="hero-ctas">
    <a href="#fichas-section" class="btn btn-primary">Ver las 8 fichas ↓</a>
    <a href="#index-section" class="btn btn-ghost">Índice de transferibilidad</a>
  </div>
</div>

<!-- NAV -->
<nav>
  <div class="nav-logo">GIRS <span>Internacional</span></div>
  <div class="nav-links">
    <a class="nav-link" href="#map-section">Mapa</a>
    <a class="nav-link" href="#index-section">Índice</a>
    <a class="nav-link" href="#fichas-section">Fichas</a>
    <a class="nav-link" href="#method-section">Metodología</a>
  </div>
</nav>

<!-- MAP -->
<section id="map-section">
  <div class="map-header fade-in">
    <div class="section-eyebrow">Distribución global</div>
    <h2 class="section-title">8 ciudades. 4 continentes. <em>Un marco común.</em></h2>
    <p class="section-desc">Haz clic en cada pin para explorar la experiencia.</p>
  </div>
  <div class="map-container">
    <svg class="world-map-svg" viewBox="0 0 1000 500" xmlns="http://www.w3.org/2000/svg">
      <rect width="1000" height="500" fill="#0D1117"/>
      <g stroke="#1F2937" stroke-width="0.5" opacity="0.5"><line x1="0" y1="125" x2="1000" y2="125"/><line x1="0" y1="250" x2="1000" y2="250"/><line x1="0" y1="375" x2="1000" y2="375"/><line x1="250" y1="0" x2="250" y2="500"/><line x1="500" y1="0" x2="500" y2="500"/><line x1="750" y1="0" x2="750" y2="500"/></g>
      <path d="M60 60L185 55L205 90L220 130L210 170L190 185L185 215L165 230L150 210L140 180L120 175L110 155L100 140L75 130L60 100Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M185 30L230 25L245 50L225 65L195 60Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M165 230L185 245L195 268L185 278L170 270L165 255Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M190 265L240 260L270 285L280 320L275 360L265 395L245 420L225 430L205 415L190 380L180 340L175 300L180 275Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M430 60L490 55L510 70L505 95L490 110L470 115L455 105L440 95L435 75Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M450 130L510 125L535 145L545 180L550 220L545 265L530 300L510 330L490 340L470 330L450 300L440 260L435 215L435 170L440 145Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M535 120L580 115L595 140L585 165L555 170L535 155Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M490 40L700 35L730 65L720 100L680 110L620 115L590 105L550 100L520 85L495 70Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M600 110L700 105L750 125L770 160L760 195L735 210L700 205L665 190L640 165L615 145L600 130Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M635 155L680 150L700 175L705 210L690 240L668 250L645 240L630 210L628 180Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M740 225L790 220L820 240L825 265L800 275L765 270L745 255Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M800 230L855 225L875 250L870 275L840 280L810 270Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M860 90L880 82L895 100L890 120L870 118Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M700 80L810 72L850 95L845 130L820 145L780 150L750 140L720 125L700 105Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <path d="M790 310L875 300L920 325L935 370L920 410L875 425L830 415L795 385L780 345Z" fill="#1A2535" stroke="#2E3A50" stroke-width="0.8"/>
      <text x="12" y="253" fill="#374151" font-size="9" font-family="monospace">0°</text>
      <text x="12" y="130" fill="#374151" font-size="9" font-family="monospace">45°N</text>
      <g class="map-pin" data-case="0" onclick="openModal(0)"><circle class="outer" cx="525" cy="124" r="18" fill="rgba(46,117,182,.25)"/><circle cx="525" cy="124" r="9" fill="#2E75B6"/><circle cx="525" cy="124" r="5" fill="white"/><text x="525" y="128" text-anchor="middle" fill="#1A3A5C" font-size="7" font-weight="700" font-family="monospace">01</text></g>
      <g class="map-pin" data-case="1" onclick="openModal(1)"><circle class="outer" cx="192" cy="169" r="18" fill="rgba(46,117,182,.25)"/><circle cx="192" cy="169" r="9" fill="#2E75B6"/><circle cx="192" cy="169" r="5" fill="white"/><text x="192" y="173" text-anchor="middle" fill="#1A3A5C" font-size="7" font-weight="700" font-family="monospace">02</text></g>
      <g class="map-pin" data-case="2" onclick="openModal(2)"><circle class="outer" cx="309" cy="73" r="18" fill="rgba(46,117,182,.25)"/><circle cx="309" cy="73" r="9" fill="#2E75B6"/><circle cx="309" cy="73" r="5" fill="white"/><text x="309" y="77" text-anchor="middle" fill="#1A3A5C" font-size="7" font-weight="700" font-family="monospace">03</text></g>
      <g class="map-pin tb" data-case="3" onclick="openModal(3)"><circle class="outer" cx="600" cy="251" r="18" fill="rgba(15,81,50,.3)"/><circle cx="600" cy="251" r="9" fill="#0F5132"/><circle cx="600" cy="251" r="5" fill="white"/><text x="600" y="255" text-anchor="middle" fill="#DCFCE7" font-size="7" font-weight="700" font-family="monospace">04</text></g>
      <g class="map-pin tb" data-case="4" onclick="openModal(4)"><circle class="outer" cx="506" cy="134" r="18" fill="rgba(15,81,50,.3)"/><circle cx="506" cy="134" r="9" fill="#0F5132"/><circle cx="506" cy="134" r="5" fill="white"/><text x="506" y="138" text-anchor="middle" fill="#DCFCE7" font-size="7" font-weight="700" font-family="monospace">05</text></g>
      <g class="map-pin" data-case="5" onclick="openModal(5)"><circle class="outer" cx="799" cy="269" r="18" fill="rgba(46,117,182,.25)"/><circle cx="799" cy="269" r="9" fill="#2E75B6"/><circle cx="799" cy="269" r="5" fill="white"/><text x="799" y="273" text-anchor="middle" fill="#1A3A5C" font-size="7" font-weight="700" font-family="monospace">06</text></g>
      <g class="map-pin tb" data-case="6" onclick="openModal(6)"><circle class="outer" cx="705" cy="198" r="18" fill="rgba(15,81,50,.3)"/><circle cx="705" cy="198" r="9" fill="#0F5132"/><circle cx="705" cy="198" r="5" fill="white"/><text x="705" y="202" text-anchor="middle" fill="#DCFCE7" font-size="7" font-weight="700" font-family="monospace">07</text></g>
      <g class="map-pin tb" data-case="7" onclick="openModal(7)"><circle class="outer" cx="286" cy="283" r="18" fill="rgba(15,81,50,.3)"/><circle cx="286" cy="283" r="9" fill="#0F5132"/><circle cx="286" cy="283" r="5" fill="white"/><text x="286" y="287" text-anchor="middle" fill="#DCFCE7" font-size="7" font-weight="700" font-family="monospace">08</text></g>
    </svg>
    <div class="map-tooltip" id="map-tooltip"></div>
  </div>
  <div class="map-legend">
    <div class="ml-item"><div class="ml-dot" style="background:#2E75B6"></div><span class="ml-label">Tema A: Economía Circular</span></div>
    <div class="ml-item"><div class="ml-dot" style="background:#0F5132"></div><span class="ml-label">Tema B: DDHH e Inclusión</span></div>
    <div class="ml-item" style="margin-left:auto"><span class="ml-label">Haz clic en un pin para ver la ficha</span></div>
  </div>
</section>

<!-- INDEX -->
<section id="index-section">
  <div class="section-header fade-in">
    <div class="section-eyebrow">Índice comparativo</div>
    <h2 class="section-title">Transferibilidad ampliada — <em>8 dimensiones</em></h2>
    <p class="section-desc">Máximo 80 puntos. Las dimensiones 7 y 8 son contribución analítica del equipo consultor.</p>
  </div>
  <div class="dim-legend fade-in">
    <span class="dim-chip" style="background:#DBEAFE;color:#1A3A5C">Pertinencia</span>
    <span class="dim-chip" style="background:#DBEAFE;color:#1A3A5C">Contexto inst.</span>
    <span class="dim-chip" style="background:#DBEAFE;color:#1A3A5C">Normativa</span>
    <span class="dim-chip" style="background:#DBEAFE;color:#1A3A5C">Financiero</span>
    <span class="dim-chip" style="background:#DBEAFE;color:#1A3A5C">Social</span>
    <span class="dim-chip" style="background:#DBEAFE;color:#1A3A5C">Tecnológico</span>
    <span class="dim-chip" style="background:#DCFCE7;color:#0F5132">Inclusión / Género ★</span>
    <span class="dim-chip" style="background:#EDE9FE;color:#5B21B6">Emancipatorio ★</span>
    <span style="font-size:.72rem;color:var(--muted);align-self:center">★ Nuevas dimensiones</span>
  </div>
  <div class="index-controls fade-in">
    <button class="filter-btn active" onclick="filterIndex('all',this)">Todas</button>
    <button class="filter-btn" onclick="filterIndex('alta',this)">ALTA transferibilidad</button>
    <button class="filter-btn" onclick="filterIndex('media',this)">MEDIA transferibilidad</button>
  </div>
  <div class="index-table-wrap fade-in">
    <table><thead><tr>
      <th>#</th><th>Experiencia</th><th>País</th>
      <th title="Pertinencia contextual">Pert.</th><th title="Contexto institucional">Inst.</th>
      <th title="Habilitadores normativos">Norm.</th><th title="Viabilidad financiera">Fin.</th>
      <th title="Aceptación social">Soc.</th><th title="Viabilidad tecnológica">Tec.</th>
      <th title="Inclusión / Género" style="color:#86EFAC">Inc./Gén.</th>
      <th title="Modelo emancipatorio" style="color:#C4B5FD">Eman.</th>
      <th>Total</th><th>Nivel</th>
    </tr></thead>
    <tbody id="index-tbody"></tbody></table>
  </div>
</section>

<!-- FICHAS -->
<section id="fichas-section">
  <div class="section-header fade-in">
    <div class="section-eyebrow">Fichas descriptivas</div>
    <h2 class="section-title">Las <em>8 experiencias</em> en detalle</h2>
    <p class="section-desc">Haz clic en una tarjeta para ver la ficha completa con contexto, modelo operativo, resultados y recomendaciones.</p>
  </div>
  <div class="fichas-filters fade-in">
    <button class="filter-btn active" onclick="filterFichas('all',this)">Todas</button>
    <button class="filter-btn" onclick="filterFichas('a',this)">Tema A: Economía Circular</button>
    <button class="filter-btn" onclick="filterFichas('b',this)">Tema B: DDHH e Inclusión</button>
    <button class="filter-btn" onclick="filterFichas('alta',this)">ALTA transferibilidad</button>
  </div>
  <div class="fichas-grid" id="fichas-grid"></div>
</section>

<!-- METHODOLOGY -->
<section id="method-section">
  <div class="section-header fade-in">
    <div class="section-eyebrow">Metodología</div>
    <h2 class="section-title">Cómo se construyó el <em>índice</em></h2>
    <p class="section-desc" style="color:#9CA3AF">El índice es el resultado del juicio analítico informado del equipo consultor, no de una fórmula automática.</p>
  </div>
  <div class="method-grid fade-in">
    <div class="method-card"><div class="mc-num">DIM 01</div><div class="mc-title">Pertinencia contextual</div><div class="mc-desc">¿Las condiciones del municipio receptor son similares al caso? (tamaño, fracción orgánica, informalidad, base fiscal)</div></div>
    <div class="method-card"><div class="mc-num">DIM 02</div><div class="mc-title">Contexto institucional</div><div class="mc-desc">¿Existe capacidad institucional suficiente a nivel municipal, departamental y nacional para implementar el modelo?</div></div>
    <div class="method-card"><div class="mc-num">DIM 03</div><div class="mc-title">Habilitadores normativos</div><div class="mc-desc">¿Existen marcos legales comparables que permitan implementar el modelo sin cambios normativos mayores?</div></div>
    <div class="method-card"><div class="mc-num">DIM 04</div><div class="mc-title">Viabilidad financiera</div><div class="mc-desc">¿El modelo puede financiarse de forma sostenida con recursos propios, sin cooperación externa permanente?</div></div>
    <div class="method-card"><div class="mc-num">DIM 05</div><div class="mc-title">Aceptación social</div><div class="mc-desc">¿Existe o puede construirse una base social dispuesta a participar y sostener el modelo en el largo plazo?</div></div>
    <div class="method-card"><div class="mc-num">DIM 06</div><div class="mc-title">Viabilidad tecnológica</div><div class="mc-desc">¿La tecnología requerida es accesible, manejable localmente y adaptable a las condiciones del territorio receptor?</div></div>
    <div class="method-card mc-new"><div class="mc-num">DIM 07 — NUEVA</div><div class="mc-title">Inclusión y perspectiva de género</div><div class="mc-desc">¿El modelo incorpora activamente a recicladores de base y mujeres, con mecanismos de educación ciudadana y participación comunitaria?</div></div>
    <div class="method-card mc-new"><div class="mc-num">DIM 08 — NUEVA</div><div class="mc-title">Modelo emancipatorio</div><div class="mc-desc">¿El modelo reconoce a los recicladores como agentes de cambio con control sobre activos, gobernanza democrática e ingresos dignos propios?</div></div>
  </div>
  <div style="margin-top:2.5rem;background:#111827;border:1px solid #1F2937;border-radius:var(--r2);padding:1.5rem 2rem" class="fade-in">
    <div style="display:flex;gap:3rem;flex-wrap:wrap">
      <div><div style="font-size:.72rem;color:#9CA3AF;letter-spacing:.08em;text-transform:uppercase;margin-bottom:.5rem">Umbral ALTA</div><div style="font-family:'Playfair Display',serif;font-size:2rem;font-weight:900;color:#86EFAC">≥ 53 / 80</div></div>
      <div><div style="font-size:.72rem;color:#9CA3AF;letter-spacing:.08em;text-transform:uppercase;margin-bottom:.5rem">Umbral MEDIA</div><div style="font-family:'Playfair Display',serif;font-size:2rem;font-weight:900;color:#FCD34D">37–52 / 80</div></div>
      <div><div style="font-size:.72rem;color:#9CA3AF;letter-spacing:.08em;text-transform:uppercase;margin-bottom:.5rem">Umbral BAJA</div><div style="font-family:'Playfair Display',serif;font-size:2rem;font-weight:900;color:#FCA5A5">&lt; 37 / 80</div></div>
      <div style="flex:1;min-width:200px;align-self:center"><div style="font-size:.85rem;color:#9CA3AF;line-height:1.6">El índice evalúa la viabilidad de <strong style="color:#E5E7EB">adaptar</strong> el modelo al contexto andino, no la calidad de la experiencia en su lugar de origen.</div></div>
    </div>
  </div>
</section>

<footer>
  <div><div class="footer-logo">GIRS <span>Internacional</span></div><div class="footer-text" style="margin-top:.4rem">Consultoría ONU-Hábitat · Bolivia y Bogotá Circular · 2026</div></div>
  <div class="footer-text">Manuela Benavides · Maria José Angarita · Sofía Ramos Castellanos<br>Universidad del Rosario</div>
</footer>

<!-- MODAL -->
<div class="modal-overlay" id="modal-overlay" onclick="closeModalOut(event)">
  <div class="modal" id="modal-box"></div>
</div>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="closeLB()">
  <button class="lb-close" onclick="closeLB()">✕</button>
  <img id="lb-img" src="" alt="" onclick="event.stopPropagation()">
  <div class="lb-caption" id="lb-cap"></div>
</div>

<script>
// ═══════════════════════════════════════════════════════════════════════════
// DATOS — Para añadir fotos cambia los nombres en cada array "fotos"
// Las imágenes deben estar en la misma carpeta que index.html
// ═══════════════════════════════════════════════════════════════════════════
var C=[
  {num:'01',tema:'a',color:'#2E75B6',name:'Food Waste Hubs',city:'Milán',country:'Italia',flag:'🇮🇹',
   entidad:'Ayuntamiento de Milán / AMSA / Asociación Recup',pop:'1,4 M (3,2 M metrop.)',
   scores:{p:7,i:5,n:6,f:5,s:7,t:6,g:4,e:2},total:42,nivel:'MEDIA',
   tagline:'Recuperación comunitaria de desperdicio alimentario a escala urbana.',
   contexto:'Milán genera ~1,4 M toneladas/año de RSU, con 30-35% de orgánicos. Antes de 2019, el 45% de ciudadanos participaba en recolección selectiva y el material llegaba con 25-30% de contaminación cruzada. El 15-20% de alimentos aptos para consumo terminaban desechados.',
   modelo:'Red de 26 hubs anti-desperdicio en los 9 distritos municipales. Cada hub capta excedentes de supermercados (AMSA los recolecta refrigerados) y redistribuye a 27.000 personas vulnerables. Dos modalidades: familias registradas (3x/semana, 15 kg máx.) y comedores sociales.',
   normativa:'Legge Gadda (Ley 166/2016): eliminó barreras fiscales a la donación corporativa, deducción fiscal del 15% de ingresos brutos. Plan Comunal 2018: meta -20% desperdicio per cápita para 2025.',
   resultados:'26 hubs operativos · 180-220 t/mes de alimentos recuperados · 27.000 personas beneficiarias · Inversión €450.000-650.000 (60% municipal + 30% ERDF-UE + 10% corporativo).',
   leccion:'Los hubs representan solo el 2% del desperdicio total: son complemento, no sustituto de transformaciones sistémicas. El modelo no integra recicladores informales: limitación crítica para contextos andinos.',
   asimetria:'El elemento más transferible es la lógica de redistribución desde mercados hacia comedores comunitarios (ollas populares). La segmentación de audiencias en la estrategia educativa es directamente replicable.',
   ods:['ODS 2','ODS 10','ODS 11','ODS 12','ODS 13','ODS 17'],
   odsC:['#DDA63A','#DD1367','#FD9D24','#BF8B2E','#3F7E44','#19486A'],
   /* FOTOS: escribe los nombres de tus imágenes aquí.
      Deben estar en la misma carpeta que index.html.
      La primera foto aparece en la tarjeta; todas en el modal. */
   fotos:['foto-milan-1.jpg','foto-milan-2.jpg']},

  {num:'02',tema:'a',color:'#2E75B6',name:'Proyecto Biciclando',city:'Hermosillo',country:'México',flag:'🇲🇽',
   entidad:'IMPLAN Hermosillo / UNDP',pop:'958.000 hab.',
   scores:{p:8,i:7,n:7,f:6,s:9,t:7,g:8,e:5},total:57,nivel:'ALTA',
   tagline:'Economía circular, movilidad sostenible y empoderamiento femenino en un solo modelo.',
   contexto:'Hermosillo enfrenta tres problemas simultáneos: tasa de reciclaje menor al 2%, transporte motorizado genera 35% de GEI, y barreras de género para empleo formal en sector ambiental. El 50,1% de habitantes son mujeres.',
   modelo:'Centros de Economía Circular (CEC) con liderazgo femenino + recolección puerta a puerta con bicicletas eléctricas cargo + sistema GIS para rutas + Zona Salva (espacio seguro de capacitación para mujeres). Más de 30 bicicladoras formalizadas.',
   normativa:'Reglamento de Ecología de Hermosillo 2024 · Ley de Movilidad y Seguridad Vial de Sonora · Ley Federal del Trabajo · Reconocimiento UNDP como buena práctica ODS.',
   resultados:'>30 mujeres formalizadas con empleo digno · >26.800 kg desviados del relleno sanitario · >4 km de infraestructura ciclista promovida · 1 CEC con liderazgo femenino creado.',
   leccion:'El diseño desde el género genera valor sistémico, no solo equitativo. La sostenibilidad económica post-UNDP es el reto no resuelto: los ingresos por venta de materiales deben demostrar autofinanciación.',
   asimetria:'Altamente transferible a ciudades intermedias de Bolivia y localidades bogotanas con recicladoras de oficio. La Zona Salva es el componente más directamente replicable en centros de acopio de ORs.',
   ods:['ODS 5','ODS 8','ODS 10','ODS 11','ODS 12','ODS 13'],
   odsC:['#FF3A21','#A21942','#DD1367','#FD9D24','#BF8B2E','#3F7E44'],
   fotos:['foto-hermosillo-1.jpg','foto-hermosillo-2.jpg']},

  {num:'03',tema:'a',color:'#2E75B6',name:'Waste Management Initiative',city:'Iqaluit',country:'Canadá',flag:'🇨🇦',
   entidad:'Gobierno Municipal / Gobierno de Nunavut / WWF Arctic',pop:'7.740 hab.',
   scores:{p:8,i:6,n:7,f:5,s:7,t:6,g:3,e:2},total:44,nivel:'MEDIA',
   tagline:'Gestión de residuos en el Ártico: diseño situado en condiciones extremas.',
   contexto:'Iqaluit es la capital de Nunavut, Ártico canadiense. Sin ningún camino a otras comunidades, los residuos deben enviarse al sur por barco en el corto período estival. El incidente Dumpcano (2014) —incendio de 4 meses, 2.000°C— evidenció los riesgos del sistema.',
   modelo:'Vertedero mejorado con controles reforzados + Centro de reuso comunitario + Gestión diferenciada de materiales peligrosos + Compostaje adaptado al permafrost + Exportación estival de reciclables al sur.',
   normativa:'Ley de Residuos Sólidos Enmienda #651 de Iqaluit: tarifas diferenciadas por tipo de residuo, permite reutilización o venta de subproductos. Marcos territoriales de Nunavut para subsidios estructurales.',
   resultados:'Tasa de desvío proyectada: 25-50% · Reducción de incendios espontáneos en el vertedero · Centro de reuso activo · Mayor conciencia ciudadana sobre fragilidad del ecosistema ártico.',
   leccion:'El valor de Iqaluit es METODOLÓGICO: las políticas de GIRS deben construirse desde las condiciones del territorio. La gobernanza multinivel es necesidad operativa, no ideal normativo.',
   asimetria:'El principio de diseño situado aplica a municipios amazónicos y étnicos de Bolivia (Guayaramerín, Cobija, San Matías, San Ignacio de Moxos). El centro de reuso es el componente operativo más transferible.',
   ods:['ODS 3','ODS 11','ODS 12','ODS 13','ODS 15','ODS 16'],
   odsC:['#4C9F38','#FD9D24','#BF8B2E','#3F7E44','#56C02B','#00689D'],
   fotos:['foto-iqaluit-1.jpg']},

  {num:'04',tema:'b',color:'#0F5132',name:'NAWACOM',city:'Nakuru',country:'Kenia',flag:'🇰🇪',
   entidad:'NAWACOM / Practical Action Kenya',pop:'570.000 hab.',
   scores:{p:9,i:8,n:7,f:7,s:10,t:7,g:8,e:9},total:65,nivel:'ALTA',
   tagline:'Cooperativa de recicladores que produce compost de marca propia y gestiona su sistema democráticamente.',
   contexto:'Nakuru: 4a ciudad más poblada de Kenia. El 60-65% de la población en asentamientos informales. El sistema municipal cubría solo el 30% de la ciudad. 513 t/día de residuos (80% orgánicos) se gestionaban via deposición en cunetas, márgenes del lago Nakuru y quema abierta.',
   modelo:'12 CBOs fundadoras (2002) → NAWACOM: cooperativa de 336 miembros en 25 grupos comunitarios, gobernanza "one member, one vote". Recolección vecinal descentralizada + almacén go-down 400m² + compostaje 90 días + marca Mazingira Organic Fertilizer para agricultores ecológicos.',
   normativa:'Cooperative Societies Act (Kenia) → préstamo Kenya Women Finance Trust (2006, US$26.000) → Reconocimiento Nakuru County Government post-descentralización 2010: permiso dumpsite, cesión terreno 20 años, compra preferencial compost.',
   resultados:'336 miembros activos · 2.500-3.000 t orgánicos/año a US$20-27/t (vs. US$40-80/t municipal) · Incremento de ingresos del 275% · 68% de miembros son mujeres · 5/9 directivos son mujeres.',
   leccion:'La integración emancipatoria genera eficiencia superior al compostaje municipal formal. La cooperativa fue el habilitador estructural para el préstamo, el terreno y las cuentas bancarias. Identificar el mercado destino ANTES de escalar.',
   asimetria:'Referente más directamente transferible para Bolivia: la tradición cooperativista boliviana, OECOMAs y perfil de recicladores son análogos. Proceso: diagnóstico → cooperativa (cuota 40% mujeres) → identificar mercado compost → microfinanzas → convenio municipal.',
   ods:['ODS 1','ODS 2','ODS 5','ODS 8','ODS 11','ODS 12'],
   odsC:['#E5243B','#DDA63A','#FF3A21','#A21942','#FD9D24','#BF8B2E'],
   fotos:['foto-nakuru-1.jpg','foto-nakuru-2.jpg']},

  {num:'05',tema:'b',color:'#991B1B',name:'Granollers — Reciclaje informal',city:'Granollers',country:'España',flag:'🇪🇸',
   entidad:'Ayuntamiento de Granollers / AMSA / UAB',pop:'61.129 hab.',
   scores:{p:8,i:7,n:6,f:5,s:6,t:7,g:3,e:2},total:44,nivel:'MEDIA',
   tagline:'Lección negativa: cómo la eficiencia técnica puede coexistir con exclusión social severa.',
   neg:true,
   contexto:'Sistema de GIRS técnicamente eficiente: 82% participación, 43,2% tasa de reciclaje (2022). Sin embargo, entre 2013-2023 emerge proliferación de chatarreros informales —migrantes en situación irregular— que recuperan el 44% del cartón comercial antes de la recolección oficial (estudio UAB 2018-2019, 37 trabajadores).',
   modelo:'Sistema formal: 234 rutas mecanizadas, eficiente. Sistema informal: recorridos nocturnos 22:00-6:00, carritos improvisados, 80-150 kg/ruta, €8-15/ruta, €150-300/mes. Mesa de Diálogo Reciclaje Inclusivo (2021-2022): 6 reuniones sin resultados implementados.',
   normativa:'Ley 7/2022 RSU España: residuos en vía pública son propiedad municipal → limbo legal. Contratación pública requiere situación legal (78% de recicladores carece de ella). Las mesas de diálogo no tienen poder ejecutivo ni presupuesto.',
   resultados:'Sistema formal: técnicamente satisfactorio. Sistema informal: 37 trabajadores en extrema precariedad, sin protección social. Parálisis decisoria durante más de 10 años.',
   leccion:'1) No se puede tecnificar sin haber integrado primero. 2) La eficiencia técnica puede coexistir con exclusión social severa. 3) Las mesas de diálogo sin mandato político y presupuesto no producen cambios.',
   asimetria:'ADVERTENCIA para Bolivia y Bogotá: no avanzar en tecnificación del sistema sin diseñar simultáneamente el mecanismo de integración del reciclador informal. Toda modernización en Bogotá debe ir precedida de análisis de impacto en ORs.',
   ods:['ODS 1','ODS 8','ODS 10','ODS 11','ODS 12','ODS 16'],
   odsC:['#E5243B','#A21942','#DD1367','#FD9D24','#BF8B2E','#00689D'],
   fotos:['foto-granollers-1.jpg']},

  {num:'06',tema:'a',color:'#2E75B6',name:'Zero Waste Cities / YPBB',city:'Bandung',country:'Indonesia',flag:'🇮🇩',
   entidad:'YPBB / Municipio de Bandung / GAIA',pop:'2,5 M hab.',
   scores:{p:9,i:8,n:7,f:8,s:9,t:8,g:6,e:5},total:60,nivel:'ALTA',
   tagline:'Transformación comunitaria de la gestión de residuos — 86% de desvío potencial con compostaje descentralizado.',
   contexto:'Bandung genera 1.500-1.600 t/día de RSU (63% orgánicos). El colapso del vertedero Leuwigajah (2005, más de 140 muertes) creó el momentum político para transformar el sistema. El desastre impulsó la Ley de Gestión de Residuos 18/2008.',
   modelo:'Modelo descentralizado de 4 componentes: (1) Segregación en fuente domiciliar · (2) Recolección separada por operadores locales · (3) Compostaje doméstico y comunitario de orgánicos · (4) Waste banks para inorgánicos reciclables con créditos individuales. Kelurahan (barrios) como unidades de implementación.',
   normativa:'Ley 18/2008 post-desastre Leuwigajah: enfoque integral reducción-reciclaje-tratamiento. Políticas municipales de Bandung fortaleciendo separación en fuente y expansión de waste banks.',
   resultados:'>40% participación en barrios piloto · Reducciones significativas en residuos al sistema municipal · Proyección: 86% de reducción con separación y compostaje a escala ciudad · Expansión de red de waste banks.',
   leccion:'La participación comunitaria transforma los sistemas de GIRS incluso en alta densidad. Los waste banks son infraestructura SOCIAL. El desafío es la escalabilidad fuera de los barrios piloto.',
   asimetria:'La composición de residuos bolivianos (60-70% orgánicos) es análoga a la de Bandung (63%), haciendo el modelo de compostaje descentralizado altamente pertinente. Los waste banks son directamente replicables en zonas periurbanas con mercados agrícolas locales.',
   ods:['ODS 3','ODS 4','ODS 11','ODS 12','ODS 13','ODS 15'],
   odsC:['#4C9F38','#C5192D','#FD9D24','#BF8B2E','#3F7E44','#56C02B'],
   fotos:['foto-bandung-1.jpg','foto-bandung-2.jpg']},

  {num:'07',tema:'b',color:'#0F5132',name:'SWaCH',city:'Pune',country:'India',flag:'🇮🇳',
   entidad:'SWaCH Cooperative / PMC / KKPKP',pop:'6 M hab.',
   scores:{p:9,i:8,n:7,f:8,s:10,t:7,g:9,e:10},total:68,nivel:'ALTA',
   tagline:'El caso más robusto de integración emancipatoria a gran escala: 3.761 recicladores, US$4,8 M en ahorros para la municipalidad.',
   contexto:'Pune, Maharashtra, India. La red informal de kabadiwallas recolectaba ~144 t/día, generando ahorros de US$220.000/año para el PMC. El sindicato KKPKP cuantificó ese valor y lo usó como argumento económico para construir voluntad política municipal.',
   modelo:'Cooperativa SWaCH + PMC: modelo de doble ingreso (tarifa mensual de usuarios + derecho a venta de materiales recuperados). Arquitectura híbrida: recolección descentralizada por 3.761 recicladores + clasificación centralizada en 12 plantas MRF. Cobertura: más de 800.000 hogares.',
   normativa:'Reglas de Gestión de RSU 2016 de India: reconocimiento formal de recicladores de base. Convenio contractual PMC-SWaCH. El riesgo es la dependencia de la voluntad política municipal ante cambios de gobierno.',
   resultados:'Más de 800.000 hogares atendidos · 277 t/día desviadas del vertedero · Ahorros para PMC: US$4,2-4,8 M/año · Incremento de ingresos de recicladores: 500-800% · Mayoría de trabajadores son mujeres.',
   leccion:'El argumento económico (US$220.000 ahorros) fue más efectivo que el argumento de justicia social para construir voluntad política. La integración emancipatoria supera en eficiencia a contratistas privados. El doble ingreso elimina la dependencia del subsidio.',
   asimetria:'Referente más directo para Bogotá Circular. Recomendaciones: contratos mínimo 5 años con ORs + doble ingreso explícito en convenios UAESP + fondo de capitalización para que ORs sean propietarias de activos + 50% representación femenina como requisito.',
   ods:['ODS 3','ODS 5','ODS 8','ODS 10','ODS 11','ODS 12'],
   odsC:['#4C9F38','#FF3A21','#A21942','#DD1367','#FD9D24','#BF8B2E'],
   fotos:['foto-pune-1.jpg','foto-pune-2.jpg','foto-pune-3.jpg']},

  {num:'08',tema:'b',color:'#0F5132',name:'Formalización de Recicladores',city:'Comas, Lima',country:'Perú',flag:'🇵🇪',
   entidad:'Municipalidad Distrital de Comas / OPMI',pop:'Distrito Lima Metropolitana',
   scores:{p:10,i:9,n:8,f:7,s:9,t:7,g:7,e:7},total:64,nivel:'ALTA',
   tagline:'El referente latinoamericano más cercano para Bolivia: formalización via ordenanza municipal.',
   contexto:'Comas, norte de Lima Metropolitana. Crecimiento acelerado y expansión urbana desorganizada: incremento de 640 t en generación de RSU (OPMI 2023). La informalidad de recicladores generaba botaderos clandestinos y ausencia de derechos laborales.',
   modelo:'Formalización de 4 asociaciones de recicladores (ACOSUR, Prince de Paz, ARULN, Luz Divina) mediante convenios municipales y permisos administrativos. 17 recicladores formalizados. Áreas de acondicionamiento para clasificación. Recolección diferenciada en origen.',
   normativa:'Ley de Residuos Sólidos del Perú · Ley General del Ambiente · Ordenanza Municipal de Comas 2023: reconoce las cuatro asociaciones como actores formales del sistema.',
   resultados:'17 recicladores formalizados con personería jurídica · Aumento de residuos diferenciados · Mejoramiento de condiciones laborales (seguridad social) · Reducción de botaderos clandestinos.',
   leccion:'La formalización con reconocimiento de derechos transforma al reciclador: de trabajador invisible a actor reconocido. La cobertura limitada (17 recicladores) es el principal desafío. Escalar e incorporar el doble ingreso de SWaCH son condiciones para la sostenibilidad.',
   asimetria:'Mayor pertinencia contextual para Bolivia: crecimiento urbano desorganizado, alta informalidad, marco legal nacional habilitador comparable. Replicable en Cochabamba, Oruro, Santa Cruz, El Alto, Tarija.',
   ods:['ODS 1','ODS 3','ODS 8','ODS 10','ODS 11','ODS 12'],
   odsC:['#E5243B','#4C9F38','#A21942','#DD1367','#FD9D24','#BF8B2E'],
   fotos:['foto-comas-1.jpg','foto-comas-2.jpg']}
];

var DK=['p','i','n','f','s','t','g','e'];
var DL=['Pertinencia','Inst.','Norm.','Fin.','Social','Tec.','Inc./Gén.','Eman.'];

function sc(v){return v>=8?'ds-h':v>=5?'ds-m':'ds-l';}
function bc(v){return v>=8?'#22C55E':v>=5?'#F59E0B':'#EF4444';}
function nb(n){return '<span class="niv niv-'+(n==='ALTA'?'a':'m')+'">'+n+'</span>';}

// INDEX
function buildIndex(f){
  var tb=document.getElementById('index-tbody');tb.innerHTML='';
  C.forEach(function(c,i){
    if(f==='alta'&&c.nivel!=='ALTA')return;
    if(f==='media'&&c.nivel!=='MEDIA')return;
    var tr=document.createElement('tr');
    tr.onclick=function(){openModal(i);};
    var dc=DK.map(function(k){
      var v=c.scores[k];
      var ex=(k==='g'||k==='e')?'border-left:2px solid #4B5563;':'';
      return '<td style="'+ex+'"><span class="dim-score '+sc(v)+'">'+v+'</span></td>';
    }).join('');
    var tc=c.nivel==='ALTA'?'#22C55E':'#F59E0B';
    tr.innerHTML='<td><span class="td-num">'+c.num+'</span></td>'
      +'<td><div class="td-name">'+c.name+'</div><div class="td-c">'+c.flag+' '+c.city+'</div></td>'
      +'<td><span class="td-c">'+c.country+'</span></td>'
      +dc
      +'<td><span class="total-b" style="color:'+tc+'">'+c.total+'</span></td>'
      +'<td>'+nb(c.nivel)+'</td>';
    tb.appendChild(tr);
  });
}
buildIndex('all');
function filterIndex(f,b){
  document.querySelectorAll('.index-controls .filter-btn').forEach(function(x){x.classList.remove('active');});
  b.classList.add('active');buildIndex(f);
}

// FICHAS
function buildFichas(f){
  var g=document.getElementById('fichas-grid');g.innerHTML='';
  C.forEach(function(c,i){
    var show=true;
    if(f==='a'&&c.tema!=='a')show=false;
    if(f==='b'&&c.tema!=='b')show=false;
    if(f==='alta'&&c.nivel!=='ALTA')show=false;
    var card=document.createElement('div');
    card.className='ficha-card'+(show?'':' hidden');
    card.onclick=function(){openModal(i);};
    var tc=c.nivel==='ALTA'?'#0F5132':'#C55A11';
    var tl=c.tema==='a'?'Tema A':'Tema B';
    var tcl=c.tema==='a'?'ta':'tb2';
    var neg=c.neg?'<div style="display:inline-flex;align-items:center;gap:.3rem;background:#FEE2E2;color:#991B1B;font-size:.68rem;font-weight:700;padding:.2rem .6rem;border-radius:100px;margin-left:.5rem">⚠ Lección negativa</div>':'';
    var bars=['p','s','g','e'].map(function(k,idx){
      var lbl=['Pertinencia','Social','Inclusión/Gén.','Emancipatorio'];
      var v=c.scores[k];var bcc=bc(v);
      return '<div class="fc-score-row"><span class="fc-score-label">'+lbl[idx]+'</span>'
        +'<div class="fc-score-bar-wrap"><div class="fc-score-bar" style="width:'+v*10+'%;background:'+bcc+'"></div></div>'
        +'<span class="fc-score-val" style="color:'+bcc+'">'+v+'</span></div>';
    }).join('');
    // Foto en tarjeta — sin backticks anidados
    var ph='';
    if(c.fotos&&c.fotos.length>0&&c.fotos[0]){
      ph='<div class="fc-photo-wrap">'
        +'<img class="fc-photo" src="'+c.fotos[0]+'" alt="Foto de '+c.name+'"'
        +' onerror="this.parentElement.style.display=\'none\'">'
        +'</div>';
    }
    card.innerHTML=
      '<div class="fc-stripe" style="background:'+c.color+'"></div>'
      +'<div class="fc-header"><div class="fc-num-wrap"><span class="fc-num">FICHA '+c.num+'</span>'+neg+'</div>'
      +'<span class="fc-tema '+tcl+'">'+tl+'</span></div>'
      +'<div class="fc-title">'+c.name+'</div>'
      +'<div class="fc-loc">📍 '+c.flag+' '+c.city+', '+c.country+'</div>'
      +ph
      +'<div class="fc-desc">'+c.tagline+'</div>'
      +'<div class="fc-scores">'+bars+'</div>'
      +'<div class="fc-footer"><div><span class="fc-total" style="color:'+tc+'">'+c.total+'/80</span></div>'
      +nb(c.nivel)+'<button class="fc-btn">Ver ficha completa →</button></div>';
    g.appendChild(card);
  });
}
buildFichas('all');
function filterFichas(f,b){
  document.querySelectorAll('.fichas-filters .filter-btn').forEach(function(x){x.classList.remove('active');});
  b.classList.add('active');buildFichas(f);
}

// MODAL
function openModal(i){
  var c=C[i];
  var ov=document.getElementById('modal-overlay');
  var box=document.getElementById('modal-box');
  var tc=c.nivel==='ALTA'?'#0F5132':'#C55A11';
  var sc2=DK.map(function(k,idx){
    var v=c.scores[k];var bcc=bc(v);
    var isN=k==='g'||k==='e';
    return '<div class="msi"'+(isN?' style="border:1.5px solid #DDD6FE"':'')+'>'
      +'<div class="msi-l"'+(isN?' style="color:#7C3AED"':'')+'>'
      +DL[idx]+(isN?' ★':'')+'</div>'
      +'<div class="msi-bw"><div class="msi-b" style="width:'+v*10+'%;background:'+bcc+'"></div></div>'
      +'<span class="msi-v" style="color:'+bcc+'">'+v+'/10</span></div>';
  }).join('');
  var ods=c.ods.map(function(o,idx){
    return '<span class="ods-tag" style="background:'+c.odsC[idx]+'">'+o+'</span>';
  }).join('');
  var neg=c.neg?'<div class="lecneg"><span>⚠</span><span><strong>Lección negativa:</strong> Este caso no documenta un modelo a replicar sino una advertencia: ilustra los riesgos de tecnificar sin integrar previamente al reciclador informal.</span></div>':'';
  // Galería — concatenación de strings, sin backticks anidados
  var gal='';
  if(c.fotos&&c.fotos.length>0){
    var imgs='';
    for(var fi=0;fi<c.fotos.length;fi++){
      var f2=c.fotos[fi];
      if(!f2)continue;
      imgs+='<img src="'+f2+'" alt="Foto '+(fi+1)+' de '+c.name+'"'
        +' onclick="openLB(\''+f2+'\',\''+c.name+' — foto '+(fi+1)+'\')"'
        +' onerror="this.style.display=\'none\'">';
    }
    gal='<div class="modal-st">Galería fotográfica</div><div class="modal-gallery">'+imgs+'</div>';
  }
  var rad=buildRadar(c.scores,c.color);
  var b6=DK.slice(0,6).reduce(function(s,k){return s+c.scores[k];},0);
  var a2=c.scores.g+c.scores.e;
  box.innerHTML=
    '<div class="modal-stripe" style="background:'+c.color+'"></div>'
    +'<button class="modal-close" onclick="closeModal()">✕</button>'
    +'<div class="modal-header">'
    +'<div class="modal-num">FICHA '+c.num+' · '+(c.tema==='a'?'TEMA A: ECONOMÍA CIRCULAR':'TEMA B: DDHH E INCLUSIÓN')+'</div>'
    +'<div class="modal-title">'+c.name+'</div>'
    +'<div class="modal-meta">'
    +'<span style="font-size:.83rem;color:var(--muted)">📍 '+c.flag+' '+c.city+', '+c.country+'</span>'
    +'<span style="color:var(--muted);font-size:.8rem">·</span>'
    +'<span style="font-size:.8rem;color:var(--muted)">'+c.entidad+'</span>'
    +'<span style="font-size:.8rem;color:var(--muted)">· Pob: '+c.pop+'</span>'
    +'</div></div>'
    +'<div class="modal-body">'
    +neg+gal
    +'<div class="modal-st">Contexto</div><p class="modal-text">'+c.contexto+'</p>'
    +'<div class="modal-st">Modelo operativo e innovación</div><p class="modal-text">'+c.modelo+'</p>'
    +'<div class="modal-st">Marco normativo</div><p class="modal-text">'+c.normativa+'</p>'
    +'<div class="modal-st">Resultados alcanzados</div><p class="modal-text">'+c.resultados+'</p>'
    +'<div class="modal-st">Lección aprendida / Lectura crítica</div><p class="modal-text">'+c.leccion+'</p>'
    +'<div class="modal-st">Asimetría territorial — Bolivia y Bogotá</div><p class="modal-text">'+c.asimetria+'</p>'
    +'<div class="modal-st">Vinculación con los ODS</div><div class="modal-tags">'+ods+'</div>'
    +'<div class="modal-st">Índice de transferibilidad</div>'
    +'<div class="radar-wrap">'+rad+'</div>'
    +'<div class="modal-sg">'+sc2+'</div>'
    +'<div class="modal-tr">'
    +'<div><div class="mtr-l">Puntuación total</div><div class="mtr-t" style="color:'+tc+'">'+c.total+'/80</div></div>'
    +'<div style="text-align:center"><div class="mtr-l" style="margin-bottom:.4rem">Dims 1-6</div><div style="font-family:\'Playfair Display\',serif;font-size:1.6rem;font-weight:900;color:#93C5FD">'+b6+'/60</div></div>'
    +'<div style="text-align:center"><div class="mtr-l" style="margin-bottom:.4rem">Dims 7-8 ★</div><div style="font-family:\'Playfair Display\',serif;font-size:1.6rem;font-weight:900;color:#C4B5FD">'+a2+'/20</div></div>'
    +'<div>'+nb(c.nivel)+'</div></div></div>';
  ov.classList.add('open');document.body.style.overflow='hidden';
}

function buildRadar(scores,color){
  var vals=DK.map(function(k){return scores[k];});
  var N=vals.length;var cx=140,cy=130,r=90;
  var angs=vals.map(function(_,i){return -Math.PI/2+(i/N)*2*Math.PI;});
  function pt(v,i){var a=angs[i];var d=(v/10)*r;return[cx+d*Math.cos(a),cy+d*Math.sin(a)];}
  var circ=[2,4,6,8,10].map(function(v){
    var pts=vals.map(function(_,i){return pt(v,i);});
    return '<polygon points="'+pts.map(function(p){return p.join(',');}).join(' ')+'" fill="none" stroke="#E5E7EB" stroke-width="0.7"/>';
  }).join('');
  var spk=vals.map(function(_,i){var p=pt(10,i);return '<line x1="'+cx+'" y1="'+cy+'" x2="'+p[0]+'" y2="'+p[1]+'" stroke="#E5E7EB" stroke-width="0.7"/>';}).join('');
  var dPts=vals.map(function(_,i){return pt(vals[i],i);});
  var poly='<polygon points="'+dPts.map(function(p){return p.join(',');}).join(' ')+'" fill="'+color+'" fill-opacity="0.18" stroke="'+color+'" stroke-width="1.8"/>';
  var dots=dPts.map(function(p,i){var n=i>=6;return '<circle cx="'+p[0]+'" cy="'+p[1]+'" r="'+(n?4:3)+'" fill="'+(n?'#7C3AED':color)+'" stroke="white" stroke-width="1.2"/>';}).join('');
  var lbs=DL.map(function(l,i){var p=pt(11.5,i);var n=i>=6;return '<text x="'+p[0]+'" y="'+p[1]+'" text-anchor="middle" dominant-baseline="middle" font-size="8.5" fill="'+(n?'#7C3AED':'#6B7280')+'" font-family="DM Sans,sans-serif" font-weight="'+(n?700:400)+'">'+l+'</text>';}).join('');
  return '<svg class="radar-svg" viewBox="0 0 280 260" xmlns="http://www.w3.org/2000/svg">'+circ+spk+poly+dots+lbs+'</svg>';
}

function closeModal(){document.getElementById('modal-overlay').classList.remove('open');document.body.style.overflow='';}
function closeModalOut(e){if(e.target===document.getElementById('modal-overlay'))closeModal();}
document.addEventListener('keydown',function(e){if(e.key==='Escape'){closeModal();closeLB();}});

// LIGHTBOX
function openLB(src,cap){
  var lb=document.getElementById('lightbox');
  document.getElementById('lb-img').src=src;
  document.getElementById('lb-cap').textContent=cap;
  lb.classList.add('open');
}
function closeLB(){document.getElementById('lightbox').classList.remove('open');}

// MAP TOOLTIP
document.querySelectorAll('.map-pin').forEach(function(pin){
  pin.addEventListener('mouseenter',function(){
    var idx=parseInt(pin.dataset.case);var c=C[idx];
    var tt=document.getElementById('map-tooltip');
    var tc=c.nivel==='ALTA'?'#0F5132':'#C55A11';
    var nb2=c.nivel==='ALTA'?'#DCFCE7':'#FEF3C7';
    tt.innerHTML='<div class="mt-num">FICHA '+c.num+'</div><div class="mt-name">'+c.name+'</div>'
      +'<div class="mt-country">'+c.flag+' '+c.city+', '+c.country+'</div>'
      +'<div class="mt-score niv" style="background:'+nb2+';color:'+tc+';margin-top:.5rem">'+c.total+'/80 · '+c.nivel+'</div>';
    var svgEl=pin.closest('svg');
    var circles=pin.querySelectorAll('circle');
    var mc=circles[1];
    var pt2=svgEl.createSVGPoint();pt2.x=parseFloat(mc.getAttribute('cx'));pt2.y=parseFloat(mc.getAttribute('cy'));
    var sp=pt2.matrixTransform(svgEl.getScreenCTM());
    var cont=document.querySelector('.map-container');var cr=cont.getBoundingClientRect();
    var left=sp.x-cr.left+15;var top=sp.y-cr.top-70;
    if(left+210>cr.width)left=sp.x-cr.left-215;if(top<0)top=sp.y-cr.top+20;
    tt.style.left=left+'px';tt.style.top=top+'px';tt.classList.add('visible');
  });
  pin.addEventListener('mouseleave',function(){document.getElementById('map-tooltip').classList.remove('visible');});
});

// NAV scroll active
window.addEventListener('scroll',function(){
  var secs=['map-section','index-section','fichas-section','method-section'];
  var cur='';
  secs.forEach(function(id){var el=document.getElementById(id);if(el&&el.getBoundingClientRect().top<120)cur=id;});
  document.querySelectorAll('.nav-link').forEach(function(l){l.classList.toggle('active',l.getAttribute('href')==='#'+cur);});
});

// Fade-in
var io=new IntersectionObserver(function(entries){
  entries.forEach(function(e){if(e.isIntersecting){e.target.classList.add('visible');io.unobserve(e.target);}});
},{threshold:0.08});
document.querySelectorAll('.fade-in').forEach(function(el){io.observe(el);});

// Hero background photo — si hero-bg.jpg no existe, el hero queda oscuro sin error
(function(){
  var hb=document.getElementById('hero-bg');
  var img=new Image();
  img.onload=function(){hb.classList.add('loaded');};
  img.src='hero-bg.jpg';
})();
</script>
</body>
</html>
