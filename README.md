<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HealthPlaced – Healthcare Internship & Placement Services</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --ink: #0a0f1a;
  --ink2: #141c2e;
  --teal: #0d9488;
  --teal2: #14b8a6;
  --teal3: #99f6e4;
  --gold: #d97706;
  --gold2: #fbbf24;
  --white: #ffffff;
  --slate: #f8fafc;
  --muted: #64748b;
  --border: rgba(13,148,136,0.15);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; font-size: 16px; }

body {
  font-family: 'Outfit', sans-serif;
  background: var(--white);
  color: var(--ink);
  overflow-x: hidden;
}

/* ── SCROLLBAR ── */
::-webkit-scrollbar { width: 5px; }
::-webkit-scrollbar-track { background: var(--ink); }
::-webkit-scrollbar-thumb { background: var(--teal); border-radius: 10px; }

/* ══════════════════════════════
   NAV
══════════════════════════════ */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 999;
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 60px;
  height: 72px;
  background: rgba(10,15,26,0.96);
  backdrop-filter: blur(20px) saturate(180%);
  border-bottom: 1px solid rgba(13,148,136,0.2);
  transition: all 0.3s;
}
.nav-logo { display: flex; align-items: center; gap: 12px; text-decoration: none; }
.nav-logo img { height: 38px; filter: brightness(1.1); }
.nav-logo span {
  font-family: 'Cormorant Garamond', serif;
  font-size: 22px; font-weight: 600; color: white;
  letter-spacing: 0.5px;
}
.nav-links { display: flex; align-items: center; gap: 36px; }
.nav-links a {
  color: rgba(255,255,255,0.65); text-decoration: none;
  font-size: 13.5px; font-weight: 500; letter-spacing: 0.3px;
  transition: color 0.2s; position: relative;
}
.nav-links a::after {
  content: ''; position: absolute; bottom: -4px; left: 0; right: 0;
  height: 1.5px; background: var(--teal2);
  transform: scaleX(0); transition: transform 0.25s;
  transform-origin: left;
}
.nav-links a:hover { color: var(--teal2); }
.nav-links a:hover::after { transform: scaleX(1); }
.nav-cta {
  background: var(--teal); color: white !important;
  padding: 10px 22px; border-radius: 50px;
  font-weight: 600; font-size: 13.5px;
  transition: all 0.25s !important;
  box-shadow: 0 0 0 0 rgba(13,148,136,0.4);
}
.nav-cta:hover {
  background: var(--teal2) !important;
  box-shadow: 0 0 0 6px rgba(13,148,136,0.15) !important;
  transform: none !important;
}
.nav-cta::after { display: none !important; }

/* ══════════════════════════════
   HERO
══════════════════════════════ */
.hero {
  min-height: 100vh;
  background: var(--ink);
  display: grid;
  grid-template-columns: 55% 45%;
  position: relative;
  overflow: hidden;
}

