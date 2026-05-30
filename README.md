<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>RutaFondo – Alexandro Morillas | Asesor Maqui+</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --ink:     #0C1220;
  --ink2:    #1E2D45;
  --slate:   #3D5166;
  --muted:   #7A8FA8;
  --line:    #D8E3EE;
  --bg:      #F4F8FD;
  --white:   #FFFFFF;
  --blue:    #1B4FD8;
  --blue2:   #2E80FF;
  --accent:  #F0A500;
  --green:   #0DAF6D;
  --green2:  #25D366;
  --red:     #E03B3B;
}

html { scroll-behavior: smooth; }

body {
  font-family: 'Plus Jakarta Sans', sans-serif;
  background: var(--bg);
  color: var(--ink);
  overflow-x: hidden;
}

/* ─── NOISE TEXTURE overlay ─── */
body::before {
  content: '';
  position: fixed; inset: 0; z-index: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events: none;
  opacity: .5;
}

/* ─── TOPBAR ─── */
.topbar {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  padding: 0 40px;
  height: 64px;
  display: flex; align-items: center; justify-content: space-between;
  background: rgba(244,248,253,0.85);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(216,227,238,0.6);
}
.topbar-logo {
  font-family: 'Playfair Display', serif;
  font-size: 22px; font-weight: 900;
  color: var(--ink);
  letter-spacing: -0.5px;
}
.topbar-logo em { color: var(--blue); font-style: normal; }
.topbar-cta {
  display: inline-flex; align-items: center; gap: 8px;
  background: var(--green2);
  color: #fff;
  font-size: 13px; font-weight: 600;
  padding: 9px 20px;
  border-radius: 100px;
  text-decoration: none;
  transition: opacity .2s, transform .2s;
}
.topbar-cta:hover { opacity: .9; transform: translateY(-1px); }

/* ─── HERO ─── */
.hero {
  min-height: 100vh;
  position: relative;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 60px;
  max-width: 1100px;
  margin: 0 auto;
  padding: 120px 40px 80px;
}
@media(max-width:820px){ .hero { grid-template-columns:1fr; padding:100px 24px 60px; } }

.hero-bg {
  position: absolute; inset: 0; z-index: -1;
  background:
    radial-gradient(ellipse 80% 60% at 70% 40%, rgba(46,128,255,0.10) 0%, transparent 60%),
    radial-gradient(ellipse 50% 50% at 20% 80%, rgba(13,175,109,0.07) 0%, transparent 60%),
    linear-gradient(180deg, #EDF3FC 0%, #F4F8FD 100%);
}

/* Decorative circles */
.hero-bg::before {
  content:'';
  position:absolute;
  width:420px; height:420px;
  border-radius:50%;
  border: 1px solid rgba(27,79,216,0.10);
  top: 15%; right: -80px;
  animation: spin 30s linear infinite;
}
.hero-bg::after {
  content:'';
  position:absolute;
  width:240px; height:240px;
  border-radius:50%;
  border: 1px solid rgba(27,79,216,0.08);
  top: 20%; right: -20px;
  animation: spin 20s linear infinite reverse;
}
@keyframes spin { to { transform: rotate(360deg); } }

.hero-left { position: relative; }

.hero-eyebrow {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(27,79,216,0.07);
  border: 1px solid rgba(27,79,216,0.18);
  border-radius: 100px;
  padding: 7px 16px;
  font-size: 11px; font-weight: 700;
  color: var(--blue);
  letter-spacing: .12em;
  text-transform: uppercase;
  margin-bottom: 24px;
  opacity: 0; animation: fadeUp .7s ease .1s both;
}

.hero-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(38px, 5.5vw, 64px);
  font-weight: 900;
  line-height: 1.08;
  color: var(--ink);
  margin-bottom: 22px;
  opacity: 0; animation: fadeUp .8s ease .2s both;
}
.hero-title .accent-word {
  color: var(--blue);
  position: relative;
  display: inline-block;
}
.hero-title .accent-word::after {
  content: '';
  position: absolute;
  bottom: 2px; left: 0; right: 0;
  height: 4px;
  background: var(--accent);
  border-radius: 2px;
  transform: scaleX(0);
  transform-origin: left;
  animation: underlineIn .6s ease .9s both;
}
@keyframes underlineIn { to { transform: scaleX(1); } }

.hero-desc {
  font-size: 16px; font-weight: 400;
  color: var(--slate);
  line-height: 1.75;
  max-width: 480px;
  margin-bottom: 36px;
  opacity: 0; animation: fadeUp .8s ease .35s both;
}

.hero-actions {
  display: flex; gap: 14px; flex-wrap: wrap;
  opacity: 0; animation: fadeUp .8s ease .5s both;
}

