[index.html](https://github.com/user-attachments/files/28737521/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>RehabPro | Protocolos de Rehabilitación</title>
  <style>
    /* ── RESET & BASE ── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --navy:   #0d2b45;
      --teal:   #1a7f74;
      --teal2:  #22a99a;
      --accent: #f0a500;
      --light:  #f4f8fb;
      --white:  #ffffff;
      --gray:   #6b7a8d;
      --dark:   #1c2b3a;
      --radius: 12px;
      --shadow: 0 4px 24px rgba(13,43,69,.12);
    }
    html { scroll-behavior: smooth; }
    body {
      font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
      background: var(--white);
      color: var(--dark);
      line-height: 1.65;
    }
    a { text-decoration: none; color: inherit; }
    img { max-width: 100%; }

    /* ── NAV ── */
    nav {
      position: sticky; top: 0; z-index: 999;
      background: var(--white);
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%;
      height: 70px;
      box-shadow: 0 2px 12px rgba(0,0,0,.10);
      border-bottom: 2px solid #e8f0f7;
    }
    .logo img {
      height: 50px;
      width: auto;
      display: block;
      border-radius: 8px;
    }
    .nav-links { display: flex; gap: 28px; align-items: center; }
    .nav-links a {
      color: var(--navy); font-size: .9rem; font-weight: 500;
      transition: color .2s;
    }
    .nav-links a:hover { color: var(--teal2); }
    .nav-cta {
      background: var(--teal2); color: var(--white) !important;
      padding: 8px 20px; border-radius: 30px; font-weight: 700 !important;
      transition: background .2s !important;
    }
    .nav-cta:hover { background: var(--accent) !important; color: var(--navy) !important; }

    /* ── HERO ── */
    .hero {
      background: linear-gradient(135deg, var(--navy) 0%, #134e6f 60%, var(--teal) 100%);
      color: var(--white);
      padding: 90px 5% 80px;
      text-align: center;
      position: relative; overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute; inset: 0;
      background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.04'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    }
    .hero-badge {
      display: inline-block;
      background: rgba(255,255,255,.12);
      border: 1px solid rgba(255,255,255,.25);
      color: var(--teal2); font-size: .8rem; font-weight: 700;
      padding: 5px 16px; border-radius: 30px;
      margin-bottom: 20px; letter-spacing: 1px; text-transform: uppercase;
    }
    .hero h1 {
      font-size: clamp(2rem, 5vw, 3.4rem);
      font-weight: 900; line-height: 1.15;
      margin-bottom: 20px;
    }
    .hero h1 span { color: var(--accent); }
    .hero p {
      font-size: 1.1rem; max-width: 640px; margin: 0 auto 36px;
      color: rgba(255,255,255,.85);
    }
    .hero-btns { display: flex; gap: 14px; justify-content: center; flex-wrap: wrap; }
    .btn-primary {
      background: var(--accent); color: var(--navy);
      padding: 14px 34px; border-radius: 30px; font-weight: 800;
      font-size: 1rem; transition: transform .2s, box-shadow .2s;
      box-shadow: 0 4px 18px rgba(240,165,0,.4);
    }
    .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(240,165,0,.5); }
    .btn-outline {
      border: 2px solid rgba(255,255,255,.5); color: var(--white);
      padding: 14px 34px; border-radius: 30px; font-weight: 700;
      font-size: 1rem; transition: background .2s;
    }
    .btn-outline:hover { background: rgba(255,255,255,.1); }

    .hero-stats {
      display: flex; justify-content: center; gap: 48px;
      margin-top: 56px; flex-wrap: wrap;
    }
    .stat { text-align: center; }
    .stat-num { font-size: 2rem; font-weight: 900; color: var(--accent); }
    .stat-lbl { font-size: .8rem; color: rgba(255,255,255,.7); text-transform: uppercase; letter-spacing: .5px; }

    /* ── SECTIONS ── */
    section { padding: 80px 5%; }
    .section-tag {
      display: inline-block; background: var(--teal2); color: var(--white);
      font-size: .75rem; font-weight: 700; padding: 4px 14px;
      border-radius: 30px; letter-spacing: 1px; text-transform: uppercase;
      margin-bottom: 12px;
    }
    h2 {
      font-size: clamp(1.6rem, 3.5vw, 2.4rem);
      font-weight: 800; color: var(--navy); margin-bottom: 12px;
    }
    .section-subtitle {
      font-size: 1.05rem; color: var(--gray); max-width: 580px; margin-bottom: 48px;
    }

    /* ── PATOLOGÍAS ── */
    #patologias { background: var(--light); }
    .patho-tabs {
      display: flex; gap: 12px; margin-bottom: 36px; flex-wrap: wrap;
    }
    .tab-btn {
      padding: 10px 24px; border-radius: 30px; border: 2px solid #d1dce8;
      background: var(--white); color: var(--navy); font-weight: 700; cursor: pointer;
      transition: all .2s; font-size: .9rem;
    }
    .tab-btn.active, .tab-btn:hover {
      background: var(--teal); border-color: var(--teal); color: var(--white);
    }
    .tab-panel { display: none; }
    .tab-panel.active { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px,1fr)); gap: 20px; }
    .patho-card {
      background: var(--white); border-radius: var(--radius);
      padding: 24px; box-shadow: var(--shadow);
      border-left: 4px solid var(--teal2);
      transition: transform .2s;
    }
    .patho-card:hover { transform: translateY(-4px); }
    .patho-icon { font-size: 2rem; margin-bottom: 10px; }
    .patho-card h3 { font-size: 1rem; font-weight: 700; color: var(--navy); margin-bottom: 6px; }
    .patho-card p { font-size: .87rem; color: var(--gray); }
    .patho-badge {
      display: inline-block; background: var(--light); color: var(--teal);
      font-size: .72rem; font-weight: 700; padding: 3px 10px;
      border-radius: 20px; margin-top: 10px;
    }

    /* ── PROTOCOLOS / TIENDA ── */
    #protocolos { background: var(--light); }
    /* ── BIBLIOTECA COMPLETA ── */
    .library-banner {
      background: linear-gradient(135deg, #1a1a2e, #16213e, #0f3460);
      border-radius: 20px; padding: 36px 40px;
      display: flex; align-items: center; justify-content: space-between;
      gap: 24px; margin-bottom: 40px; flex-wrap: wrap;
      box-shadow: 0 8px 40px rgba(0,0,0,.25);
      position: relative; overflow: hidden;
    }
    .library-banner::before {
      content: ''; position: absolute; top: -40px; right: -40px;
      width: 200px; height: 200px; border-radius: 50%;
      background: rgba(34,169,154,.15);
    }
    .library-badge {
      background: var(--accent); color: var(--navy);
      font-size: .72rem; font-weight: 900; text-transform: uppercase;
      letter-spacing: 1px; padding: 4px 12px; border-radius: 20px;
      display: inline-block; margin-bottom: 10px;
    }
    .library-banner h3 { color: #fff; font-size: 1.5rem; font-weight: 900; margin-bottom: 6px; }
    .library-banner p { color: rgba(255,255,255,.7); font-size: .9rem; }
    .library-price-block { text-align: center; flex-shrink: 0; }
    .library-old-price { color: rgba(255,255,255,.4); text-decoration: line-through; font-size: .9rem; }
    .library-new-price { color: var(--accent); font-size: 2.2rem; font-weight: 900; line-height: 1; }
    .library-new-price span { font-size: 1rem; font-weight: 500; color: rgba(255,255,255,.7); }
    .library-saving { background: #22a99a; color: #fff; font-size: .75rem; font-weight: 800;
      border-radius: 20px; padding: 3px 10px; margin-top: 6px; display: inline-block; }
    .library-btn {
      background: var(--accent); color: var(--navy); border: none;
      padding: 14px 32px; border-radius: 30px; font-size: 1rem; font-weight: 900;
      cursor: pointer; transition: transform .2s, box-shadow .2s; white-space: nowrap;
      box-shadow: 0 4px 18px rgba(240,165,0,.4);
    }
    .library-btn:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(240,165,0,.5); }
    /* ── PACK DE CATEGORÍA ── */
    .pack-card {
      grid-column: 1 / -1;
      background: linear-gradient(135deg, #0d2b45, #1a5276);
      border-radius: var(--radius); padding: 24px 28px;
      display: flex; align-items: center; justify-content: space-between;
      gap: 20px; flex-wrap: wrap;
      box-shadow: 0 4px 20px rgba(13,43,69,.2);
    }
    .pack-card-info h4 { color: #fff; font-size: 1.05rem; font-weight: 800; margin-bottom: 4px; }
    .pack-card-info p { color: rgba(255,255,255,.65); font-size: .83rem; }
    .pack-price-block { display: flex; align-items: center; gap: 14px; flex-wrap: wrap; }
    .pack-old { color: rgba(255,255,255,.4); text-decoration: line-through; font-size: .9rem; }
    .pack-new { color: var(--accent); font-size: 1.6rem; font-weight: 900; }
    .pack-save { background: #22a99a; color: #fff; font-size: .72rem; font-weight: 800;
      border-radius: 20px; padding: 3px 10px; }
    .pack-buy-btn {
      background: var(--accent); color: var(--navy); border: none;
      padding: 12px 28px; border-radius: 30px; font-size: .95rem; font-weight: 800;
      cursor: pointer; transition: transform .2s; white-space: nowrap;
    }
    .pack-buy-btn:hover { transform: translateY(-2px); }
    /* ── TARJETAS INDIVIDUALES ── */
    .products-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(280px,1fr));
      gap: 20px; margin-top: 12px;
    }
    .product-card {
      border-radius: var(--radius); overflow: hidden;
      box-shadow: var(--shadow); border: 1px solid #e2eaf2;
      background: #fff;
      transition: transform .2s, box-shadow .2s;
      display: flex; flex-direction: column;
    }
    .product-card:hover { transform: translateY(-6px); box-shadow: 0 12px 36px rgba(13,43,69,.16); }
    .product-header {
      background: linear-gradient(135deg, var(--navy), #1a5276);
      padding: 28px 24px 20px;
      position: relative;
    }
    .product-header.sport  { background: linear-gradient(135deg, #0d3b6e, #1a6ea8); }
    .product-header.clinic { background: linear-gradient(135deg, #0d4535, var(--teal)); }
    .product-category {
      font-size: .72rem; font-weight: 700; color: rgba(255,255,255,.7);
      text-transform: uppercase; letter-spacing: 1px; margin-bottom: 8px;
    }
    .product-header h3 {
      color: var(--white); font-size: 1.15rem; font-weight: 800;
    }
    .product-price {
      position: absolute; top: 20px; right: 20px;
      background: var(--accent); color: var(--navy);
      font-size: 1.1rem; font-weight: 900;
      padding: 6px 14px; border-radius: 20px;
    }
    .product-body { padding: 20px 24px; flex: 1; display: flex; flex-direction: column; }
    .product-body p { font-size: .9rem; color: var(--gray); margin-bottom: 14px; flex: 1; }
    .product-features { list-style: none; margin-bottom: 20px; }
    .product-features li {
      font-size: .85rem; color: var(--dark); padding: 4px 0;
      display: flex; align-items: flex-start; gap: 8px;
    }
    .product-features li::before { content: '✓'; color: var(--teal2); font-weight: 900; }
    .paypal-form { margin-top: auto; }
    .paypal-btn {
      display: flex; align-items: center; justify-content: center; gap: 10px;
      width: 100%; padding: 13px;
      background: #0070ba; color: var(--white);
      border: none; border-radius: 8px; cursor: pointer;
      font-size: .95rem; font-weight: 700;
      transition: background .2s; text-decoration: none;
    }
    .paypal-btn:hover { background: #003087; }
    .paypal-btn svg { width: 20px; height: 20px; }

    /* ── CÓMO FUNCIONA ── */
    #como-funciona { background: var(--light); }
    .steps { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px,1fr)); gap: 32px; margin-top: 12px; }
    .step { text-align: center; }
    .step-num {
      width: 56px; height: 56px; border-radius: 50%;
      background: var(--teal); color: var(--white);
      font-size: 1.4rem; font-weight: 900;
      display: flex; align-items: center; justify-content: center;
      margin: 0 auto 16px;
    }
    .step h3 { font-size: 1rem; font-weight: 700; color: var(--navy); margin-bottom: 6px; }
    .step p { font-size: .88rem; color: var(--gray); }

    /* ── SOBRE MÍ ── */
    #sobre-mi { background: var(--navy); color: var(--white); }
    #sobre-mi h2 { color: var(--white); }
    .photo-gallery {
      display: grid; grid-template-columns: repeat(3,1fr); gap: 12px; margin-top: 36px;
    }
    .photo-gallery img {
      width: 100%; aspect-ratio: 1; object-fit: cover;
      border-radius: 12px; border: 2px solid rgba(255,255,255,.1);
      transition: transform .3s, border-color .3s;
    }
    .photo-gallery img:hover { transform: scale(1.03); border-color: var(--teal2); }
    .about-grid {
      display: grid; grid-template-columns: 1fr 2fr; gap: 56px; align-items: center;
    }
    .about-avatar {
      width: 220px; height: 220px; border-radius: 50%;
      background: var(--teal); display: flex; align-items: center; justify-content: center;
      font-size: 5rem; margin: 0 auto;
      border: 5px solid var(--teal2);
      box-shadow: 0 0 0 12px rgba(34,169,154,.15);
      overflow: hidden;
    }
    .about-avatar img { width: 100%; height: 100%; object-fit: cover; }
    .about-champion {
      display: flex; align-items: center; gap: 10px;
      background: linear-gradient(135deg, #f0a500, #d4890a);
      border-radius: 30px; padding: 8px 18px; margin-bottom: 18px;
      width: fit-content;
    }
    .about-champion span { font-weight: 800; font-size: .88rem; color: #1c2b3a; }
    .about-stats { display: grid; grid-template-columns: repeat(3,1fr); gap: 16px; margin: 20px 0; }
    .about-stat { text-align: center; background: rgba(255,255,255,.08); border-radius: 10px; padding: 14px 8px; }
    .about-stat strong { display: block; font-size: 1.5rem; font-weight: 900; color: #22a99a; }
    .about-stat span { font-size: .75rem; color: rgba(255,255,255,.65); }
    .about-text p { color: rgba(255,255,255,.8); margin-bottom: 16px; }
    .credentials { display: flex; gap: 12px; flex-wrap: wrap; margin-top: 20px; }
    .cred {
      background: rgba(255,255,255,.1); border: 1px solid rgba(255,255,255,.2);
      padding: 8px 18px; border-radius: 20px;
      font-size: .82rem; color: rgba(255,255,255,.9); font-weight: 600;
    }

    /* ── GARANTÍA ── */
    .guarantee {
      background: linear-gradient(135deg, var(--teal) 0%, var(--teal2) 100%);
      color: var(--white); text-align: center; padding: 60px 5%;
    }
    .guarantee h2 { color: var(--white); font-size: 1.8rem; }
    .guarantee p { color: rgba(255,255,255,.85); max-width: 540px; margin: 12px auto 0; }
    .guarantee-icon { font-size: 3.5rem; margin-bottom: 16px; }

    /* ── CONTACTO ── */
    #contacto { background: var(--light); }
    .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 48px; align-items: start; }
    .contact-info h3 { font-size: 1.2rem; font-weight: 700; color: var(--navy); margin-bottom: 16px; }
    .contact-item {
      display: flex; align-items: flex-start; gap: 14px; margin-bottom: 20px;
    }
    .contact-icon {
      width: 42px; height: 42px; min-width: 42px;
      background: var(--teal2); border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.1rem;
    }
    .contact-item p { font-size: .9rem; color: var(--gray); }
    .contact-item strong { display: block; color: var(--dark); }
    .contact-form { background: var(--white); border-radius: var(--radius); padding: 32px; box-shadow: var(--shadow); }
    .contact-form h3 { font-size: 1.1rem; font-weight: 700; color: var(--navy); margin-bottom: 20px; }
    .form-group { margin-bottom: 16px; }
    label { font-size: .85rem; font-weight: 600; color: var(--dark); margin-bottom: 6px; display: block; }
    input, textarea, select {
      width: 100%; padding: 11px 14px; border: 1.5px solid #d1dce8;
      border-radius: 8px; font-size: .9rem; font-family: inherit;
      transition: border-color .2s; outline: none;
    }
    input:focus, textarea:focus, select:focus { border-color: var(--teal2); }
    textarea { resize: vertical; min-height: 110px; }
    .btn-submit {
      width: 100%; padding: 13px; background: var(--teal);
      color: var(--white); border: none; border-radius: 8px;
      font-size: 1rem; font-weight: 700; cursor: pointer;
      transition: background .2s;
    }
    .btn-submit:hover { background: var(--navy); }

    /* ── FOOTER ── */
    footer {
      background: var(--dark); color: rgba(255,255,255,.6);
      text-align: center; padding: 32px 5%; font-size: .85rem;
    }
    footer a { color: var(--teal2); }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      .about-grid { grid-template-columns: 1fr; }
      .contact-grid { grid-template-columns: 1fr; }
      .nav-links { display: none; }
      .hero-stats { gap: 28px; }
    }
  </style>
  <script src="https://www.paypal.com/sdk/js?client-id=AT31BJNpfy1Ad1MS19OrLkkK-AuwjHCwASSGS01HghuEdbc7UFMiKwvnA_8xo-TPeBVUNSVw2OYnH-am&currency=MXN"></script>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo"><img src="logo.png" alt="Relavitat" /></div>
  <div class="nav-links">
    <a href="#patologias">Patologías</a>
    <a href="#protocolos">Protocolos</a>
    <a href="#como-funciona">Cómo funciona</a>
    <a href="#sobre-mi">Sobre mí</a>
    <a href="#protocolos" class="nav-cta">Comprar ahora</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-badge">✦ Fisioterapia basada en evidencia</div>
  <h1>Protocolos de Rehabilitación<br><span>Clínica y Deportiva</span></h1>
  <p>Guías clínicas estructuradas, listas para aplicar, diseñadas por especialistas para las patologías más frecuentes en fisioterapia.</p>
  <div class="hero-btns">
    <a href="#protocolos" class="btn-primary">Ver protocolos →</a>
    <a href="#patologias" class="btn-outline">Conocer más</a>
  </div>
  <div class="hero-stats">
    <div class="stat"><div class="stat-num">35+</div><div class="stat-lbl">Protocolos</div></div>
    <div class="stat"><div class="stat-num">8</div><div class="stat-lbl">Carpetas temáticas</div></div>
    <div class="stat"><div class="stat-num">PDF</div><div class="stat-lbl">Descarga inmediata</div></div>
    <div class="stat"><div class="stat-num">$159</div><div class="stat-lbl">MXN por carpeta</div></div>
  </div>
</section>

<!-- PATOLOGÍAS -->
<section id="patologias">
  <div class="section-tag">Áreas de especialidad</div>
  <h2>Patologías más frecuentes</h2>
  <p class="section-subtitle">Protocolos desarrollados para las condiciones que más ves en consulta, tanto en el ámbito deportivo como en la práctica clínica general.</p>

  <div class="patho-tabs">
    <button class="tab-btn active" onclick="switchTab('deporte', this)">🏅 Deporte</button>
    <button class="tab-btn" onclick="switchTab('clinica', this)">🏥 Clínica</button>
  </div>

  <!-- DEPORTE -->
  <div class="tab-panel active" id="tab-deporte">
    <div class="patho-card">
      <div class="patho-icon">🦵</div>
      <h3>Lesión de LCA (Ligamento Cruzado Anterior)</h3>
      <p>Protocolo completo desde la fase aguda hasta el retorno deportivo, con criterios objetivos de progresión.</p>
      <span class="patho-badge">Rodilla</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🦶</div>
      <h3>Esguince de tobillo</h3>
      <p>Manejo del esguince grado I-III, trabajo propioceptivo y prevención de recurrencias.</p>
      <span class="patho-badge">Tobillo</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">💪</div>
      <h3>Lesión del manguito rotador</h3>
      <p>Rehabilitación de desgarros parciales y totales con fases progresivas de fortalecimiento.</p>
      <span class="patho-badge">Hombro</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🏃</div>
      <h3>Tendinopatía rotuliana</h3>
      <p>Protocolo de carga excéntrica y progresión funcional para el tendón rotuliano.</p>
      <span class="patho-badge">Rodilla</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🦿</div>
      <h3>Distensión de isquiotibiales</h3>
      <p>Retorno seguro al deporte tras lesión muscular de isquiotibiales con criterios funcionales.</p>
      <span class="patho-badge">Muslo</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🩹</div>
      <h3>Pubalgia del deportista</h3>
      <p>Abordaje multidisciplinar de la pubalgia con énfasis en la zona central y aductores.</p>
      <span class="patho-badge">Cadera / Core</span>
    </div>
  </div>

  <!-- CLÍNICA -->
  <div class="tab-panel" id="tab-clinica">
    <div class="patho-card">
      <div class="patho-icon">🔙</div>
      <h3>Dolor lumbar crónico</h3>
      <p>Abordaje biopsicosocial con ejercicio terapéutico, educación en dolor y estrategias de autogestión.</p>
      <span class="patho-badge">Columna lumbar</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🦴</div>
      <h3>Osteoartritis de rodilla</h3>
      <p>Programa conservador basado en ejercicio para la gonalgia, con manejo del dolor y función.</p>
      <span class="patho-badge">Rodilla</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🫀</div>
      <h3>Cervicalgia mecánica</h3>
      <p>Terapia manual, ejercicio cervical y corrección postural para el dolor cervical inespecífico.</p>
      <span class="patho-badge">Columna cervical</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🤲</div>
      <h3>Síndrome del túnel carpiano</h3>
      <p>Rehabilitación conservadora con movilización nerviosa, férulas y ejercicios de deslizamiento.</p>
      <span class="patho-badge">Muñeca / Mano</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🦾</div>
      <h3>Hombro doloroso</h3>
      <p>Síndrome de pinzamiento subacromial: protocolo de movilidad, fuerza y control motor escapular.</p>
      <span class="patho-badge">Hombro</span>
    </div>
    <div class="patho-card">
      <div class="patho-icon">🧠</div>
      <h3>Fibromialgia</h3>
      <p>Programa de ejercicio aeróbico, estiramientos y educación en neurociencia del dolor.</p>
      <span class="patho-badge">Sistémico</span>
    </div>
  </div>
</section>

<!-- Modal de ÉXITO (descarga) -->
<div id="success-modal" style="display:none; position:fixed; inset:0; background:rgba(0,0,0,.7); z-index:9999; align-items:center; justify-content:center;">
  <div style="background:#fff; border-radius:16px; padding:36px 28px; max-width:420px; width:90%; text-align:center; position:relative;">
    <button onclick="document.getElementById('success-modal').style.display='none'" style="position:absolute; top:12px; right:16px; background:none; border:none; font-size:1.4rem; cursor:pointer; color:#666;">✕</button>
    <div style="font-size:3rem; margin-bottom:12px;">🎉</div>
    <h3 style="color:#0d2b45; font-size:1.3rem; margin-bottom:8px;">¡Pago completado!</h3>
    <p style="color:#6b7a8d; font-size:.9rem; margin-bottom:24px;">Tu compra fue exitosa. Haz clic en el botón para acceder a tu carpeta en Google Drive.</p>
    <a id="success-link" href="#" target="_blank"
      style="display:block; background:#22a99a; color:#fff; padding:14px; border-radius:10px; font-weight:800; font-size:1rem; text-decoration:none; margin-bottom:12px;">
      📥 Descargar mis protocolos →
    </a>
    <p style="font-size:.78rem; color:#6b7a8d;">Guarda el enlace. También puedes contactarnos a <a href="mailto:alwaysnano1@gmail.com" style="color:#1a7f74;">alwaysnano1@gmail.com</a></p>
  </div>
</div>

<!-- Modal de compra -->
<div id="buy-modal" style="display:none; position:fixed; inset:0; background:rgba(0,0,0,.7); z-index:9999; align-items:center; justify-content:center;">
  <div style="background:#fff; border-radius:16px; padding:32px; max-width:420px; width:90%; text-align:center; position:relative;">
    <button onclick="closeModal()" style="position:absolute; top:12px; right:16px; background:none; border:none; font-size:1.4rem; cursor:pointer; color:#666;">✕</button>
    <div style="font-size:2.5rem; margin-bottom:8px;" id="modal-icon">📄</div>
    <h3 id="modal-title" style="color:#0d2b45; margin-bottom:4px; font-size:1.1rem;"></h3>
    <p style="color:#6b7a8d; font-size:.85rem; margin-bottom:16px;">Protocolo de Rehabilitación · PDF</p>
    <div id="modal-price" style="font-size:1.6rem; font-weight:900; color:#0d2b45; margin-bottom:20px;"></div>
    <div id="paypal-modal-btn"></div>
  </div>
</div>

<!-- PROTOCOLOS -->
<section id="protocolos">
  <div class="section-tag">Tienda</div>
  <h2>Protocolos de Rehabilitación</h2>
  <p class="section-subtitle">8 carpetas temáticas con todos los protocolos incluidos. Descarga inmediata vía Google Drive.</p>

  <!-- BANNER BIBLIOTECA COMPLETA -->
  <div class="library-banner">
    <div>
      <span class="library-badge">⭐ Mejor valor</span>
      <h3>Biblioteca Completa — 8 Carpetas · 35+ Protocolos</h3>
      <p>Todo el catálogo en un solo pago. Columna, hombro, rodilla, neurológico y más.<br>Años de experiencia clínica y deportiva resumidos en protocolos listos para aplicar.</p>
    </div>
    <div class="library-price-block">
      <div class="library-old-price">$1,272 MXN valor individual</div>
      <div class="library-new-price">$999 <span>MXN</span></div>
      <div class="library-saving">Ahorras $273 · 21% OFF</div>
    </div>
    <button class="library-btn" onclick="openModal('Biblioteca Completa — 8 Carpetas Rehavitat','📚','999.00','ALL')">
      🛒 Comprar biblioteca completa
    </button>
  </div>

  <!-- GRID DE 8 CARPETAS -->
  <div class="products-grid" id="carpetas-grid">
    <!-- Generado por JavaScript -->
  </div>
</section>

<!-- CÓMO FUNCIONA -->
<section id="como-funciona">
  <div class="section-tag">Proceso</div>
  <h2>¿Cómo funciona?</h2>
  <p class="section-subtitle">Compra simple y entrega inmediata en 3 pasos.</p>
  <div class="steps">
    <div class="step">
      <div class="step-num">1</div>
      <h3>Elige tu protocolo</h3>
      <p>Selecciona el protocolo o pack que necesitas para tu práctica clínica o deportiva.</p>
    </div>
    <div class="step">
      <div class="step-num">2</div>
      <h3>Paga con PayPal</h3>
      <p>Completa tu pago de forma segura con tu cuenta PayPal o con tarjeta de crédito/débito.</p>
    </div>
    <div class="step">
      <div class="step-num">3</div>
      <h3>Descarga tu PDF</h3>
      <p>Recibirás el enlace de descarga de inmediato al correo que registraste en PayPal.</p>
    </div>
    <div class="step">
      <div class="step-num">4</div>
      <h3>Aplica en clínica</h3>
      <p>Usa el protocolo directamente con tus pacientes. Imprimible y digital.</p>
    </div>
  </div>
</section>

<!-- SOBRE MÍ -->
<section id="sobre-mi">
  <div class="about-grid">
    <div style="display:flex; flex-direction:column; align-items:center; gap:18px;">
      <div class="about-avatar"><img src="perfil.jpg" alt="Fernando Martínez Roldán" /></div>
      <!-- Logro estrella -->
      <div style="background:linear-gradient(135deg,#f0a500,#d4890a); border-radius:12px; padding:14px 20px; text-align:center; width:100%;">
        <div style="font-size:1.5rem;">🏆</div>
        <strong style="display:block; color:#1c2b3a; font-size:.95rem; margin-top:4px;">Campeón Liga MX</strong>
        <span style="font-size:.78rem; color:rgba(28,43,58,.75);">Atlas FC · Clausura 2022 · Bicampeones</span>
      </div>
    </div>

    <div class="about-text">
      <div class="section-tag">Quién soy</div>
      <h2>Fernando Martínez Roldán</h2>

      <div class="about-stats">
        <div class="about-stat">
          <strong>+8</strong>
          <span>Años de experiencia</span>
        </div>
        <div class="about-stat">
          <strong>Atlas FC</strong>
          <span>Primera División Liga MX</span>
        </div>
        <div class="about-stat">
          <strong>Máster</strong>
          <span>Readaptación de Lesiones FSI</span>
        </div>
      </div>

      <p>Soy fisioterapeuta y readaptador del <strong>Primer Equipo Varonil de Atlas F.C.</strong> en la Liga MX. He acompañado al equipo en uno de sus mejores momentos históricos: el <strong>bicampeonato Clausura 2022</strong>. Trabajo diariamente con futbolistas profesionales, diseñando y ejecutando procesos de rehabilitación de alto nivel.</p>

      <p>Mis protocolos son el resultado de años de experiencia clínica y deportiva, combinando la mejor evidencia científica con la práctica real. Cada PDF concentra el conocimiento que he construido a lo largo de mi carrera para que puedas aplicarlo desde el primer día.</p>

      <div class="credentials">
        <span class="cred">🎓 Universidad Valle de México</span>
        <span class="cred">🏅 Especialista G-SE (España)</span>
        <span class="cred">📚 Physio Network · López Chicharro</span>
        <span class="cred">⚽ Atlas FC desde 2019</span>
        <span class="cred">🦴 Ortopédica · Deportiva · Geriátrica</span>
      </div>
    </div>
  </div>

  <!-- Galería debajo del perfil -->
  <div class="photo-gallery" style="margin-top:28px;">
    <img src="galeria1.png" alt="Fernando Martínez — Atlas FC" />
    <img src="galeria2.jpg" alt="Trabajo con jugadores" />
    <img src="galeria3.png" alt="Bicampeones Liga MX" />
  </div>
</section>

<!-- GARANTÍA -->
<div class="guarantee">
  <div class="guarantee-icon">🛡️</div>
  <h2>Garantía de satisfacción</h2>
  <p>Si el contenido no cumple tus expectativas, contáctame dentro de los 7 días y te reembolso el 100%. Sin preguntas.</p>
</div>

<!-- CONTACTO -->
<section id="contacto">
  <div class="section-tag">Contacto</div>
  <h2>¿Tienes alguna pregunta?</h2>
  <p class="section-subtitle">Escríbeme antes de comprar o si necesitas información sobre algún protocolo específico.</p>

  <div class="contact-grid">
    <div class="contact-info">
      <h3>Información de contacto</h3>
      <div class="contact-item">
        <div class="contact-icon">📧</div>
        <div>
          <strong>Correo electrónico</strong>
          <p>alwaysnano1@gmail.com</p>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">💬</div>
        <div>
          <strong>WhatsApp</strong>
          <p>Escríbeme para consultas rápidas sobre los protocolos</p>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">⏰</div>
        <div>
          <strong>Tiempo de respuesta</strong>
          <p>Respondo en menos de 24 horas</p>
        </div>
      </div>
    </div>

    <div class="contact-form">
      <h3>Envíame un mensaje</h3>
      <form onsubmit="sendMail(event)">
        <div class="form-group">
          <label>Nombre completo</label>
          <input type="text" id="fname" placeholder="Tu nombre" required>
        </div>
        <div class="form-group">
          <label>Correo electrónico</label>
          <input type="email" id="femail" placeholder="tu@correo.com" required>
        </div>
        <div class="form-group">
          <label>Asunto</label>
          <select id="fsubject">
            <option>Consulta sobre un protocolo</option>
            <option>Solicitar protocolo personalizado</option>
            <option>Problema con mi compra</option>
            <option>Otro</option>
          </select>
        </div>
        <div class="form-group">
          <label>Mensaje</label>
          <textarea id="fmessage" placeholder="¿En qué puedo ayudarte?"></textarea>
        </div>
        <button type="submit" class="btn-submit">Enviar mensaje →</button>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2026 RehabPro — Fernando Martínez Roldán · <a href="mailto:alwaysnano1@gmail.com">alwaysnano1@gmail.com</a></p>
  <p style="margin-top:8px; font-size:.78rem;">Los protocolos son material educativo profesional. No sustituyen el juicio clínico del fisioterapeuta.</p>
</footer>

<script>
  // Tab switcher
  function switchTab(tab, btn) {
    document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('tab-' + tab).classList.add('active');
    btn.classList.add('active');
  }

  // Contact form → mailto
  function sendMail(e) {
    e.preventDefault();
    const name    = document.getElementById('fname').value;
    const email   = document.getElementById('femail').value;
    const subject = document.getElementById('fsubject').value;
    const message = document.getElementById('fmessage').value;
    const body    = encodeURIComponent(`De: ${name} (${email})\n\n${message}`);
    const sub     = encodeURIComponent(subject);
    window.location.href = `mailto:alwaysnano1@gmail.com?subject=${sub}&body=${body}`;
  }
</script>

<script>
  // ── 8 CARPETAS DE GOOGLE DRIVE ──
  // IMPORTANTE: Para que los compradores puedan acceder, cada carpeta debe estar
  // configurada en Drive como "Cualquiera con el enlace puede ver"
  const carpetas = [
    {
      id: 1,
      nombre: 'Tendinopatías y Bursitis',
      icon: '🏋️',
      color: '#6c3483',
      protocolos: ['Tendón de Aquiles','Supraespinoso','Infraespinoso','Subescapular','Redondo Mayor y Menor','Pubalgia Deportiva','Epicondilalgia Lateral/Medial','De Quervain / Muñeca y Dedos','Fascitis Plantar / Periostitis'],
      driveId: '1xhfB3IBHnehhkjsAQ9MXsoc7YCztIPvT',
    },
    {
      id: 2,
      nombre: 'Desgarros y Sobrecargas Musculares',
      icon: '💪',
      color: '#1a5276',
      protocolos: ['Isquiotibiales','Aductor','Glúteo Mayor','Recto Femoral','Gemelo y Sóleo','Desgarros y Sobrecargas Musculares'],
      driveId: '1KFXVRauv_eb1BCOMISyZxuypnMjRcBa_',
    },
    {
      id: 3,
      nombre: 'Patología de Columna',
      icon: '🦴',
      color: '#0d3b6e',
      protocolos: ['Cervicalgia','Latigazo Cervical (WAD)','Dolor Torácico Mecánico','Dolor Lumbar Inespecífico','Hernia de Disco Lumbar','Radiculopatía Lumbar','Ciática'],
      driveId: '1zS5M7--LGpWp-kEgIMBtitMIlIWzcZMw',
    },
    {
      id: 4,
      nombre: 'Artrosis y Degenerativo',
      icon: '🦵',
      color: '#784212',
      protocolos: ['Lesiones Meniscales','FAI / Artrosis de Cadera'],
      driveId: '1YtEuWB3dgUwOCXfifVlHEfnlSlZGjPfT',
    },
    {
      id: 5,
      nombre: 'Esguinces e Inestabilidad',
      icon: '🦶',
      color: '#117a65',
      protocolos: ['LCA (Ligamento Cruzado Anterior)','Esguince de Tobillo','Inestabilidad Crónica de Tobillo','Inestabilidad Bankart / SLAP'],
      driveId: '12Wa9LLHcBaqLR7_KfOESggeKzwIBqrYz',
    },
    {
      id: 6,
      nombre: 'Post-Quirúrgico',
      icon: '🏥',
      color: '#7b241c',
      protocolos: ['Rehabilitación Post-Qx de Hombro','Prótesis de Rodilla y Cadera'],
      driveId: '1zPdUadCm6abdPgN70e0ozw4ItLzJaTAE',
    },
    {
      id: 7,
      nombre: 'Neurológico',
      icon: '🧠',
      color: '#4a235a',
      protocolos: ['EVC / Parkinson','Lesiones Medulares','Parálisis Facial / Neuropatías','Síndrome del Túnel Carpiano'],
      driveId: '1bTxUUMh430WE4CKj1LKwm-k1XN2Ttrqj',
    },
    {
      id: 8,
      nombre: 'Prevención y General',
      icon: '🛡️',
      color: '#145a32',
      protocolos: ['Sarcopenia / Osteoporosis'],
      driveId: '1Q_lnpRHKOGqWvnzzzL8OPf7T4bARDyy2',
    },
  ];

  let currentAmount  = '159.00';
  let currentProduct = '';
  let currentDriveId = '';

  // Render grid de carpetas
  function renderCarpetas() {
    const grid = document.getElementById('carpetas-grid');
    grid.innerHTML = carpetas.map(c => `
      <div class="product-card">
        <div class="product-header" style="background:linear-gradient(135deg,${c.color},${c.color}99); padding:20px 20px 14px; position:relative;">
          <div class="product-category" style="font-size:.7rem;font-weight:700;color:rgba(255,255,255,.7);text-transform:uppercase;letter-spacing:1px;margin-bottom:6px;">
            ${c.icon} Carpeta ${c.id}
          </div>
          <h3 style="color:#fff;font-size:1.05rem;font-weight:800;padding-right:76px;line-height:1.3;">${c.nombre}</h3>
          <div style="position:absolute;top:16px;right:16px;background:#f0a500;color:#1c2b3a;font-size:.95rem;font-weight:900;padding:5px 12px;border-radius:16px;">$159</div>
        </div>
        <div class="product-body" style="padding:16px 20px;display:flex;flex-direction:column;flex:1;">
          <ul class="product-features" style="margin-bottom:16px;flex:1;">
            ${c.protocolos.map(p => `<li>${p}</li>`).join('')}
          </ul>
          <span style="font-size:.75rem;color:#6b7a8d;margin-bottom:12px;display:block;">${c.protocolos.length} protocolo${c.protocolos.length>1?'s':''} incluido${c.protocolos.length>1?'s':''} · PDF descargables</span>
          <button onclick="openModal('${c.nombre.replace(/'/g,"\\'")}','${c.icon}','159.00','${c.driveId}')"
            style="width:100%;padding:12px;background:#0070ba;color:#fff;border:none;border-radius:8px;font-size:.95rem;font-weight:700;cursor:pointer;transition:background .2s;"
            onmouseover="this.style.background='#005ea6'" onmouseout="this.style.background='#0070ba'">
            🛒 Comprar — $159 MXN
          </button>
        </div>
      </div>
    `).join('');
  }

  function openModal(name, icon, amount, driveId) {
    currentProduct = name;
    currentAmount  = amount || '159.00';
    currentDriveId = driveId || 'ALL';
    document.getElementById('modal-title').textContent = name;
    document.getElementById('modal-icon').textContent = icon;
    document.getElementById('modal-price').innerHTML =
      '$' + parseFloat(currentAmount).toLocaleString('es-MX') +
      ' <span style="font-size:1rem;color:#6b7a8d;">MXN</span>';
    document.getElementById('buy-modal').style.display = 'flex';
    document.getElementById('paypal-modal-btn').innerHTML = '';

    paypal.Buttons({
      style: { layout: 'vertical', color: 'blue', shape: 'rect', label: 'pay' },
      createOrder: function(data, actions) {
        return actions.order.create({
          purchase_units: [{
            description: 'Rehavitat: ' + currentProduct,
            amount: { currency_code: 'MXN', value: currentAmount }
          }]
        });
      },
      onApprove: function(data, actions) {
        return actions.order.capture().then(function(details) {
          closeModal();
          // Mostrar modal de descarga
          var driveUrl = currentDriveId === 'ALL'
            ? 'https://drive.google.com/drive/folders/1nQtRnsB9mpB6silIv3AuvYh1mTMPdL1h?usp=sharing'
            : 'https://drive.google.com/drive/folders/' + currentDriveId + '?usp=sharing';
          document.getElementById('success-link').href = driveUrl;
          document.getElementById('success-modal').style.display = 'flex';
        });
      },
      onError: function(err) {
        alert('Hubo un error en el pago. Por favor intenta de nuevo o escríbenos a alwaysnano1@gmail.com');
      }
    }).render('#paypal-modal-btn');
  }

  function closeModal() {
    document.getElementById('buy-modal').style.display = 'none';
    document.getElementById('paypal-modal-btn').innerHTML = '';
  }

  // Cerrar modal al hacer clic fuera
  document.getElementById('buy-modal').addEventListener('click', function(e) {
    if (e.target === this) closeModal();
  });
  document.getElementById('success-modal').addEventListener('click', function(e) {
    if (e.target === this) this.style.display = 'none';
  });

  // Render al cargar
  renderCarpetas();
</script>

</body>
</html>