/* Geometric background decoration */
.hero-bg {
  position: absolute; inset: 0; z-index: 0;
  overflow: hidden;
}
.hero-bg::before {
  content: '';
  position: absolute;
  top: -200px; right: -100px;
  width: 700px; height: 700px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(13,148,136,0.18) 0%, transparent 65%);
}
.hero-bg::after {
  content: '';
  position: absolute;
  bottom: -150px; left: 20%;
  width: 500px; height: 500px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(13,148,136,0.08) 0%, transparent 70%);
}
.hero-grid-lines {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(13,148,136,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(13,148,136,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
}

.hero-left {
  padding: 160px 80px 80px;
  position: relative; z-index: 2;
  display: flex; flex-direction: column; justify-content: center;
}

.hero-eyebrow {
  display: inline-flex; align-items: center; gap: 10px;
  margin-bottom: 32px;
}
.eyebrow-line {
  width: 32px; height: 2px;
  background: linear-gradient(90deg, var(--teal), var(--teal2));
}
.eyebrow-text {
  font-size: 11px; font-weight: 600;
  letter-spacing: 3px; text-transform: uppercase;
  color: var(--teal2);
}

.hero-headline {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(52px, 5.5vw, 80px);
  line-height: 1.05;
  color: white;
  font-weight: 600;
  margin-bottom: 28px;
}
.hero-headline .accent {
  color: transparent;
  -webkit-text-stroke: 1.5px var(--teal2);
}
.hero-headline .teal { color: var(--teal2); }

.hero-desc {
  font-size: 17px; line-height: 1.8;
  color: rgba(255,255,255,0.55);
  max-width: 480px;
  margin-bottom: 48px;
  font-weight: 300;
}

.hero-actions { display: flex; gap: 16px; align-items: center; margin-bottom: 64px; }

.btn-hero-primary {
  display: inline-flex; align-items: center; gap: 10px;
  background: linear-gradient(135deg, var(--teal) 0%, var(--teal2) 100%);
  color: white; text-decoration: none;
  padding: 16px 36px; border-radius: 50px;
  font-weight: 600; font-size: 15px;
  transition: all 0.3s;
  box-shadow: 0 8px 32px rgba(13,148,136,0.35);
}
.btn-hero-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 16px 48px rgba(13,148,136,0.45);
}
.btn-hero-secondary {
  display: inline-flex; align-items: center; gap: 10px;
  color: rgba(255,255,255,0.7); text-decoration: none;
  padding: 16px 32px; border-radius: 50px;
  font-weight: 500; font-size: 15px;
  border: 1px solid rgba(255,255,255,0.15);
  transition: all 0.3s;
}
.btn-hero-secondary:hover {
  color: white;
  border-color: rgba(255,255,255,0.4);
  background: rgba(255,255,255,0.05);
}

.hero-metrics {
  display: flex; gap: 0;
  padding-top: 40px;
  border-top: 1px solid rgba(255,255,255,0.08);
}
.metric {
  flex: 1; padding: 0 32px 0 0;
  border-right: 1px solid rgba(255,255,255,0.08);
}
.metric:first-child { padding-left: 0; }
.metric:last-child { border-right: none; }
.metric-val {
  font-family: 'Cormorant Garamond', serif;
  font-size: 42px; font-weight: 700;
  color: white; line-height: 1;
  margin-bottom: 6px;
}
.metric-val span { color: var(--teal2); }
.metric-label {
  font-size: 12px; color: rgba(255,255,255,0.4);
  text-transform: uppercase; letter-spacing: 1.5px;
}

/* ── HERO RIGHT (Photo) ── */
.hero-right {
  position: relative; z-index: 2;
  display: flex; align-items: flex-end; justify-content: center;
  padding-bottom: 0;
  overflow: hidden;
}

.photo-container {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex; align-items: flex-end; justify-content: center;
}

/* Teal gradient wash behind photo */
.photo-container::before {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 85%;
  background: linear-gradient(175deg, transparent 0%, rgba(13,148,136,0.1) 40%, rgba(13,148,136,0.22) 100%);
  z-index: 1;
}

.photo-container::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0; height: 160px;
  background: linear-gradient(to top, var(--ink) 0%, transparent 100%);
  z-index: 3;
}

.hero-photo {
  position: relative; z-index: 2;
  width: 82%;
  max-width: 420px;
  height: auto;
  display: block;
  object-fit: cover;
  object-position: center top;
  /* Professional photo enhancement */
  filter: contrast(1.08) brightness(1.03) saturate(0.95);
  mask-image: linear-gradient(to bottom, black 60%, transparent 100%);
  -webkit-mask-image: linear-gradient(to bottom, black 60%, transparent 100%);
}

/* Decorative teal corner bracket */
.photo-bracket {
  position: absolute;
  top: 80px; right: 40px;
  width: 60px; height: 60px;
  border-top: 2px solid var(--teal2);
  border-right: 2px solid var(--teal2);
  opacity: 0.5;
  z-index: 4;
}
.photo-bracket-bl {
  position: absolute;
  bottom: 40px; left: 30px;
  width: 60px; height: 60px;
  border-bottom: 2px solid var(--teal2);
  border-left: 2px solid var(--teal2);
  opacity: 0.5;
  z-index: 4;
}