.btn-wsp {
  display: inline-flex; align-items: center; gap: 10px;
  background: linear-gradient(135deg, var(--green2), #128C7E);
  color: #fff;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-weight: 700; font-size: 15px;
  padding: 15px 30px;
  border-radius: 14px;
  text-decoration: none;
  box-shadow: 0 8px 28px rgba(37,211,102,0.30);
  transition: transform .2s, box-shadow .2s;
}
.btn-wsp:hover { transform: translateY(-2px); box-shadow: 0 14px 36px rgba(37,211,102,0.40); }

.btn-outline {
  display: inline-flex; align-items: center; gap: 8px;
  background: transparent;
  color: var(--ink2);
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-weight: 600; font-size: 15px;
  padding: 14px 28px;
  border-radius: 14px;
  border: 1.5px solid var(--line);
  text-decoration: none;
  transition: border-color .2s, color .2s, background .2s;
  cursor: pointer;
}
.btn-outline:hover { border-color: var(--blue); color: var(--blue); background: rgba(27,79,216,0.04); }

/* Hero right — floating card */
.hero-right {
  opacity: 0; animation: fadeUp .9s ease .4s both;
}

.hero-card {
  background: var(--white);
  border: 1px solid var(--line);
  border-radius: 28px;
  padding: 36px 32px;
  box-shadow:
    0 2px 4px rgba(12,18,32,0.04),
    0 12px 40px rgba(12,18,32,0.08),
    0 40px 80px rgba(27,79,216,0.06);
  position: relative;
}
.hero-card::before {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: 29px;
  background: linear-gradient(135deg, rgba(27,79,216,0.15), rgba(46,128,255,0.05), transparent 60%);
  z-index: -1;
}

.hc-tag {
  font-size: 11px; font-weight: 700; letter-spacing: .1em;
  text-transform: uppercase; color: var(--muted);
  margin-bottom: 20px;
}
.hc-advisor {
  display: flex; align-items: center; gap: 16px;
  padding-bottom: 20px;
  border-bottom: 1px solid var(--line);
  margin-bottom: 20px;
}
.hc-avatar {
  width: 54px; height: 54px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--blue), var(--blue2));
  display: flex; align-items: center; justify-content: center;
  font-family: 'Playfair Display', serif;
  font-size: 20px; font-weight: 900; color: #fff;
  flex-shrink: 0;
  box-shadow: 0 4px 16px rgba(27,79,216,0.30);
}
.hc-name { font-weight: 700; font-size: 16px; color: var(--ink); }
.hc-role { font-size: 12px; color: var(--muted); margin-top: 2px; }

.hc-stats {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 12px; margin-bottom: 20px;
}
.hc-stat {
  background: var(--bg);
  border-radius: 12px;
  padding: 14px 16px;
}
.hc-stat-val {
  font-family: 'Playfair Display', serif;
  font-size: 22px; font-weight: 700;
  color: var(--blue);
  line-height: 1;
  margin-bottom: 4px;
}
.hc-stat-lbl { font-size: 11px; color: var(--muted); font-weight: 500; }

.hc-badges { display: flex; flex-wrap: wrap; gap: 8px; }
.hc-badge {
  display: inline-flex; align-items: center; gap: 5px;
  background: #F0FDF6;
  border: 1px solid #A7F3D0;
  border-radius: 8px;
  padding: 5px 10px;
  font-size: 11px; font-weight: 600; color: #065F46;
}

/* ─── SECTION WRAPPER ─── */
.section {
  max-width: 1100px;
  margin: 0 auto;
  padding: 90px 40px;
  position: relative; z-index: 1;
}
@media(max-width:600px){ .section { padding: 70px 20px; } }

.section-eyebrow {
  display: inline-flex; align-items: center; gap: 6px;
  font-size: 11px; font-weight: 700; letter-spacing: .14em;
  text-transform: uppercase; color: var(--blue);
  margin-bottom: 14px;
}
.section-eyebrow::before {
  content: ''; width: 20px; height: 2px;
  background: var(--blue); border-radius: 2px;
}

.section-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(28px, 4vw, 46px);
  font-weight: 900; line-height: 1.12;
  color: var(--ink);
  margin-bottom: 16px;
}
.section-title em { font-style: normal; color: var(--blue); }

.section-sub {
  font-size: 16px; color: var(--slate);
  line-height: 1.7; max-width: 540px;
}

/* ─── PROBLEM QUOTE ─── */
.quote-strip {
  background: var(--ink);
  color: #fff;
  padding: 64px 40px;
  text-align: center;
  position: relative; overflow: hidden;
}
.quote-strip::before {
  content: '"';
  position: absolute;
  font-family: 'Playfair Display', serif;
  font-size: 320px; font-weight: 900;
  color: rgba(255,255,255,0.03);
  top: -60px; left: 20px;
  line-height: 1;
  pointer-events: none;
}
.quote-text {
  font-family: 'Playfair Display', serif;
  font-size: clamp(18px, 3vw, 28px);
  font-weight: 700;
  color: #fff;
  max-width: 700px;
  margin: 0 auto 14px;
  line-height: 1.4;
  position: relative; z-index: 1;
}
.quote-text em { color: var(--accent); font-style: normal; }
.quote-attr {
  font-size: 13px; color: rgba(255,255,255,0.45);
  font-weight: 500; letter-spacing: .06em;
}

/* ─── BENEFITS ─── */
.benefits-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-top: 50px;
}
@media(max-width:760px){ .benefits-grid { grid-template-columns: 1fr 1fr; } }
@media(max-width:480px){ .benefits-grid { grid-template-columns: 1fr; } }

.benefit-card {
  background: var(--white);
  border: 1px solid var(--line);
  border-radius: 20px;
  padding: 28px 24px;
  transition: transform .3s, box-shadow .3s, border-color .3s;
  position: relative; overflow: hidden;
  box-shadow: 0 2px 8px rgba(12,18,32,0.04);
}
.benefit-card:hover {
  transform: translateY(-5px);
  border-color: rgba(27,79,216,0.20);
  box-shadow: 0 20px 48px rgba(27,79,216,0.10);
}
.benefit-num {
  font-family: 'Playfair Display', serif;
  font-size: 11px; font-weight: 700;
  color: rgba(27,79,216,0.25);
  letter-spacing: .1em;
  margin-bottom: 16px;
}
.benefit-icon-wrap {
  width: 48px; height: 48px;
  background: linear-gradient(135deg, rgba(27,79,216,0.08), rgba(46,128,255,0.05));
  border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 22px;
  margin-bottom: 16px;
  border: 1px solid rgba(27,79,216,0.10);
}
.benefit-title { font-size: 15px; font-weight: 700; color: var(--ink); margin-bottom: 8px; }
.benefit-desc { font-size: 13px; color: var(--muted); line-height: 1.65; }

