<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sagres Automação Comercial | Londrina – PR</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,400&family=Manrope:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --bg: #070b14; --bg2: #0c1220; --card: #101828; --card2: #0f1a2e;
      --accent: #1a6fe8; --accent2: #45aaff; --teal: #4ecdc4;
      --text: #e8edf8; --muted: #6b7a99;
      --border: rgba(255,255,255,0.06);
      --grad: linear-gradient(135deg, #1a6fe8 0%, #45aaff 100%);
    }
    html { scroll-behavior: smooth; }
    body { font-family: 'Plus Jakarta Sans', sans-serif; background: var(--bg); color: var(--text); overflow-x: hidden; }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 200;
      padding: 0 3rem; height: 64px;
      display: flex; align-items: center; justify-content: space-between;
      background: rgba(7,11,20,0.85); backdrop-filter: blur(20px);
      border-bottom: 1px solid var(--border);
    }
    .nav-logo {
      font-family: 'Manrope', sans-serif; font-weight: 900; font-size: 1.3rem;
      letter-spacing: -0.05em; display: flex; align-items: center; gap: 7px;
    }
    .nav-dot {
      width: 8px; height: 8px; background: var(--grad); border-radius: 50%;
      animation: blink 2s ease-in-out infinite;
    }
    @keyframes blink { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.3;transform:scale(0.6)} }
    .nav-links { display: flex; gap: 2rem; align-items: center; }
    .nav-links a {
      font-size: 0.875rem; font-weight: 500; color: var(--muted);
      text-decoration: none; transition: color .2s; position: relative;
    }
    .nav-links a::after {
      content:''; position:absolute; bottom:-4px; left:0;
      width:0; height:1px; background: var(--accent2); transition: width .25s;
    }
    .nav-links a:hover { color: var(--text); }
    .nav-links a:hover::after { width: 100%; }
    .nav-phone { color: var(--teal) !important; font-weight: 600 !important; }
    .nav-phone::after { display: none !important; }
    .nav-cta {
      background: var(--grad); color: #fff !important; padding: 8px 20px;
      border-radius: 8px; font-weight: 600 !important; font-size: 0.85rem !important;
      box-shadow: 0 4px 20px rgba(26,111,232,0.35);
      transition: transform .2s, opacity .2s !important;
    }
    .nav-cta:hover { transform: translateY(-1px); opacity: 0.9; }
    .nav-cta::after { display: none !important; }

    /* HERO */
    .hero {
      min-height: 100vh; padding: 100px 3rem 5rem;
      display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 4rem;
      align-items: center; position: relative; overflow: hidden;
    }
    .hero::before {
      content: ''; position: absolute; top: 0; right: -10%; width: 55%; height: 100%;
      background: var(--card2); clip-path: polygon(15% 0, 100% 0, 100% 100%, 0% 100%); z-index: 0;
    }
    .hero::after {
      content: ''; position: absolute; top: 15%; left: 35%;
      width: 500px; height: 500px;
      background: radial-gradient(circle, rgba(26,111,232,0.18) 0%, transparent 65%);
      pointer-events: none; z-index: 0; animation: breathe 6s ease-in-out infinite;
    }
    @keyframes breathe { 0%,100%{transform:scale(1);opacity:0.8} 50%{transform:scale(1.2);opacity:1} }
    .hero-ring {
      position: absolute; border-radius: 50%;
      border: 1px solid rgba(26,111,232,0.12); pointer-events: none; z-index: 0;
    }
    .hero-content { position: relative; z-index: 1; }
    .hero-eyebrow {
      display: inline-flex; align-items: center; gap: 10px;
      font-size: 0.72rem; font-weight: 700; letter-spacing: 0.14em;
      text-transform: uppercase; color: var(--accent2); margin-bottom: 1.8rem;
    }
    .hero-eyebrow::before { content:''; width:28px; height:2px; background: var(--grad); border-radius:2px; }
    .hero h1 {
      font-family: 'Manrope', sans-serif; font-weight: 900;
      font-size: clamp(2.8rem, 5vw, 4.8rem); line-height: 1.0;
      letter-spacing: -0.05em; margin-bottom: 1.6rem;
    }
    .hero h1 em { font-style:normal; background: var(--grad); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }
    .hero h1 .outline { font-style:normal; color: var(--text); }
    .hero-desc { font-size: 1.05rem; line-height: 1.75; color: var(--muted); max-width: 460px; margin-bottom: 2.5rem; }
    .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; margin-bottom: 3.5rem; }
    .btn-primary {
      background: var(--grad); color: #fff; padding: 14px 32px; border-radius: 10px;
      font-family: 'Manrope', sans-serif; font-weight: 700; font-size: 0.95rem;
      text-decoration: none; display: inline-flex; align-items: center; gap: 8px;
      box-shadow: 0 8px 32px rgba(26,111,232,0.4); transition: transform .2s, box-shadow .2s;
    }
    .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 16px 40px rgba(26,111,232,0.55); }
    .arrow { transition: transform .2s; }
    .btn-primary:hover .arrow { transform: translateX(4px); }
    .btn-ghost {
      background: transparent; color: var(--text); border: 1px solid rgba(255,255,255,0.12);
      padding: 14px 32px; border-radius: 10px;
      font-family: 'Manrope', sans-serif; font-weight: 600; font-size: 0.95rem;
      text-decoration: none; transition: border-color .2s, background .2s, transform .2s;
    }
    .btn-ghost:hover { border-color: var(--accent2); background: rgba(26,111,232,0.06); transform: translateY(-2px); }
    .hero-trust { display: flex; align-items: center; gap: 1.2rem; }
    .trust-avs { display: flex; }
    .trust-av {
      width: 36px; height: 36px; border-radius: 50%; border: 2px solid var(--bg);
      background: var(--grad); display: grid; place-items: center;
      font-size: 0.75rem; font-weight: 700; margin-left: -10px;
    }
    .trust-av:first-child { margin-left: 0; }
    .trust-text { font-size: 0.82rem; color: var(--muted); }
    .trust-text strong { color: var(--text); }
    .hero-right { position: relative; z-index: 1; display: flex; flex-direction: column; gap: 1rem; }
    .hero-main-card {
      background: linear-gradient(135deg, #111e38, #0d1829);
      border: 1px solid rgba(26,111,232,0.25); border-radius: 20px; padding: 2rem;
      position: relative; overflow: hidden; box-shadow: 0 24px 60px rgba(0,0,0,0.5);
    }
    .hero-main-card::before {
      content:''; position:absolute; top:0; left:0; right:0; height:2px; background: var(--grad);
    }
    .card-lbl { font-size: 0.7rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--accent2); margin-bottom: 1rem; }
    .big-num {
      font-family: 'Manrope', sans-serif; font-size: 4.5rem; font-weight: 900;
      letter-spacing: -0.06em; background: var(--grad);
      -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text;
      line-height: 1; margin-bottom: .3rem;
    }
    .big-desc { font-size: 0.9rem; color: var(--muted); }
    .mini-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .mini-card {
      background: var(--card); border: 1px solid var(--border); border-radius: 14px;
      padding: 1.2rem 1.4rem; transition: border-color .25s, transform .25s;
    }
    .mini-card:hover { border-color: rgba(26,111,232,0.3); transform: translateY(-2px); }
    .mini-val { font-family: 'Manrope', sans-serif; font-size: 1.8rem; font-weight: 800; letter-spacing: -0.04em; line-height: 1; margin-bottom: 4px; }
    .mini-val.blue { color: var(--accent2); }
    .mini-val.teal { color: var(--teal); }
    .mini-lbl { font-size: 0.75rem; color: var(--muted); }
    .support-badge {
      background: linear-gradient(135deg, #0f2040, #1a3060);
      border: 1px solid rgba(78,205,196,0.25); border-radius: 14px;
      padding: 1.2rem 1.4rem; display: flex; align-items: center; gap: 1rem;
    }
    .support-ico {
      width: 44px; height: 44px; background: rgba(78,205,196,0.12);
      border-radius: 12px; display: grid; place-items: center; font-size: 1.3rem; flex-shrink: 0;
    }
    .support-badge h4 { font-size: 0.9rem; font-weight: 600; margin-bottom: 3px; }
    .support-badge p { font-size: 0.75rem; color: var(--muted); line-height: 1.4; }
    @keyframes fadeUp { from{opacity:0;transform:translateY(30px)} to{opacity:1;transform:translateY(0)} }
    .hero-eyebrow { animation: fadeUp .6s .1s both; }
    .hero h1 { animation: fadeUp .6s .2s both; }
    .hero-desc { animation: fadeUp .6s .3s both; }
    .hero-btns { animation: fadeUp .6s .4s both; }
    .hero-trust { animation: fadeUp .6s .5s both; }
    .hero-right { animation: fadeUp .7s .4s both; }

    /* TICKER */
    .ticker { border-top:1px solid var(--border); border-bottom:1px solid var(--border); background: var(--card); padding: 14px 0; overflow: hidden; white-space: nowrap; }
    .ticker-track { display: inline-flex; animation: marquee 32s linear infinite; }
    @keyframes marquee { from{transform:translateX(0)} to{transform:translateX(-50%)} }
    .ticker-item { display: inline-flex; align-items: center; gap: 1rem; padding: 0 2.5rem; font-size: 0.82rem; font-weight: 600; color: var(--muted); letter-spacing: 0.04em; }
    .tdot { width:5px; height:5px; background: var(--accent); border-radius: 50%; flex-shrink: 0; }

    /* SECTIONS */
    .s { padding: 7rem 3rem; }
    .s-tag { display: inline-flex; align-items: center; gap: 8px; font-size: 0.72rem; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--accent2); margin-bottom: 1rem; }
    .s-tag::before { content:''; width:20px; height:2px; background: var(--accent2); border-radius:2px; }
    .s-title { font-family: 'Manrope', sans-serif; font-size: clamp(2rem,3.5vw,3rem); font-weight: 900; letter-spacing: -0.05em; line-height: 1.05; margin-bottom: 1rem; }
    .s-sub { color: var(--muted); font-size: 1rem; line-height: 1.7; max-width: 520px; }

    /* PRODUCTS */
    .products-section { background: var(--bg); }
    .products-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; gap: 2rem; }
    .products-grid {
      display: grid; grid-template-columns: repeat(4, 1fr);
      gap: 0; border: 1px solid var(--border); border-radius: 20px; overflow: hidden;
    }
    .pc {
      background: var(--card);
      padding: 1.4rem 1.5rem;
      border-right: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      transition: background .2s; cursor: default; position: relative;
    }
    .pc:nth-child(4n) { border-right: none; }
    .pc:nth-last-child(-n+4) { border-bottom: none; }
    .pc::after { content:''; position:absolute; top:0; left:0; width:2px; height:0; background:var(--grad); transition:height .3s; }
    .pc:hover { background: #0f1c32; }
    .pc:hover::after { height: 100%; }
    .pc:hover .pi { transform: scale(1.12); }
    .pi {
      width: 40px; height: 40px;
      margin-bottom: .9rem;
      display: flex; align-items: center; justify-content: center;
      border-radius: 10px;
      font-size: 1.25rem;
      transition: transform .2s;
    }
    .pc h3 { font-family:'Manrope',sans-serif; font-size:0.88rem; font-weight:700; margin-bottom:.35rem; letter-spacing:-0.01em; }
    .pc p { font-size:0.76rem; color:var(--muted); line-height:1.55; }
    .pc.feat {
      grid-column: span 2;
      background: linear-gradient(135deg,#0d1a35,#0a1428);
      border-right: 1px solid var(--border);
    }
    .pc.feat .pi { width:48px; height:48px; font-size:1.6rem; }
    .pc.feat h3 { font-size: 1rem; }
    .pc.feat p { font-size: 0.82rem; }
    .pbadge { display:inline-block; background: rgba(26,111,232,0.15); color: var(--accent2); font-size:0.58rem; font-weight:800; letter-spacing:0.1em; text-transform:uppercase; padding:2px 8px; border-radius:100px; margin-bottom:.7rem; border: 1px solid rgba(26,111,232,0.25); }

    /* WHY */
    .why-section { background: var(--bg2); border-top:1px solid var(--border); border-bottom:1px solid var(--border); }
    .why-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: start; }
    .why-feats { display:flex; flex-direction:column; margin-top:2.5rem; }
    .wf {
      display:flex; gap:1.2rem; padding:1.5rem 0;
      border-bottom:1px solid var(--border); position:relative;
      transition: padding-left .25s;
    }
    .wf::before {
      content:''; position:absolute; left:-3rem; top:0; bottom:0; width:3px;
      background:var(--grad); transform:scaleY(0); transition:transform .3s; transform-origin:top;
    }
    .wf:hover { padding-left:.5rem; }
    .wf:hover::before { transform:scaleY(1); }
    .wf-num { font-family:'Manrope',sans-serif; font-size:0.7rem; font-weight:800; color:var(--accent); letter-spacing:0.06em; flex-shrink:0; padding-top:3px; }
    .wf h4 { font-size:0.95rem; font-weight:600; margin-bottom:4px; }
    .wf p { font-size:0.82rem; color:var(--muted); line-height:1.6; }
    .why-vis { position:sticky; top:100px; }
    .why-card {
      background: linear-gradient(145deg,#111e38,#0c1525);
      border:1px solid rgba(26,111,232,0.18); border-radius:24px; padding:2.5rem;
      position:relative; overflow:hidden; box-shadow:0 32px 80px rgba(0,0,0,0.5);
    }
    .why-card::before { content:''; position:absolute; top:-40px; right:-40px; width:200px; height:200px; background:radial-gradient(circle,rgba(26,111,232,0.15),transparent 70%); }
    .why-card::after { content:''; position:absolute; top:0; left:0; right:0; height:1px; background:linear-gradient(90deg,transparent,rgba(69,170,255,0.5),transparent); }
    .wct { font-family:'Manrope',sans-serif; font-size:1.1rem; font-weight:700; margin-bottom:1.5rem; position:relative; }
    .chips { display:flex; flex-wrap:wrap; gap:.6rem; position:relative; }
    .chip {
      background:rgba(26,111,232,0.08); border:1px solid rgba(26,111,232,0.15);
      color:var(--text); font-size:0.78rem; font-weight:500; padding:6px 14px;
      border-radius:100px; transition:background .2s, border-color .2s;
    }
    .chip:hover { background:rgba(26,111,232,0.16); border-color:rgba(26,111,232,0.35); }
    .wdiv { border:none; border-top:1px solid var(--border); margin:1.8rem 0; }
    .apps-row { display:grid; grid-template-columns:1fr 1fr; gap:.8rem; position:relative; }
    .arc { background:rgba(255,255,255,0.03); border:1px solid var(--border); border-radius:12px; padding:1rem; }
    .arc h5 { font-size:0.85rem; font-weight:600; margin-bottom:2px; }
    .arc span { font-size:0.72rem; color:var(--muted); display:block; margin-bottom:.5rem; }
    .slinks { display:flex; gap:.4rem; }
    .sl { background:rgba(255,255,255,0.06); color:var(--muted); font-size:0.65rem; font-weight:700; letter-spacing:0.04em; padding:3px 8px; border-radius:5px; text-decoration:none; transition:color .2s, background .2s; }
    .sl:hover { color:var(--text); background:rgba(255,255,255,0.1); }

    /* ABOUT */
    .about-section { background:var(--bg); position:relative; overflow:hidden; }
    .about-section::before { content:''; position:absolute; bottom:-100px; left:-100px; width:500px; height:500px; background:radial-gradient(circle,rgba(26,111,232,0.07),transparent 65%); pointer-events:none; }
    .about-inner { display:grid; grid-template-columns:0.9fr 1.1fr; gap:6rem; align-items:center; position:relative; z-index:1; }
    .aqc {
      background:var(--card2); border:1px solid rgba(26,111,232,0.15); border-radius:24px; padding:2.5rem;
      position:relative; overflow:hidden;
    }
    .aqc::before { content:''; position:absolute; top:0; left:0; right:0; height:2px; background:linear-gradient(90deg,var(--accent),var(--teal)); }
    .bq { font-family:'Manrope',sans-serif; font-size:6rem; font-weight:900; line-height:0.7; color:rgba(26,111,232,0.1); margin-bottom:1rem; display:block; }
    .aqt { font-size:0.95rem; line-height:1.8; color:var(--muted); margin-bottom:2rem; }
    .aqt strong { color:var(--text); font-weight:600; }
    .ametrics { display:grid; grid-template-columns:1fr 1fr; gap:1px; background:var(--border); border:1px solid var(--border); border-radius:14px; overflow:hidden; }
    .ambox { background:var(--card); padding:1.2rem 1.5rem; }
    .amval { font-family:'Manrope',sans-serif; font-size:2rem; font-weight:900; letter-spacing:-0.04em; background:var(--grad); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; margin-bottom:3px; }
    .amlbl { font-size:0.75rem; color:var(--muted); }
    .atcol .s-title { margin-bottom:1.5rem; }
    .atcol .s-sub { margin-bottom:2rem; max-width:100%; }
    .timeline { display:flex; flex-direction:column; }
    .ti { display:flex; gap:1.5rem; padding:1.2rem 0; border-left:2px solid var(--border); padding-left:1.5rem; position:relative; transition:border-color .2s; }
    .ti:hover { border-left-color:var(--accent); }
    .ti::before { content:''; position:absolute; left:-5px; top:1.5rem; width:8px; height:8px; background:var(--bg2); border:2px solid var(--muted); border-radius:50%; transition:border-color .2s, background .2s; }
    .ti:hover::before { border-color:var(--accent); background:var(--accent); }
    .ti h4 { font-size:0.9rem; font-weight:600; margin-bottom:3px; }
    .ti p { font-size:0.8rem; color:var(--muted); line-height:1.5; }

    /* CONTACT */
    .contact-section { background:var(--bg2); border-top:1px solid var(--border); }
    .contact-inner { display:grid; grid-template-columns:1fr 1fr; gap:4rem; align-items:start; }
    .ccards { display:grid; grid-template-columns:1fr 1fr; gap:.6rem; margin-top:2rem; }
    .cc {
      padding:.9rem 1rem;
      border-bottom: 1px solid var(--border);
      display:flex; align-items:flex-start; gap:.7rem;
      transition: border-color .2s;
    }
    .cc:hover { border-color: rgba(26,111,232,0.35); }
    .cci { font-size:1rem; flex-shrink:0; margin-top:2px; opacity:.7; }
    .cc h4 { font-size:0.68rem; font-weight:600; letter-spacing:0.08em; text-transform:uppercase; color:var(--muted); margin-bottom:3px; }
    .cc a, .cc p { font-size:0.88rem; font-weight:500; color:var(--text); text-decoration:none; line-height:1.4; }
    .cc a:hover { color:var(--accent2); }
    .map-wrap { border-radius:16px; overflow:hidden; border:1px solid var(--border); height:100%; min-height:420px; box-shadow:0 20px 60px rgba(0,0,0,0.4); }
    .map-wrap iframe { width:100%; height:100%; border:none; filter:grayscale(0.5) invert(0.9) hue-rotate(200deg) saturate(0.7); }
    .ctab { margin-top:1.5rem; grid-column: 1 / -1; }
    .ctab p { font-size:0.82rem; color:var(--muted); margin-bottom:1rem; }

    /* FOOTER */
    footer { background:var(--bg); border-top:1px solid var(--border); }
    .foot-inner { padding:3rem 3rem 2rem; display:grid; grid-template-columns:1.5fr 1fr 1fr; gap:3rem; }
    .fbrand .nav-logo { font-size:1.4rem; margin-bottom:1rem; }
    .fbrand p { font-size:0.82rem; color:var(--muted); line-height:1.7; max-width:300px; }
    .fcol h5 { font-family:'Manrope',sans-serif; font-size:0.82rem; font-weight:700; letter-spacing:0.08em; text-transform:uppercase; color:var(--muted); margin-bottom:1.2rem; }
    .fcol a { display:block; font-size:0.85rem; color:var(--text); text-decoration:none; margin-bottom:.6rem; opacity:.7; transition:opacity .2s, color .2s; }
    .fcol a:hover { opacity:1; color:var(--accent2); }
    .foot-bot { border-top:1px solid var(--border); padding:1.5rem 3rem; display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:1rem; }
    .foot-bot p { font-size:0.75rem; color:var(--muted); }
    .fbl { display:flex; gap:1.5rem; }
    .fbl a { font-size:0.75rem; color:var(--muted); text-decoration:none; }
    .fbl a:hover { color:var(--text); }

    @media(max-width:900px){
      .hero{grid-template-columns:1fr;padding:90px 1.5rem 4rem;}
      .hero::before{display:none;}
      .hero-right{order:-1;}
      .why-inner,.about-inner,.contact-inner{grid-template-columns:1fr;gap:2.5rem;}
      .products-grid{grid-template-columns:1fr 1fr;}
      .pc.feat{grid-column:span 2;}
      .s{padding:4rem 1.5rem;}
      .products-header{flex-direction:column;}
      nav{padding:0 1.5rem;}
      .nav-links{display:none;}
      .foot-inner{grid-template-columns:1fr;gap:2rem;}
      .foot-bot{padding:1.5rem;}
    }
  </style>
</head>
<body>

<nav>
  <div class="nav-logo"><div class="nav-dot"></div>SAGRES</div>
  <div class="nav-links">
    <a href="#produtos">Produtos</a>
    <a href="#porque">Por que Sagres?</a>
    <a href="#clientes">Clientes</a>
    <a href="#sobre">Sobre</a>
    <a href="#contato">Contato</a>
    <a href="https://wa.me/554333388099" target="_blank" rel="noopener" class="nav-phone">📞 43 3338-8099</a>
    <a href="https://sagrescloud.com.br/" class="nav-cta" target="_blank">Área do Usuário →</a>
  </div>
</nav>

<section class="hero">
  <div class="hero-ring" style="width:420px;height:420px;top:5%;right:2%;animation:spin 30s linear infinite;opacity:.5"></div>
  <div class="hero-ring" style="width:200px;height:200px;top:25%;right:18%;animation:spin 18s linear infinite reverse;opacity:.3"></div>
  <style>@keyframes spin{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}</style>

  <div class="hero-content">
    <div class="hero-eyebrow">Automação Comercial · Londrina – PR</div>
    <h1>
      Tecnologia que<br>
      <em>transforma</em> seu<br>
      <span class="outline">restaurante.</span>
    </h1>
    <p class="hero-desc">Mais de 20 anos integrando software, hardware e suporte técnico especializado. Soluções completas para bares, restaurantes, lanchonetes e franquias.</p>
    <div class="hero-btns">
      <a href="#contato" class="btn-primary">Falar com especialista <span class="arrow">→</span></a>
      <a href="#produtos" class="btn-ghost">Ver produtos</a>
    </div>
    <div class="hero-trust">
      <div class="trust-avs">
        <div class="trust-av">🍕</div>
        <div class="trust-av">🍔</div>
        <div class="trust-av">🥩</div>
        <div class="trust-av">🍣</div>
        <div class="trust-av">+</div>
      </div>
      <div class="trust-text">Confiado por <strong>+3.000 PDVs</strong> em todo o Brasil</div>
    </div>
  </div>

  <div class="hero-right">
    <div class="hero-main-card">
      <div class="card-lbl">Anos de Experiência</div>
      <div class="big-num">+20</div>
      <div class="big-desc">Anos no mercado nacional de automação comercial</div>
    </div>
    <div class="mini-grid">
      <div class="mini-card"><div class="mini-val blue">+3k</div><div class="mini-lbl">PDVs instalados</div></div>
      <div class="mini-card"><div class="mini-val teal">Stone</div><div class="mini-lbl">Partner Oficial</div></div>
    </div>
    <div class="support-badge">
      <div class="support-ico">⚡</div>
      <div>
        <h4>Suporte 24/7/365</h4>
        <p>Plantão emergencial disponível todos os dias, incluindo feriados</p>
      </div>
    </div>
  </div>
</section>

<div class="ticker">
  <div class="ticker-track">
    <span class="ticker-item"><span class="tdot"></span>Sagres NFCe</span>
    <span class="ticker-item"><span class="tdot"></span>Prato Digital</span>
    <span class="ticker-item"><span class="tdot"></span>Suporte 24/7</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres Delivery</span>
    <span class="ticker-item"><span class="tdot"></span>Alô Garçom</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres Gestão</span>
    <span class="ticker-item"><span class="tdot"></span>Programa Fidelidade</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres Franquia</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres CRM</span>
    <span class="ticker-item"><span class="tdot"></span>Stone Partner Oficial</span>
    <span class="ticker-item"><span class="tdot"></span>+20 Anos de Mercado</span>
    <span class="ticker-item"><span class="tdot"></span>NFCe · NFe · SEFAZ</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres NFCe</span>
    <span class="ticker-item"><span class="tdot"></span>Prato Digital</span>
    <span class="ticker-item"><span class="tdot"></span>Suporte 24/7</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres Delivery</span>
    <span class="ticker-item"><span class="tdot"></span>Alô Garçom</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres Gestão</span>
    <span class="ticker-item"><span class="tdot"></span>Programa Fidelidade</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres Franquia</span>
    <span class="ticker-item"><span class="tdot"></span>Sagres CRM</span>
    <span class="ticker-item"><span class="tdot"></span>Stone Partner Oficial</span>
    <span class="ticker-item"><span class="tdot"></span>+20 Anos de Mercado</span>
    <span class="ticker-item"><span class="tdot"></span>NFCe · NFe · SEFAZ</span>
  </div>
</div>

<section class="s products-section" id="produtos">
  <div class="products-header">
    <div><div class="s-tag">Portfólio</div><h2 class="s-title">Nossos Produtos</h2></div>
    <p class="s-sub">Soluções integradas para cada etapa — do pedido à gestão financeira e fiscal do seu estabelecimento.</p>
  </div>
  <div class="products-grid">
    <div class="pc feat">
      <div class="pbadge">Destaque</div>
      <div class="pi" style="background:linear-gradient(135deg,#ff6b35,#f7c59f)">🍽️</div>
      <h3>Prato Digital</h3>
      <p>Portal, site, app e weblink completo — Delivery, Retirada, Fura Fila, Eu Que Peço e Programa de Fidelidade em uma única plataforma.</p>
    </div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#1a6fe8,#45aaff22)">🧾</div><h3>Sagres NFCe</h3><p>Modelo 65 — NFC-e com CPF na Nota / Nota Fiscal Paranaense integrada.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#6c63ff,#a29bfe44)">📄</div><h3>Sagres NFe</h3><p>Modelo 55 para entrada, saída, importação, exportação e remessa.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#00b894,#55efc444)">📊</div><h3>Sagres Dash</h3><p>Dashboard mobile com gráficos e indicadores de desempenho em tempo real.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#0984e3,#74b9ff44)">📱</div><h3>Sagres Android</h3><p>App integrado ao NFCe para automatizar pedidos via garçom ou totem.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#e17055,#fab1a044)">🔔</div><h3>Alô Garçom</h3><p>Cardápio virtual e chamada de garçom pelo celular do cliente, sem app.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#fdcb6e,#ffeaa744)">🛵</div><h3>Sagres Delivery</h3><p>Controle de entregas, bina integrada, comissões e status em tempo real.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#a29bfe,#d8d4ff44)">📦</div><h3>Sagres Gestão</h3><p>Estoque, conta assinada, fiado, contas a pagar/receber e financeiro completo.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#fd79a8,#fdcfe444)">🏪</div><h3>Sagres Franquia</h3><p>Comunicação e gestão centralizada entre franqueados e franqueadoras.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#00cec9,#81ecec44)">🔗</div><h3>Sagres Integração</h3><p>Sincronização de vendas, preços e dados entre franqueado e franqueador.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#6c63ff,#a29bfe44)">💬</div><h3>Sagres SMS</h3><p>Notificações automáticas confirmando pedidos e avisos de retirada.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#e17055,#fab1a044)">👨‍🍳</div><h3>Sagres Produção</h3><p>Monitor de cozinha para acompanhar montagem e status dos pedidos.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#0984e3,#74b9ff44)">📅</div><h3>Sagres Encomendas</h3><p>Agendamento e controle de encomendas com avisos automáticos.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#00b894,#55efc444)">📈</div><h3>Sagres Relatórios</h3><p>DRE, DRG, plano de contas, financeiros e operacionais em múltiplos formatos.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#fd79a8,#fdcfe444)">🎯</div><h3>Sagres CRM</h3><p>Frequência, consumo e fidelidade — dados para relacionamento próximo.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#fdcb6e,#ffeaa744)">🏆</div><h3>Prog. Fidelidade</h3><p>Pontos acumulados por consumo trocáveis por produtos do cardápio.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#1a6fe8,#45aaff22)">💳</div><h3>Venda Antecipada</h3><p>Clientes compram créditos e consomem posteriormente com débito automático.</p></div>
    <div class="pc"><div class="pi" style="background:linear-gradient(135deg,#a29bfe,#d8d4ff44)">🖥️</div><h3>Sagres TS</h3><p>Interface touch screen otimizada para operação rápida no balcão.</p></div>
  </div>
</section>

<section class="s why-section" id="porque">
  <div class="why-inner">
    <div>
      <div class="s-tag">Diferenciais</div>
      <h2 class="s-title">Por que escolher a Sagres?</h2>
      <p class="s-sub">Somos mais do que software — somos o parceiro técnico que cuida de tudo para que você foque no seu negócio.</p>
      <div class="why-feats">
        <div class="wf"><span class="wf-num">01</span><div><h4>Atendimento Personalizado</h4><p>Moldamos o sistema para as necessidades do seu estabelecimento. Nada de solução genérica.</p></div></div>
        <div class="wf"><span class="wf-num">02</span><div><h4>Suporte 24/7 com Plantão Emergencial</h4><p>Problemas não escolhem hora. Nossa equipe está disponível todos os dias do ano, incluindo feriados.</p></div></div>
        <div class="wf"><span class="wf-num">03</span><div><h4>Alinhamento Fiscal Completo</h4><p>NFC-e, NF-e, SEFAZ — trabalhamos em conformidade com toda a legislação vigente.</p></div></div>
        <div class="wf"><span class="wf-num">04</span><div><h4>Suporte Online em Tempo Real</h4><p>Conexão remota imediata, backups locais e em nuvem, e acompanhamento pós-instalação.</p></div></div>
        <div class="wf"><span class="wf-num">05</span><div><h4>Sistemas Totalmente Integrados</h4><p>PDV, gestão, delivery, fidelidade, produção — um ecossistema coeso e sem conflitos.</p></div></div>
      </div>
    </div>
    <div class="why-vis">
      <div class="why-card">
        <div class="wct">Especialidades e Serviços</div>
        <div class="chips">
          <span class="chip">Atendimento Personalizado</span><span class="chip">Treinamentos</span>
          <span class="chip">Suporte 24/7/365</span><span class="chip">Sistemas Integrados</span>
          <span class="chip">Backups Local & Nuvem</span><span class="chip">Acesso Remoto</span>
          <span class="chip">Análise de Demanda</span><span class="chip">Controle de Estoque</span>
          <span class="chip">Compatível com Mobile</span><span class="chip">Pós-instalação</span>
          <span class="chip">NFC-e & NF-e</span><span class="chip">Conta Assinada</span>
        </div>
        <hr class="wdiv">
        <div class="wct">Aplicativos Disponíveis</div>
        <div class="apps-row">
          <div class="arc"><h5>Sagres Dash</h5><span>Relatórios e gráficos mobile</span><div class="slinks"><a class="sl" href="https://itunes.apple.com/us/app/sagres-dash/id1407831060?mt=8" target="_blank">App Store</a><a class="sl" href="https://play.google.com/store/apps/details?id=br.com.sagresinformatica.sagresreport" target="_blank">Play Store</a></div></div>
          <div class="arc"><h5>Prato Digital</h5><span>Delivery, fidelidade e mais</span><div class="slinks"><a class="sl" href="https://apps.apple.com/br/app/prato-digital/id1476417358" target="_blank">App Store</a><a class="sl" href="https://play.google.com/store/apps/details?id=br.com.sagresinformatica.prato_digital" target="_blank">Play Store</a></div></div>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="s about-section" id="sobre">
  <div class="about-inner">
    <div class="aqc">
      <span class="bq">"</span>
      <p class="aqt"><strong>Sagres Informática</strong> nasceu diante da necessidade do mercado em ter a <strong>solução completa</strong> integrando serviços, hardware e software. Com isso deixamos os nossos clientes tranquilos com a infra-estrutura de tecnologia da sua empresa.<br><br>Trabalhamos também alinhados com a <strong>legislação fiscal vigente</strong> evitando futuros problemas contábeis para nossos clientes. O suporte é composto por colaboradores treinados e atenciosos que estão sempre prontos para solucionar diversas dúvidas e solicitações dos clientes tornando o atendimento mais rápido e eficiente.<br><br>Se você busca uma empresa sólida, com <strong>20 anos de atividades no mercado Nacional</strong>, venha nos fazer uma visita e teremos o maior prazer em atendê-los.<br><br>E se você, profissional de Tecnologia da Informação, tiver interesse em fazer parte de nossa história, <a href="mailto:rh@sagresinformatica.com.br" style="color:var(--accent2);text-decoration:underline;font-style:normal;font-weight:600;">trabalhe conosco</a> e venha fazer parte de nossa equipe de colaboradores. Envie-nos seu currículo.</p>
      <div class="ametrics">
        <div class="ambox"><div class="amval">+20</div><div class="amlbl">Anos no mercado</div></div>
        <div class="ambox"><div class="amval">+3k</div><div class="amlbl">PDVs instalados</div></div>
        <div class="ambox"><div class="amval">24/7</div><div class="amlbl">Suporte disponível</div></div>
        <div class="ambox"><div class="amval">100%</div><div class="amlbl">Foco no cliente</div></div>
      </div>
    </div>
    <div class="atcol">
      <div class="s-tag">Nossa História</div>
      <h2 class="s-title">Uma empresa construída por décadas de dedicação</h2>
      <p class="s-sub">Desde o início, nossa missão é ser o parceiro tecnológico que você pode confiar — com solidez, expertise e um time humano que se importa.</p>
      <div class="timeline">
        <div class="ti"><div><h4>Fundação da Sagres</h4><p>Criada em Londrina/PR com o objetivo de oferecer automação comercial completa ao mercado de food service.</p></div></div>
        <div class="ti"><div><h4>Expansão Nacional</h4><p>Crescimento para mais de 3.000 PDVs instalados em todo o Brasil, atendendo restaurantes, franquias e redes.</p></div></div>
        <div class="ti"><div><h4>Lançamento do Prato Digital</h4><p>Plataforma completa de delivery, fidelidade e autoatendimento — unindo o físico ao digital.</p></div></div>
        <div class="ti"><div><h4>Parceria Stone & Sagres Cloud</h4><p>Tornamo-nos Partner Oficial Stone e lançamos o Sagres Cloud para gestão 100% online em tempo real.</p></div></div>
      </div>
    </div>
  </div>
</section>

<section class="s contact-section" id="contato">
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:start;">
    <div>
      <div class="s-tag">Fale Conosco</div>
      <h2 class="s-title">Vamos conversar?</h2>
      <p class="s-sub">Nossa equipe está pronta para apresentar a melhor solução para o seu estabelecimento. Sem compromisso.</p>

      <div class="ccards">
        <div class="cc"><span class="cci">📍</span><div><h4>Endereço</h4><p>Rua João Wyclif, 111 — Sala 208<br>Gleba Fazenda Palhano · Londrina/PR</p></div></div>
        <div class="cc"><span class="cci">📞</span><div><h4>Telefone Fixo</h4><a href="https://wa.me/554333388099" target="_blank" rel="noopener">43 3338-8099</a></div></div>
        <div class="cc"><span class="cci">🌙</span><div><h4>Plantão 24h</h4><a href="https://wa.me/554399962360" target="_blank" rel="noopener">43 9 9996-2360</a></div></div>
        <div class="cc"><span class="cci">📱</span><div><h4>Celular</h4><a href="https://wa.me/554398817368" target="_blank" rel="noopener">43 9 8817-3683</a></div></div>
        <div class="cc"><span class="cci">💼</span><div><h4>Trabalhe Conosco</h4><a href="mailto:rh@sagresinformatica.com.br">Envie seu currículo →</a></div></div>
      </div>

      <div style="margin-top:2rem;">
        <p style="font-size:0.82rem;color:var(--muted);margin-bottom:1rem;">Acesse sua conta diretamente na plataforma:</p>
        <a href="https://sagrescloud.com.br/" class="btn-primary" target="_blank" style="display:inline-flex">Acessar Sagres Cloud <span class="arrow">→</span></a>
      </div>
    </div>

    <div class="map-wrap">
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3668.1!2d-51.1766!3d-23.3315!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ecd4a13232de45%3A0xbc7682a9e5b06b65!2sRua+Jo%C3%A3o+Wyclif%2C+111+-+Gleba+Fazenda+Palhano%2C+Londrina+-+PR%2C+86050-450!5e0!3m2!1spt!2sbr!4v1700000000000" allowfullscreen loading="lazy"></iframe>
    </div>
  </div>
</section>

<section class="s" id="clientes" style="background:var(--bg);border-top:1px solid var(--border);">
  <div style="text-align:center;margin-bottom:3rem;">
    <div class="s-tag" style="justify-content:center;">Clientes</div>
    <h2 class="s-title">Quem confia na Sagres</h2>
    <p class="s-sub" style="margin:0 auto;">Restaurantes, lanchonetes, pizzarias, churrascarias e muito mais em Londrina e região.</p>
  </div>

  <div class="logos-grid">
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/hamburguersP.jpg" alt="Hamburguers"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/zelanches.png" alt="Zé Lanches"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/dalicencaP.jpg" alt="Dá Licença"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/galpaonelore.png" alt="Galpão Nelore"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/pastelmelP.png" alt="Pastel Mel"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/donatelloL.jpg" alt="Donatello"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/lagondolaP.jpg" alt="La Gondola"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/borelP.png" alt="Borel"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/picwichP.png" alt="PicWich"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/bambuzaP.png" alt="Bambuza"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/robsP.png" alt="Robs"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/dogkingP.jpg" alt="Dog King"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/jetP.png" alt="Jet Chicken"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/kiberamaP.png" alt="Kiberama"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/viraP.png" alt="Vira Lanches"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/pizzaMovieP.jpg" alt="Pizza Movie"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/jinjin.png" alt="JinJin Wok"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/piubellaP.png" alt="Piu Bella"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/pizzaClubP.png" alt="Pizza Club"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/chikP.png" alt="Chik"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/nortesul.png" alt="Norte Sul"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/gelobelLogo.jpg" alt="Gelobel"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/pizzamaisP.png" alt="Pizza Mais"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/TortasAlemasP.png" alt="Tortas Alemãs"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/moinhoP.png" alt="Moinho"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/nacaoP.png" alt="Nação"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/limoziniP.png" alt="Limozini"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/chimarraoP.png" alt="Chimarrão"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/chimarraoGrillP.png" alt="Chimarrão Grill"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/valentinoP.jpg" alt="Valentino"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/arnaldo.jpg" alt="Arnaldo"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/pandorP.png" alt="Pandor"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/limoniziGrillP.png" alt="Limonizi Grill"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/prosperidadeP.jpg" alt="Prosperidade"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/freddoP.png" alt="Freddo"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/palhano.jpg" alt="Palhano"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/ventosulP.png" alt="Vento Sul"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/rioP.jpg" alt="Rio Branco"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/hachimitsu.png" alt="Hachimitsu"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/zanoniP.jpg" alt="Zanoni"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/cucaP.jpg" alt="Cuca"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/ilhabela.jpg" alt="Ilha Bela"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/2800.jpg" alt="2800"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/casadasmalhas.jpg" alt="Casa das Malhas"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/feijuca_grillP.jpg" alt="Feijuca Grill"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/hightec.png" alt="Hightec"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/milane.png" alt="Milane"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/bompaladar.png" alt="Bom Paladar"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/patio_san_miguelP.jpg" alt="Pátio San Miguel"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/bollognaP.png" alt="Bollogna"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/h2choppP.jpg" alt="H2 Chopp"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/moinho_grillP.png" alt="Moinho Grill"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/kozanP.png" alt="Kozan"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/geronimoP.jpg" alt="Geronimo"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/ishikawaP.jpg" alt="Ishikawa"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/meuchefP.png" alt="Meu Chef"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/losmutacosP.jpg" alt="Los Mutacos"></div>
    <div class="logo-card"><img src="https://www.sagresinformatica.com.br/img/logoClientes/londrina/kerokeryP.png" alt="Kerokery"></div>
  </div>
</section>

<style>
.logos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
  gap: .7rem;
}
.logo-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: .8rem;
  display: flex; align-items: center; justify-content: center;
  height: 90px;
  overflow: hidden;
  transition: border-color .2s, transform .2s, background .2s;
}
.logo-card:hover {
  border-color: rgba(26,111,232,0.3);
  background: #0f1c32;
  transform: translateY(-3px);
}
.logo-card img {
  max-width: 100%; max-height: 100%;
  object-fit: contain;
  filter: grayscale(0.3) brightness(0.9);
  transition: filter .2s;
}
.logo-card:hover img {
  filter: grayscale(0) brightness(1.05);
}
</style>

<footer>
  <div class="foot-inner">
    <div class="fbrand">
      <div class="nav-logo"><div class="nav-dot"></div>SAGRES</div>
      <p>Automação comercial completa para restaurantes, bares, lanchonetes e franquias. Mais de 20 anos transformando negócios com tecnologia e suporte de excelência.</p>
    </div>
    <div class="fcol">
      <h5>Produtos</h5>
      <a href="#">Sagres NFCe</a><a href="#">Prato Digital</a><a href="#">Sagres Delivery</a>
      <a href="#">Sagres Gestão</a><a href="#">Sagres Dash</a><a href="#">Sagres Franquia</a>
    </div>
    <div class="fcol">
      <h5>Empresa</h5>
      <a href="#sobre">Sobre nós</a>
      <a href="https://sagrescloud.com.br/" target="_blank">Sagres Cloud</a>
      <a href="http://www.pratodigital.com.br" target="_blank">Prato Digital</a>
      <a href="mailto:rh@sagresinformatica.com.br">Trabalhe Conosco</a>
    </div>
  </div>
</footer>

</body>
</html>