/* Name card floating */
.name-card {
  position: absolute;
  bottom: 48px; right: 32px;
  background: rgba(255,255,255,0.06);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(13,148,136,0.3);
  border-radius: 14px;
  padding: 18px 22px;
  z-index: 5;
}
.name-card h3 {
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px; font-weight: 600; color: white;
  margin-bottom: 3px;
}
.name-card p {
  font-size: 12px; color: var(--teal2);
  text-transform: uppercase; letter-spacing: 1.5px;
}
.name-card-dot {
  display: flex; align-items: center; gap: 6px; margin-top: 10px;
}
.dot { width: 7px; height: 7px; background: var(--teal2); border-radius: 50%; animation: pulse 2s infinite; }
@keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.4;transform:scale(1.4)} }
.name-card-dot span { font-size: 11px; color: rgba(255,255,255,0.4); }

/* ══════════════════════════════
   TRUST BAR
══════════════════════════════ */
.trust-bar {
  background: var(--teal);
  padding: 18px 60px;
  display: flex; align-items: center; justify-content: center;
  gap: 48px; flex-wrap: wrap;
}
.trust-item {
  display: flex; align-items: center; gap: 10px;
  font-size: 13.5px; font-weight: 600; color: white;
  letter-spacing: 0.3px;
}
.trust-item span:first-child { font-size: 18px; }

/* ══════════════════════════════
   SECTION COMMON
══════════════════════════════ */
.section { padding: 100px 80px; }
.section-inner { max-width: 1200px; margin: 0 auto; }

.chip {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(13,148,136,0.08);
  border: 1px solid rgba(13,148,136,0.2);
  border-radius: 50px;
  padding: 6px 16px; margin-bottom: 20px;
  font-size: 12px; font-weight: 600;
  color: var(--teal); text-transform: uppercase; letter-spacing: 1.5px;
}

.section-h {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(34px, 4vw, 54px);
  font-weight: 600; color: var(--ink);
  line-height: 1.15; margin-bottom: 16px;
}
.section-h .teal { color: var(--teal); }

.section-p {
  font-size: 17px; color: var(--muted);
  line-height: 1.75; max-width: 560px;
  font-weight: 300;
}

/* ══════════════════════════════
   SERVICES
══════════════════════════════ */
.services-section { background: var(--slate); }

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 56px;
}

.service-card {
  background: white;
  border-radius: 20px;
  padding: 36px 32px;
  border: 1px solid rgba(0,0,0,0.06);
  position: relative; overflow: hidden;
  transition: all 0.35s;
  cursor: default;
}
.service-card::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(13,148,136,0.04) 0%, transparent 60%);
  opacity: 0; transition: opacity 0.35s;
}
.service-card:hover {
  border-color: rgba(13,148,136,0.25);
  box-shadow: 0 24px 60px rgba(13,148,136,0.12), 0 0 0 1px rgba(13,148,136,0.08);
  transform: translateY(-6px);
}
.service-card:hover::before { opacity: 1; }

.svc-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 72px; font-weight: 700;
  color: rgba(13,148,136,0.07);
  position: absolute; top: 12px; right: 20px;
  line-height: 1;
}
.svc-icon {
  width: 56px; height: 56px;
  background: linear-gradient(135deg, var(--teal) 0%, var(--teal2) 100%);
  border-radius: 16px;
  display: flex; align-items: center; justify-content: center;
  font-size: 24px; margin-bottom: 24px;
  box-shadow: 0 8px 24px rgba(13,148,136,0.3);
}
.service-card h3 {
  font-size: 18px; font-weight: 700; color: var(--ink);
  margin-bottom: 12px; line-height: 1.3;
}
.service-card p {
  font-size: 14px; color: var(--muted); line-height: 1.7;
}