/* ─── STATS BAND ─── */
.stats-band {
  background: linear-gradient(135deg, var(--ink2) 0%, var(--ink) 100%);
  padding: 64px 40px;
  position: relative; overflow: hidden;
}
.stats-band::after {
  content:'';
  position:absolute;
  width:600px; height:600px;
  border-radius:50%;
  background: radial-gradient(circle, rgba(27,79,216,0.20) 0%, transparent 70%);
  top:-200px; right:-100px;
  pointer-events:none;
}
.stats-inner {
  max-width: 1100px; margin: 0 auto;
  display: grid; grid-template-columns: repeat(3,1fr);
  gap: 40px; text-align: center;
  position: relative; z-index: 1;
}
@media(max-width:600px){ .stats-inner { grid-template-columns:1fr; } }
.stat-val {
  font-family: 'Playfair Display', serif;
  font-size: clamp(40px,7vw,60px); font-weight: 900;
  color: var(--accent);
  line-height: 1;
}
.stat-lbl { font-size: 13px; color: rgba(255,255,255,0.5); margin-top: 8px; font-weight: 500; }

/* ─── STEPS ─── */
.steps-wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 0;
  margin-top: 50px;
  position: relative;
}
@media(max-width:700px){ .steps-wrapper { grid-template-columns:1fr; } }

.steps-wrapper::before {
  content:'';
  position:absolute;
  top: 28px; left: calc(16.66% + 20px); right: calc(16.66% + 20px);
  height: 1px;
  background: linear-gradient(90deg, var(--blue), var(--blue2));
  opacity: .3;
}
@media(max-width:700px){ .steps-wrapper::before { display:none; } }