/* ══════════════════════════════
   ABOUT / CONSULTANT SECTION
══════════════════════════════ */
.about-section {
  background: white;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
  padding: 100px 80px;
}
.about-img-col { position: relative; }
.about-img-wrap {
  position: relative;
  border-radius: 24px; overflow: hidden;
  box-shadow: 0 40px 80px rgba(0,0,0,0.14);
}
.about-img-wrap img {
  width: 100%; display: block;
  filter: contrast(1.05) brightness(1.02) saturate(0.9);
  border-radius: 24px;
  aspect-ratio: 3/4; object-fit: cover; object-position: center top;
}
.about-img-deco {
  position: absolute;
  top: -20px; left: -20px;
  width: 100%; height: 100%;
  border-radius: 24px;
  border: 2px solid rgba(13,148,136,0.3);
  z-index: -1;
}
.about-exp-badge {
  position: absolute;
  bottom: -20px; right: -20px;
  background: linear-gradient(135deg, var(--teal) 0%, var(--teal2) 100%);
  border-radius: 20px;
  padding: 22px 28px;
  text-align: center;
  box-shadow: 0 16px 48px rgba(13,148,136,0.4);
}
.about-exp-badge .num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 44px; font-weight: 700; color: white; line-height: 1;
}
.about-exp-badge .lbl { font-size: 12px; color: rgba(255,255,255,0.8); margin-top: 4px; line-height: 1.4; }

.about-right {}
.about-right .section-h { margin-bottom: 20px; }
.about-right .section-p { margin-bottom: 32px; }
.about-tagline {
  font-family: 'Cormorant Garamond', serif;
  font-size: 22px; color: var(--teal); font-style: italic;
  margin-bottom: 36px; line-height: 1.4;
}
.about-details { display: flex; flex-direction: column; gap: 16px; }
.about-row {
  display: flex; align-items: center; gap: 14px;
  padding: 14px 20px;
  background: var(--slate);
  border-radius: 12px;
  border-left: 3px solid var(--teal);
}
.about-row .icon { font-size: 20px; }
.about-row div { display: flex; flex-direction: column; }
.about-row small { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; }
.about-row strong { font-size: 14.5px; color: var(--ink); font-weight: 600; }

/* ══════════════════════════════
   WHY CHOOSE
══════════════════════════════ */
.why-section { background: var(--ink); padding: 100px 80px; }
.why-section .section-h { color: white; }
.why-section .section-p { color: rgba(255,255,255,0.5); }

.why-tabs {
  display: flex; gap: 12px; margin: 40px 0 48px;
}
.why-tab {
  padding: 10px 24px;
  border-radius: 50px;
  font-size: 13.5px; font-weight: 600;
  cursor: pointer; border: 1px solid rgba(255,255,255,0.12);
  color: rgba(255,255,255,0.5);
  transition: all 0.25s;
}
.why-tab.active, .why-tab:hover {
  background: var(--teal); border-color: var(--teal); color: white;
}

.why-grid {
  display: grid; grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}
.why-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 18px; padding: 28px;
  display: flex; gap: 20px; align-items: flex-start;
  transition: all 0.3s;
}
.why-card:hover {
  background: rgba(13,148,136,0.08);
  border-color: rgba(13,148,136,0.3);
  transform: translateX(4px);
}
.why-card-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 32px; font-weight: 700; color: var(--teal2);
  line-height: 1; min-width: 32px;
}
.why-card h4 { font-size: 15px; font-weight: 700; color: white; margin-bottom: 6px; }
.why-card p { font-size: 13px; color: rgba(255,255,255,0.45); line-height: 1.65; }

/* ══════════════════════════════
   SPECIAL BENEFIT
══════════════════════════════ */
.benefit-section { background: white; padding: 0 80px 0; }
.benefit-wrap {
  background: linear-gradient(135deg, var(--ink) 0%, #0c3d35 100%);
  border-radius: 32px;
  padding: 72px 80px;
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 60px; align-items: center;
  position: relative; overflow: hidden;
}
.benefit-wrap::before {
  content: '';
  position: absolute;
  right: -80px; top: -80px;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(13,148,136,0.2) 0%, transparent 70%);
}
.benefit-wrap::after {
  content: '';
  position: absolute;
  left: 40%; bottom: -60px;
  width: 200px; height: 200px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(13,148,136,0.1) 0%, transparent 70%);
}
.benefit-left { position: relative; z-index: 2; }
.benefit-left .chip { background: rgba(255,255,255,0.08); border-color: rgba(255,255,255,0.15); color: var(--teal3); }
.benefit-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 44px; font-weight: 600; color: white;
  line-height: 1.15; margin-bottom: 20px;
}
.benefit-title .gold { color: var(--gold2); }
.benefit-desc { font-size: 16px; color: rgba(255,255,255,0.6); line-height: 1.75; font-weight: 300; }
.benefit-tag {
  display: inline-flex; align-items: center; gap: 8px;
  margin-top: 24px;
  background: var(--gold);
  color: var(--ink); font-weight: 700; font-size: 14px;
  padding: 10px 22px; border-radius: 50px;
}

.benefit-right {
  position: relative; z-index: 2;
  display: flex; flex-direction: column; gap: 16px;
}
.benefit-item {
  display: flex; align-items: center; gap: 14px;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 14px; padding: 18px 22px;
}
.b-check {
  width: 32px; height: 32px; min-width: 32px;
  background: linear-gradient(135deg, var(--teal), var(--teal2));
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 14px; color: white; font-weight: 700;
}
.benefit-item p { font-size: 14px; color: rgba(255,255,255,0.75); line-height: 1.5; }

/* ══════════════════════════════
   CONTACT
══════════════════════════════ */
.contact-section { background: var(--slate); }
.contact-grid {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 60px; margin-top: 56px; align-items: start;
}
.contact-info-col {}
.contact-info-col .section-h { font-size: 36px; margin-bottom: 14px; }
.contact-info-col .section-p { font-size: 15px; margin-bottom: 40px; }

.contact-cards { display: flex; flex-direction: column; gap: 14px; }
.c-card {
  background: white;
  border-radius: 16px;
  padding: 20px 24px;
  display: flex; align-items: center; gap: 16px;
  border: 1px solid rgba(0,0,0,0.06);
  transition: all 0.25s;
  text-decoration: none;
}
.c-card:hover {
  border-color: var(--teal);
  box-shadow: 0 8px 32px rgba(13,148,136,0.1);
  transform: translateX(4px);
}
.c-icon-wrap {
  width: 48px; height: 48px;
  background: linear-gradient(135deg, var(--teal) 0%, var(--teal2) 100%);
  border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 20px; min-width: 48px;
}
.c-card-text small { font-size: 11px; color: var(--muted); text-transform: uppercase; letter-spacing: 1.2px; display: block; margin-bottom: 3px; }
.c-card-text strong { font-size: 15px; color: var(--ink); font-weight: 600; }

/* Form */
.contact-form-col {
  background: white;
  border-radius: 24px;
  padding: 40px;
  border: 1px solid rgba(0,0,0,0.06);
  box-shadow: 0 8px 40px rgba(0,0,0,0.06);
}
.form-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 28px; font-weight: 600; color: var(--ink);
  margin-bottom: 8px;
}
.form-sub { font-size: 14px; color: var(--muted); margin-bottom: 28px; }

.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.fg { margin-bottom: 18px; }
.fg label { font-size: 12.5px; font-weight: 600; color: var(--ink); letter-spacing: 0.3px; display: block; margin-bottom: 8px; }
.fg input, .fg select, .fg textarea {
  width: 100%; padding: 13px 16px;
  border: 1.5px solid rgba(0,0,0,0.1);
  border-radius: 12px;
  font-family: 'Outfit', sans-serif; font-size: 14px; color: var(--ink);
  background: var(--slate); outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.fg input:focus, .fg select:focus, .fg textarea:focus {
  border-color: var(--teal);
  box-shadow: 0 0 0 3px rgba(13,148,136,0.1);
  background: white;
}
.fg textarea { resize: vertical; min-height: 110px; }
.form-btn {
  width: 100%; padding: 16px;
  background: linear-gradient(135deg, var(--teal) 0%, var(--teal2) 100%);
  color: white; border: none; border-radius: 12px;
  font-family: 'Outfit', sans-serif; font-size: 15px; font-weight: 700;
  cursor: pointer; transition: all 0.3s;
  box-shadow: 0 8px 28px rgba(13,148,136,0.35);
  display: flex; align-items: center; justify-content: center; gap: 8px;
}
.form-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 14px 40px rgba(13,148,136,0.45);
}