.step-item {
  text-align: center;
  padding: 0 20px;
  position: relative;
}
.step-num {
  width: 56px; height: 56px;
  border-radius: 50%;
  background: var(--white);
  border: 2px solid var(--blue);
  display: flex; align-items: center; justify-content: center;
  font-family: 'Playfair Display', serif;
  font-size: 22px; font-weight: 900; color: var(--blue);
  margin: 0 auto 20px;
  position: relative; z-index: 1;
  box-shadow: 0 0 0 6px var(--bg);
  transition: background .3s, color .3s;
}
.step-item:hover .step-num { background: var(--blue); color: #fff; }
.step-title { font-size: 16px; font-weight: 700; color: var(--ink); margin-bottom: 8px; }
.step-desc { font-size: 13px; color: var(--muted); line-height: 1.65; }

/* ─── FORM SECTION ─── */
.form-section {
  background: var(--white);
  border-top: 1px solid var(--line);
  border-bottom: 1px solid var(--line);
}
.form-inner {
  max-width: 780px;
  margin: 0 auto;
  padding: 90px 40px;
}
@media(max-width:600px){ .form-inner { padding: 60px 20px; } }

.form-header { text-align: center; margin-bottom: 48px; }

/* Progress */
.progress-bar {
  display: flex; align-items: center; justify-content: center;
  gap: 0; margin-bottom: 44px;
}
.pb-step {
  display: flex; flex-direction: column; align-items: center; gap: 8px;
}
.pb-dot {
  width: 40px; height: 40px;
  border-radius: 50%;
  background: var(--bg);
  border: 2px solid var(--line);
  display: flex; align-items: center; justify-content: center;
  font-family: 'Playfair Display', serif;
  font-weight: 700; font-size: 15px;
  color: var(--muted);
  transition: all .3s;
  position: relative; z-index: 1;
}
.pb-dot.done  { background: var(--blue); border-color: var(--blue); color: #fff; }
.pb-dot.active {
  background: var(--blue); border-color: var(--blue); color: #fff;
  box-shadow: 0 0 0 6px rgba(27,79,216,0.12);
}
.pb-label { font-size: 10px; font-weight: 600; color: var(--muted); letter-spacing: .08em; text-transform: uppercase; }
.pb-label.active { color: var(--blue); }
.pb-line {
  width: 80px; height: 2px;
  background: var(--line);
  margin-bottom: 18px;
  transition: background .3s;
  flex-shrink: 0;
}
.pb-line.done { background: var(--blue); }
@media(max-width:480px){ .pb-line { width: 36px; } }

/* Step panels */
.fstep { display: none; animation: fadeIn .35s ease; }
.fstep.active { display: block; }
@keyframes fadeIn { from { opacity:0; transform:translateY(8px); } to { opacity:1; transform:translateY(0); } }

.fstep-title {
  font-family: 'Playfair Display', serif;
  font-size: 22px; font-weight: 900;
  color: var(--ink); margin-bottom: 6px;
}
.fstep-sub { font-size: 14px; color: var(--muted); margin-bottom: 32px; }

/* Fields */
.field { margin-bottom: 22px; }
.field-label {
  display: block;
  font-size: 12px; font-weight: 700;
  letter-spacing: .06em;
  text-transform: uppercase;
  color: var(--slate);
  margin-bottom: 8px;
}
.field-label sup { color: var(--red); }
.field-input {
  width: 100%;
  padding: 13px 18px;
  border: 1.5px solid var(--line);
  border-radius: 12px;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 15px; color: var(--ink);
  background: #FAFCFF;
  outline: none;
  transition: border-color .2s, box-shadow .2s, background .2s;
}
.field-input::placeholder { color: #B0BEC5; }
.field-input:focus {
  border-color: var(--blue);
  background: #fff;
  box-shadow: 0 0 0 4px rgba(27,79,216,0.08);
}
.field-input.is-err { border-color: var(--red); background: #FFF8F8; }
.field-row { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; }
@media(max-width:520px){ .field-row { grid-template-columns:1fr; } }
.err-txt { font-size: 12px; color: var(--red); margin-top: 5px; display: none; }
.err-txt.show { display: block; }

/* Doc toggle */
.doc-toggle { display: flex; gap: 10px; }
.dtog {
  flex:1; padding: 11px 8px;
  border: 1.5px solid var(--line);
  border-radius: 10px;
  background: #FAFCFF;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 13px; font-weight: 600; color: var(--muted);
  cursor: pointer; text-align: center;
  transition: all .2s;
}
.dtog.on { border-color: var(--blue); background: rgba(27,79,216,0.05); color: var(--blue); }

/* Budget cards */
.budget-grid {
  display: grid; grid-template-columns: repeat(4,1fr); gap: 12px;
  margin-bottom: 6px;
}
@media(max-width:500px){ .budget-grid { grid-template-columns: 1fr 1fr; } }
.bcard {
  border: 1.5px solid var(--line);
  border-radius: 14px; padding: 16px 10px;
  text-align: center; cursor: pointer;
  background: #FAFCFF;
  transition: all .2s;
}
.bcard:hover { border-color: var(--blue2); background: #F0F7FF; }
.bcard.on { border-color: var(--blue); background: rgba(27,79,216,0.06); box-shadow: 0 4px 16px rgba(27,79,216,0.10); }
.bcard-ico { font-size: 24px; margin-bottom: 6px; }
.bcard-val { font-size: 12px; font-weight: 700; color: var(--ink); }
.bcard-sub { font-size: 10px; color: var(--muted); margin-top: 2px; }
.bcard.on .bcard-val { color: var(--blue); }

/* Vehicle grid */
.vgrid {
  display: grid; grid-template-columns: repeat(3,1fr); gap: 12px;
  margin-bottom: 6px;
}
@media(max-width:480px){ .vgrid { grid-template-columns: repeat(2,1fr); } }
.vcard {
  border: 1.5px solid var(--line);
  border-radius: 14px; padding: 18px 10px;
  text-align: center; cursor: pointer;
  background: #FAFCFF;
  transition: all .2s;
}
.vcard:hover { border-color: var(--blue2); background: #F0F7FF; }
.vcard.on { border-color: var(--blue); background: rgba(27,79,216,0.06); box-shadow: 0 4px 16px rgba(27,79,216,0.10); }
.vcard-ico { font-size: 30px; margin-bottom: 8px; }
.vcard-lbl { font-size: 13px; font-weight: 700; color: var(--ink); }
.vcard.on .vcard-lbl { color: var(--blue); }

/* Condition */
.cond-toggle { display: flex; gap: 10px; }
.ctog {
  flex:1; padding: 12px 8px;
  border: 1.5px solid var(--line);
  border-radius: 10px;
  background: #FAFCFF;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 13px; font-weight: 600; color: var(--muted);
  cursor: pointer; text-align: center;
  transition: all .2s;
}
.ctog.on { border-color: var(--blue); background: rgba(27,79,216,0.05); color: var(--blue); }

/* Nav */
.form-nav {
  display: flex; gap: 12px; justify-content: flex-end;
  margin-top: 32px;
  padding-top: 24px;
  border-top: 1px solid var(--line);
}
.fbtn-back {
  padding: 12px 26px;
  border: 1.5px solid var(--line);
  border-radius: 12px;
  background: transparent;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 14px; font-weight: 600; color: var(--slate);
  cursor: pointer; transition: all .2s;
}
.fbtn-back:hover { border-color: var(--blue); color: var(--blue); }
.fbtn-next {
  padding: 13px 30px;
  border: none; border-radius: 12px;
  background: linear-gradient(135deg, var(--blue), var(--blue2));
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 14px; font-weight: 700; color: #fff;
  cursor: pointer;
  box-shadow: 0 4px 18px rgba(27,79,216,0.28);
  transition: transform .2s, box-shadow .2s;
}
.fbtn-next:hover { transform: translateY(-2px); box-shadow: 0 8px 28px rgba(27,79,216,0.38); }
.fbtn-send {
  padding: 13px 30px;
  border: none; border-radius: 12px;
  background: linear-gradient(135deg, var(--green2), #128C7E);
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 14px; font-weight: 700; color: #fff;
  cursor: pointer; display: flex; align-items: center; gap: 8px;
  box-shadow: 0 4px 18px rgba(37,211,102,0.30);
  transition: transform .2s, box-shadow .2s;
}
.fbtn-send:hover { transform: translateY(-2px); box-shadow: 0 8px 28px rgba(37,211,102,0.42); }

/* Success */
.form-success { display: none; text-align: center; padding: 40px 0; }
.succ-ring {
  width: 88px; height: 88px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--green2), #128C7E);
  display: flex; align-items: center; justify-content: center;
  font-size: 38px; margin: 0 auto 24px;
  box-shadow: 0 8px 32px rgba(37,211,102,0.28);
  animation: popIn .5s cubic-bezier(.26,1.8,.52,1) both;
}
@keyframes popIn { from { transform: scale(0); opacity:0; } }
.succ-title {
  font-family: 'Playfair Display', serif;
  font-size: 28px; font-weight: 900; color: var(--ink); margin-bottom: 12px;
}
.succ-sub { font-size: 15px; color: var(--muted); max-width: 400px; margin: 0 auto 30px; line-height: 1.65; }

/* ─── CTA FINAL ─── */
.cta-final {
  background: linear-gradient(135deg, var(--ink) 0%, #142240 100%);
  padding: 100px 40px;
  text-align: center;
  position: relative; overflow: hidden;
}
.cta-final::before {
  content:'';
  position:absolute;
  width:700px; height:700px;
  border-radius:50%;
  background: radial-gradient(circle, rgba(27,79,216,0.20) 0%, transparent 70%);
  top:-200px; left:50%; transform:translateX(-50%);
  pointer-events:none;
}
.cta-final-inner { position:relative; z-index:1; max-width:620px; margin:0 auto; }
.cta-final-eyebrow {
  display:inline-block;
  font-size:11px; font-weight:700; letter-spacing:.14em;
  text-transform:uppercase; color:var(--accent);
  margin-bottom:16px;
}
.cta-final-title {
  font-family:'Playfair Display', serif;
  font-size:clamp(28px,5vw,52px); font-weight:900;
  color:#fff; line-height:1.1; margin-bottom:18px;
}
.cta-final-sub { font-size:16px; color:rgba(255,255,255,.55); line-height:1.7; margin-bottom:40px; }
.cta-final-btns { display:flex; gap:14px; justify-content:center; flex-wrap:wrap; }

/* ─── FOOTER ─── */
footer {
  background: #080E1A;
  padding: 40px;
  display: flex; align-items: center; justify-content: space-between;
  flex-wrap: wrap; gap: 16px;
}
.ft-logo {
  font-family: 'Playfair Display', serif;
  font-size: 20px; font-weight: 900; color: #fff;
}
.ft-logo em { color: var(--accent); font-style: normal; }
.ft-info { font-size: 12px; color: rgba(255,255,255,.35); line-height: 1.7; }
.ft-info a { color: var(--green2); text-decoration: none; }
.ft-info strong { color: rgba(255,255,255,.6); }

/* ─── REVEAL ─── */
.reveal { opacity:0; transform:translateY(28px); transition: opacity .7s ease, transform .7s ease; }
.reveal.in { opacity:1; transform:translateY(0); }

@keyframes fadeUp {
  from { opacity:0; transform:translateY(22px); }
  to   { opacity:1; transform:translateY(0); }
}
</style>
</head>
<body>

<!-- TOPBAR -->
<nav class="topbar">
  <div class="topbar-logo">Ruta<em>Fondo</em></div>
  <a class="topbar-cta" href="https://wa.me/51940304372?text=Hola%20Alexandro%2C%20quiero%20informaci%C3%B3n%20sobre%20RutaFondo%20%F0%9F%9A%98" target="_blank">
    💬 Contáctame
  </a>
</nav>

<!-- HERO -->
<div class="hero-bg"></div>
<section class="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">🚘 Fondos de Ahorro Grupal · Maqui+</div>
    <h1 class="hero-title">
      Tu vehículo,<br>tu <span class="accent-word">patrimonio</span>,<br>tu meta.
    </h1>
    <p class="hero-desc">
      No esperes el momento perfecto — el mejor momento es cuando decides actuar. En RutaFondo te acompañamos con un plan real, accesible y diseñado para ti.
    </p>
    <div class="hero-actions">
      <a class="btn-wsp" href="https://wa.me/51940304372?text=Hola%20Alexandro%2C%20quiero%20informaci%C3%B3n%20sobre%20RutaFondo%20%F0%9F%9A%98" target="_blank">
        💬 Hablar con Alexandro
      </a>
      <a class="btn-outline" href="#formulario">Ver mi plan →</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="hero-card">
      <div class="hc-tag">TU ASESOR DE CONFIANZA</div>
      <div class="hc-advisor">
        <div class="hc-avatar">AM</div>
        <div>
          <div class="hc-name">Alexandro Morillas</div>
          <div class="hc-role">Asesor de Ventas · Maqui+</div>
        </div>
      </div>
      <div class="hc-stats">
        <div class="hc-stat">
          <div class="hc-stat-val">100%</div>
          <div class="hc-stat-lbl">Asesoría personalizada</div>
        </div>
        <div class="hc-stat">
          <div class="hc-stat-val">0</div>
          <div class="hc-stat-lbl">Pretextos para empezar</div>
        </div>
        <div class="hc-stat">
          <div class="hc-stat-val">+Rápido</div>
          <div class="hc-stat-lbl">Con el poder del grupo</div>
        </div>
        <div class="hc-stat">
          <div class="hc-stat-val">24h</div>
          <div class="hc-stat-lbl">Respuesta garantizada</div>
        </div>
      </div>
      <div class="hc-badges">
        <span class="hc-badge">✅ Respaldo Maqui+</span>
        <span class="hc-badge">🛡️ Trato directo</span>
        <span class="hc-badge">📋 Plan a tu medida</span>
      </div>
    </div>
  </div>
</section>

<!-- QUOTE STRIP -->
<div class="quote-strip reveal">
  <div class="quote-text">
    "Miles de personas siguen esperando el momento perfecto.<br>
    Nuestros asociados <em>ya están en camino.</em>"
  </div>
  <div class="quote-attr">— Alexandro Morillas · Asesor RutaFondo</div>
</div>

<!-- BENEFICIOS -->
<section class="section reveal">
  <div class="section-eyebrow">¿Por qué RutaFondo?</div>
  <h2 class="section-title">Todo lo que necesitas<br>en <em>un solo lugar</em></h2>
  <p class="section-sub">Desde tu primer auto hasta tu patrimonio — te acompañamos en cada paso con honestidad y experiencia real.</p>

  <div class="benefits-grid">
    <div class="benefit-card">
      <div class="benefit-num">01</div>
      <div class="benefit-icon-wrap">🚗</div>
      <div class="benefit-title">Auto a tu alcance</div>
      <div class="benefit-desc">Nuevo o seminuevo. Encontramos la opción ideal para tu presupuesto y estilo de vida.</div>
    </div>
    <div class="benefit-card">
      <div class="benefit-num">02</div>
      <div class="benefit-icon-wrap">🏠</div>
      <div class="benefit-title">Vivienda y patrimonio</div>
      <div class="benefit-desc">Planificación inteligente para que tu dinero trabaje por ti y construyas futuro sólido.</div>
    </div>
    <div class="benefit-card">
      <div class="benefit-num">03</div>
      <div class="benefit-icon-wrap">💰</div>
      <div class="benefit-title">Cuotas accesibles</div>
      <div class="benefit-desc">Planes que se adaptan a tu bolsillo. Sin apreturas, sin estrés, con total orden.</div>
    </div>
    <div class="benefit-card">
      <div class="benefit-num">04</div>
      <div class="benefit-icon-wrap">🤝</div>
      <div class="benefit-title">Asesoría personalizada</div>
      <div class="benefit-desc">Alexandro te acompaña desde el primer día. Tu situación es única y merece atención real.</div>
    </div>
    <div class="benefit-card">
      <div class="benefit-num">05</div>
      <div class="benefit-icon-wrap">👥</div>
      <div class="benefit-title">Fondos grupales</div>
      <div class="benefit-desc">Ahorra junto a otros y alcanza tus metas más rápido. La fuerza colectiva te impulsa.</div>
    </div>
    <div class="benefit-card">
      <div class="benefit-num">06</div>
      <div class="benefit-icon-wrap">📊</div>
      <div class="benefit-title">Planificación vehicular</div>
      <div class="benefit-desc">Programas diseñados para que tengas claridad total en cada etapa de tu ruta financiera.</div>
    </div>
  </div>
</section>

<!-- STATS BAND -->
<div class="stats-band reveal">
  <div class="stats-inner">
    <div>
      <div class="stat-val">100%</div>
      <div class="stat-lbl">Asesoría personalizada desde el día uno</div>
    </div>
    <div>
      <div class="stat-val">+Rápido</div>
      <div class="stat-lbl">Alcanza tus metas con el poder del grupo</div>
    </div>
    <div>
      <div class="stat-val">0</div>
      <div class="stat-lbl">Pretextos — planes reales para situaciones reales</div>
    </div>
  </div>
</div>

<!-- STEPS -->
<section class="section reveal">
  <div style="text-align:center; margin-bottom:0;">
    <div class="section-eyebrow" style="justify-content:center;">¿Cómo funciona?</div>
    <h2 class="section-title">3 pasos para <em>comenzar tu ruta</em></h2>
  </div>
  <div class="steps-wrapper">
    <div class="step-item">
      <div class="step-num">1</div>
      <div class="step-title">Escríbele a Alexandro</div>
      <div class="step-desc">Cuéntanos tu meta — auto, vivienda o ahorro. Sin compromiso ni presión. Solo una conversación honesta.</div>
    </div>
    <div class="step-item">
      <div class="step-num">2</div>
      <div class="step-title">Trazamos tu plan</div>
      <div class="step-desc">Diseñamos juntos un programa a tu medida con cuotas accesibles, metas claras y pasos concretos.</div>
    </div>
    <div class="step-item">
      <div class="step-num">3</div>
      <div class="step-title">Avanzas en tu ruta</div>
      <div class="step-desc">Te acompañamos en cada paso hasta que llegues exactamente donde siempre quisiste estar.</div>
    </div>
  </div>
</section>

<!-- FORMULARIO -->
<div class="form-section" id="formulario">
  <div class="form-inner">
    <div class="form-header reveal">
      <div class="section-eyebrow" style="justify-content:center; display:inline-flex;">Comienza aquí</div>
      <h2 class="section-title">Cuéntanos sobre <em>tu meta</em></h2>
      <p class="section-sub" style="margin:0 auto; text-align:center;">
        Completa este formulario en 3 pasos y Alexandro te contactará con un plan personalizado — sin costo ni compromiso.
      </p>
    </div>

    <!-- Progress -->
    <div class="progress-bar" id="progressBar">
      <div class="pb-step">
        <div class="pb-dot active" id="pd1">1</div>
        <div class="pb-label active" id="pl1">Datos</div>
      </div>
      <div class="pb-line" id="pline1"></div>
      <div class="pb-step">
        <div class="pb-dot" id="pd2">2</div>
        <div class="pb-label" id="pl2">Inversión</div>
      </div>
      <div class="pb-line" id="pline2"></div>
      <div class="pb-step">
        <div class="pb-dot" id="pd3">3</div>
        <div class="pb-label" id="pl3">Vehículo</div>
      </div>
    </div>

    <!-- STEP 1 -->
    <div class="fstep active" id="fstep1">
      <div class="fstep-title">👤 Tus datos de contacto</div>
      <div class="fstep-sub">Para que Alexandro pueda comunicarse contigo de forma directa.</div>

      <div class="field-row">
        <div class="field">
          <label class="field-label">Nombre completo <sup>*</sup></label>
          <input class="field-input" id="f_nombre" type="text" placeholder="Ej. Juan Pérez Quispe">
          <div class="err-txt" id="e_nombre">Por favor ingresa tu nombre completo.</div>
        </div>
        <div class="field">
          <label class="field-label">Teléfono / WhatsApp <sup>*</sup></label>
          <input class="field-input" id="f_tel" type="tel" placeholder="Ej. 987 654 321">
          <div class="err-txt" id="e_tel">Ingresa un número válido.</div>
        </div>
      </div>

      <div class="field">
        <label class="field-label">Correo electrónico <sup>*</sup></label>
        <input class="field-input" id="f_email" type="email" placeholder="tucorreo@gmail.com">
        <div class="err-txt" id="e_email">Ingresa un correo válido.</div>
      </div>

      <div class="field">
        <label class="field-label" style="margin-bottom:10px;">Tipo de documento <sup>*</sup></label>
        <div class="doc-toggle" style="margin-bottom:12px;">
          <button class="dtog on" onclick="setDoc(this,'DNI')">🪪 DNI</button>
          <button class="dtog" onclick="setDoc(this,'CE')">📄 Carnet de Extranjería</button>
          <button class="dtog" onclick="setDoc(this,'Otro')">📋 Otro</button>
        </div>
        <input class="field-input" id="f_doc" type="text" placeholder="Número de documento">
        <div class="err-txt" id="e_doc">Ingresa tu número de documento.</div>
      </div>

      <div class="form-nav">
        <button class="fbtn-next" onclick="goTo(2)">Siguiente →</button>
      </div>
    </div>

    <!-- STEP 2 -->
    <div class="fstep" id="fstep2">
      <div class="fstep-title">💰 Tu capacidad de inversión</div>
      <div class="fstep-sub">Esto nos ayuda a identificar el plan ideal para ti sin forzar tu presupuesto.</div>

      <div class="field">
        <label class="field-label">Inversión mensual disponible <sup>*</sup></label>
        <div class="budget-grid">
          <div class="bcard" onclick="setBudget(this,'menos200')">
            <div class="bcard-ico">🌱</div>
            <div class="bcard-val">Hasta S/200</div>
            <div class="bcard-sub">Inicio tranquilo</div>
          </div>
          <div class="bcard" onclick="setBudget(this,'200-400')">
            <div class="bcard-ico">📈</div>
            <div class="bcard-val">S/200 – S/400</div>
            <div class="bcard-sub">Crecimiento estable</div>
          </div>
          <div class="bcard" onclick="setBudget(this,'400-700')">
            <div class="bcard-ico">🚀</div>
            <div class="bcard-val">S/400 – S/700</div>
            <div class="bcard-sub">Avance acelerado</div>
          </div>
          <div class="bcard" onclick="setBudget(this,'mas700')">
            <div class="bcard-ico">💎</div>
            <div class="bcard-val">Más de S/700</div>
            <div class="bcard-sub">Meta premium</div>
          </div>
        </div>
        <div class="err-txt" id="e_budget">Selecciona una opción de inversión.</div>
      </div>

      <div class="field">
        <label class="field-label">¿Tienes ahorro inicial disponible?</label>
        <select class="field-input" id="f_ahorro">
          <option value="">— Selecciona una opción —</option>
          <option value="No por ahora">No por ahora</option>
          <option value="Menos de S/1,000">Menos de S/1,000</option>
          <option value="S/1,000 – S/3,000">S/1,000 – S/3,000</option>
          <option value="S/3,000 – S/6,000">S/3,000 – S/6,000</option>
          <option value="Más de S/6,000">Más de S/6,000</option>
        </select>
      </div>

      <div class="form-nav">
        <button class="fbtn-back" onclick="goTo(1)">← Atrás</button>
        <button class="fbtn-next" onclick="goTo(3)">Siguiente →</button>
      </div>
    </div>

    <!-- STEP 3 -->
    <div class="fstep" id="fstep3">
      <div class="fstep-title">🚗 Tu vehículo ideal</div>
      <div class="fstep-sub">Cuéntanos qué tipo de vehículo tienes en mente.</div>

      <div class="field">
        <label class="field-label">Tipo de vehículo <sup>*</sup></label>
        <div class="vgrid">
          <div class="vcard" onclick="setVehicle(this,'Sedán')">
            <div class="vcard-ico">🚗</div>
            <div class="vcard-lbl">Sedán</div>
          </div>
          <div class="vcard" onclick="setVehicle(this,'SUV / 4x4')">
            <div class="vcard-ico">🚙</div>
            <div class="vcard-lbl">SUV / 4x4</div>
          </div>
          <div class="vcard" onclick="setVehicle(this,'Pickup')">
            <div class="vcard-ico">🛻</div>
            <div class="vcard-lbl">Pickup</div>
          </div>
          <div class="vcard" onclick="setVehicle(this,'Van / Furgón')">
            <div class="vcard-ico">🚐</div>
            <div class="vcard-lbl">Van / Furgón</div>
          </div>
          <div class="vcard" onclick="setVehicle(this,'Moto')">
            <div class="vcard-ico">🏍️</div>
            <div class="vcard-lbl">Moto</div>
          </div>
          <div class="vcard" onclick="setVehicle(this,'Otro')">
            <div class="vcard-ico">🚌</div>
            <div class="vcard-lbl">Otro</div>
          </div>
        </div>
        <div class="err-txt" id="e_vehicle">Selecciona el tipo de vehículo.</div>
      </div>

      <div class="field">
        <label class="field-label">¿Nuevo o seminuevo?</label>
        <div class="cond-toggle">
          <button class="ctog on" onclick="setCond(this,'Nuevo')">✨ Nuevo</button>
          <button class="ctog" onclick="setCond(this,'Seminuevo')">🔄 Seminuevo</button>
          <button class="ctog" onclick="setCond(this,'Cualquiera')">💡 Cualquiera</button>
        </div>
      </div>

      <div class="field">
        <label class="field-label">Marca o modelo de interés</label>
        <input class="field-input" id="f_modelo" type="text" placeholder="Ej. Toyota Hilux, Hyundai Tucson, Kia Sportage...">
      </div>

      <div class="field">
        <label class="field-label">¿Algo más que quieras contarnos?</label>
        <textarea class="field-input" id="f_notas" rows="3" placeholder="Tu consulta, dudas o información adicional..." style="resize:vertical; min-height:90px;"></textarea>
      </div>

      <div class="form-nav">
        <button class="fbtn-back" onclick="goTo(2)">← Atrás</button>
        <button class="fbtn-send" onclick="enviar()">💬 Enviar a Alexandro por WhatsApp</button>
      </div>
    </div>

    <!-- SUCCESS -->
    <div class="form-success" id="formOk">
      <div class="succ-ring">✅</div>
      <div class="succ-title">¡Perfecto, ya estás en camino!</div>
      <div class="succ-sub">Tu información fue enviada a Alexandro. Te contactará a la brevedad para armar tu plan personalizado.</div>
      <a class="btn-wsp" href="https://wa.me/51940304372" target="_blank" style="display:inline-flex; margin:0 auto;">
        💬 Escribir directamente por WhatsApp
      </a>
    </div>

  </div>
</div>

<!-- CTA FINAL -->
<div class="cta-final reveal">
  <div class="cta-final-inner">
    <div class="cta-final-eyebrow">¿Listo para empezar?</div>
    <h2 class="cta-final-title">El mejor momento<br>es ahora.</h2>
    <p class="cta-final-sub">Tu próximo vehículo, tu patrimonio, tu tranquilidad financiera — todo empieza con una decisión. Alexandro y el equipo RutaFondo hacen el resto.</p>
    <div class="cta-final-btns">
      <a class="btn-wsp" href="https://wa.me/51940304372?text=Hola%20Alexandro%2C%20quiero%20informaci%C3%B3n%20sobre%20RutaFondo%20%F0%9F%9A%98" target="_blank">
        💬 Escribir a Alexandro
      </a>
      <a class="btn-outline" href="#formulario" style="color:rgba(255,255,255,.7); border-color:rgba(255,255,255,.2);">
        📋 Llenar formulario
      </a>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="ft-logo">Ruta<em>Fondo</em></div>
  <div class="ft-info">
    <strong>Alexandro Morillas</strong> · Asesor de Ventas · Maqui+<br>
    📱 <a href="https://wa.me/51940304372">+51 940 304 372</a> · Fondos de Ahorro Grupal · Asesoría Vehicular y Patrimonial
  </div>
</footer>

<script>
// ── Scroll reveal ──
const obs = new IntersectionObserver(entries => {
  entries.forEach((e,i) => {
    if (e.isIntersecting) setTimeout(() => e.target.classList.add('in'), i*70);
  });
}, { threshold: 0.08 });
document.querySelectorAll('.reveal').forEach(r => obs.observe(r));

// ── Form state ──
let curStep = 1;
let doc_type = 'DNI', budget = '', vehicle = '', cond = 'Nuevo';

function setDoc(btn, v) {
  document.querySelectorAll('.dtog').forEach(b => b.classList.remove('on'));
  btn.classList.add('on'); doc_type = v;
}
function setBudget(card, v) {
  document.querySelectorAll('.bcard').forEach(c => c.classList.remove('on'));
  card.classList.add('on'); budget = v;
  document.getElementById('e_budget').classList.remove('show');
}
function setVehicle(card, v) {
  document.querySelectorAll('.vcard').forEach(c => c.classList.remove('on'));
  card.classList.add('on'); vehicle = v;
  document.getElementById('e_vehicle').classList.remove('show');
}
function setCond(btn, v) {
  document.querySelectorAll('.ctog').forEach(b => b.classList.remove('on'));
  btn.classList.add('on'); cond = v;
}

function updateProgress(step) {
  for (let i = 1; i <= 3; i++) {
    const dot = document.getElementById('pd'+i);
    const lbl = document.getElementById('pl'+i);
    dot.classList.remove('active','done');
    lbl.classList.remove('active');
    if (i < step)  { dot.classList.add('done'); dot.innerHTML = '✓'; }
    if (i === step){ dot.classList.add('active'); dot.innerHTML = i; lbl.classList.add('active'); }
    if (i > step)  { dot.innerHTML = i; }
  }
  for (let i = 1; i <= 2; i++) {
    document.getElementById('pline'+i).classList.toggle('done', i < step);
  }
}

function err(id, fid, msg) {
  const e = document.getElementById(id);
  e.textContent = msg; e.classList.add('show');
  if (fid) document.getElementById(fid).classList.add('is-err');
  return false;
}
function clrErr(id, fid) {
  document.getElementById(id).classList.remove('show');
  if (fid) document.getElementById(fid).classList.remove('is-err');
}

function validate1() {
  let ok = true;
  const n = document.getElementById('f_nombre').value.trim();
  const t = document.getElementById('f_tel').value.trim();
  const em = document.getElementById('f_email').value.trim();
  const d = document.getElementById('f_doc').value.trim();
  if (n.length < 3) { err('e_nombre','f_nombre','Ingresa tu nombre completo.'); ok=false; } else clrErr('e_nombre','f_nombre');
  if (t.length < 7) { err('e_tel','f_tel','Ingresa un número de teléfono válido.'); ok=false; } else clrErr('e_tel','f_tel');
  if (!em.includes('@') || !em.includes('.')) { err('e_email','f_email','Ingresa un correo electrónico válido.'); ok=false; } else clrErr('e_email','f_email');
  if (d.length < 6) { err('e_doc','f_doc','Ingresa tu número de documento.'); ok=false; } else clrErr('e_doc','f_doc');
  return ok;
}
function validate2() {
  if (!budget) { document.getElementById('e_budget').classList.add('show'); return false; }
  return true;
}
function validate3() {
  if (!vehicle) { document.getElementById('e_vehicle').classList.add('show'); return false; }
  return true;
}

function goTo(n) {
  if (n > curStep) {
    if (curStep === 1 && !validate1()) return;
    if (curStep === 2 && !validate2()) return;
  }
  document.getElementById('fstep'+curStep).classList.remove('active');
  document.getElementById('fstep'+n).classList.add('active');
  curStep = n;
  updateProgress(n);
  document.getElementById('formulario').scrollIntoView({ behavior:'smooth', block:'start' });
}

const bLabel = { 'menos200':'Hasta S/200', '200-400':'S/200 – S/400', '400-700':'S/400 – S/700', 'mas700':'Más de S/700' };

function enviar() {
  if (!validate3()) return;
  const nombre = document.getElementById('f_nombre').value.trim();
  const tel    = document.getElementById('f_tel').value.trim();
  const email  = document.getElementById('f_email').value.trim();
  const docNum = document.getElementById('f_doc').value.trim();
  const ahorro = document.getElementById('f_ahorro').value || 'No indicado';
  const modelo = document.getElementById('f_modelo').value.trim() || 'No especificado';
  const notas  = document.getElementById('f_notas').value.trim() || 'Ninguna';

  const msg =
`🚘 *NUEVO LEAD — RutaFondo*

👤 *Nombre:* ${nombre}
📱 *Teléfono:* ${tel}
📧 *Correo:* ${email}
🪪 *${doc_type}:* ${docNum}

💰 *Inversión mensual:* ${bLabel[budget] || budget}
🏦 *Ahorro inicial:* ${ahorro}

🚗 *Vehículo:* ${vehicle} (${cond})
🔍 *Modelo de interés:* ${modelo}
📝 *Notas:* ${notas}`;

  window.open('https://wa.me/51940304372?text=' + encodeURIComponent(msg), '_blank');

  document.querySelectorAll('.fstep').forEach(s => s.style.display='none');
  document.getElementById('progressBar').style.display='none';
  document.getElementById('formOk').style.display='block';
}
</script>
</body>
</html>