/* ══════════════════════════════
   FOOTER
══════════════════════════════ */
footer {
  background: var(--ink2);
  padding: 70px 80px 32px;
}
.footer-grid {
  display: grid; grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 48px; padding-bottom: 48px;
  border-bottom: 1px solid rgba(255,255,255,0.06);
  margin-bottom: 32px;
}
.footer-brand img { height: 40px; margin-bottom: 16px; display: block; }
.footer-brand p { font-size: 14px; color: rgba(255,255,255,0.4); line-height: 1.8; max-width: 280px; margin-bottom: 20px; }
.social-links { display: flex; gap: 12px; }
.social-btn {
  width: 38px; height: 38px;
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 16px; text-decoration: none;
  transition: all 0.2s; color: rgba(255,255,255,0.5);
}
.social-btn:hover { background: var(--teal); border-color: var(--teal); color: white; }
.footer-col h4 { font-size: 13px; font-weight: 700; color: white; letter-spacing: 0.5px; margin-bottom: 20px; text-transform: uppercase; }
.footer-col ul { list-style: none; }
.footer-col li { margin-bottom: 12px; }
.footer-col a { font-size: 14px; color: rgba(255,255,255,0.4); text-decoration: none; transition: color 0.2s; }
.footer-col a:hover { color: var(--teal2); }
.footer-bottom {
  display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 16px;
}
.footer-bottom p { font-size: 13px; color: rgba(255,255,255,0.25); }
.footer-pills { display: flex; gap: 8px; }
.fpill {
  background: rgba(255,255,255,0.04); border-radius: 50px;
  padding: 6px 14px; font-size: 12px; color: rgba(255,255,255,0.3);
  border: 1px solid rgba(255,255,255,0.07);
}

/* ══════════════════════════════
   ANIMATIONS
══════════════════════════════ */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}
.hero-left > * { animation: fadeUp 0.8s ease both; }
.hero-eyebrow { animation-delay: 0.1s; }
.hero-headline { animation-delay: 0.2s; }
.hero-desc { animation-delay: 0.35s; }
.hero-actions { animation-delay: 0.5s; }
.hero-metrics { animation-delay: 0.65s; }

/* ══════════════════════════════
   MOBILE
══════════════════════════════ */
@media (max-width: 1024px) {
  nav { padding: 0 24px; }
  nav ul { display: none; }
  .section { padding: 70px 24px; }
  .hero { grid-template-columns: 1fr; }
  .hero-left { padding: 120px 24px 60px; text-align: center; }
  .hero-desc { margin: 0 auto 40px; }
  .hero-actions { justify-content: center; }
  .hero-metrics { justify-content: center; }
  .hero-right { height: 480px; }
  .name-card { bottom: 20px; right: 16px; }
  .services-grid { grid-template-columns: 1fr 1fr; }
  .about-section { grid-template-columns: 1fr; padding: 70px 24px; }
  .why-grid { grid-template-columns: 1fr; }
  .benefit-wrap { grid-template-columns: 1fr; padding: 48px 36px; }
  .contact-grid { grid-template-columns: 1fr; }
  footer { padding: 48px 24px 28px; }
  .footer-grid { grid-template-columns: 1fr 1fr; }
  .benefit-section { padding: 0 24px; }
}
</style>
</head>
<body>

<!-- ══ NAV ══ -->
<nav>
  <a class="nav-logo" href="#">
    <img src="data:image/jpeg;base64,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AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAP/EAAL/2gAMAwEAAgADAAAAIQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA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AAAAAAAAAAAAAAAAAAAAAAAAAAAABALJIGKvlQrNc5OXedyK5wApiZYS9IrDILAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABEAAAAAAAAAADEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD/xAAC/9oADAMBAAIAAwAAABDzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz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PPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPPBvvPl/PPPPPBm9fENfKJImhN/PPPPPPPPPPOCvPPPPPPPPPPPPPPPPPPPPPPPPPPJlvDt77tfxsbq6tRvnOearzGp2fOllMt3fIbK9fPPPPPPPPPPPPPPPPPPPPPPPPPMaPiIRF42qc9Mevka0OMJgPXWE5LpuWClbmqfNPPPPPPPPPPPPPPPPPPPPPPPPPPCwzGOLntqodEMSPPtc3BdN95px5SX/ADmMI7Hwx3zzzzzzzzzzzzzzzzzzzzzzzzzyAfzh/wCKs5VZaMPJn91ea88o+SwxKjoF0NKgRyf888888888888888888888888888M8McMN8sc888s8c8ccs88MM9Mcs9MsN98d98c88888888888888888888888888888888Y058xpw62+y8/x0x2E+d9h8z+8888888888888888888888888888888888s9Ou/I5nwWnNbxXRxn7ytc9QFA4Xh8vMM/8888888888888888888888888888888888888888888888/88888888888e888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888/8QASREAAgEDAgIGBgUHCQgDAAAAAQIDAAQRBTESIRMiQVFhcQYQUIGRsSMyQlLRFCByc5Kh4RUWMDNAQ1RiwSQlNVNggpCyNGOi/9oACAECAQE/AP8AyOx2N3J9WFvfy+dLpN2d+EeZo6VMPtCjpsw7aaxnXsB8qaKRd0PtiGCad+CJCxq19HicGd/+1ag063gGERR866JB2V0afcX4V0afcX4UYYzvGvwFNbQH+7X3cvlT2MR2yP31PpSt2A+I5Gp9NmjyU6wogg4I9Us0UKF5JFRe8nFXfpNCsipbrxDiHE7bcPbge0dN0OW5AlmykXZ3tR/IdOgXi4Y484HInJ91fy1pf+JH7D/hVve2t0WEMobh35Eb+f5mKuLmC3XilkCirj0gXaCHPi/4CrjXp1+vcpH4cqn9KI12nkf9Gp/SgvtBk9hZquPSC+fIV1T9EVc3Msp4pJGY97HNKOoWPbyFWkhltbeQ7tEp+I9n6PowIW4uV8UQ/M+r0k/+DH+uX5H1ejf9bc/or+Zqmsi3Jhgw0na3YtaprUNuxaeQyTH7OedXnpDdTZAfgX7qb+8095KdgPfzNG4nP2/3CjJKftmizfaY1FGZCGI6gqY/VWtMBGnWf6hPl7O0PTRO/TyrmND1R941f3RtLV5gnERjA8ziv5yzf4ZPia1DV5L2FYmiVQHDZB7gR6tO1B7FpGWMNxADma/nLN/hk+JrTL9r6F3aMKVfHI1rWpG1jEMRxK43+6K1vWDZqIYOc7+/hHf50UkY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" alt="HealthPlaced">
  </a>
  <div class="nav-links">
    <a href="#services">Services</a>
    <a href="#about">About</a>
    <a href="#why">Why Us</a>
    <a href="#contact">Contact</a>
    <a href="tel:8076319172" class="nav-cta">📞 8076319172</a>
  </div>
</nav>

<!-- ══ HERO ══ -->
<section class="hero" id="home">
  <div class="hero-bg">
    <div class="hero-grid-lines"></div>
  </div>

  <div class="hero-left">
    <div class="hero-eyebrow">
      <div class="eyebrow-line"></div>
      <span class="eyebrow-text">India's Healthcare Placement Partner</span>
    </div>

    <h1 class="hero-headline">
      Right People.<br>
      <span class="teal">Right Place.</span><br>
      <span class="accent">Better Care.</span>
    </h1>

    <p class="hero-desc">
      HealthPlaced connects skilled healthcare professionals with verified hospitals, clinics & labs across Pan India. Permanent placements, internships, bulk hiring — all under one roof.
    </p>

    <div class="hero-actions">
      <a href="#contact" class="btn-hero-primary">
        🏥 Hire Healthcare Staff
      </a>
      <a href="#contact" class="btn-hero-secondary">
        👨‍⚕️ Find Your Job →
      </a>
    </div>

    <div class="hero-metrics">
      <div class="metric">
        <div class="metric-val">500<span>+</span></div>
        <div class="metric-label">Placements Done</div>
      </div>
      <div class="metric">
        <div class="metric-val">200<span>+</span></div>
        <div class="metric-label">Partner Hospitals</div>
      </div>
      <div class="metric">
        <div class="metric-val">Pan<span> IN</span></div>
        <div class="metric-label">India Coverage</div>
      </div>
    </div>
  </div>

  <div class="hero-right">
    <div class="photo-container">
      <div class="photo-bracket"></div>
      <div class="photo-bracket-bl"></div>
      <img class="hero-photo" src="data:image/jpeg;base64,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