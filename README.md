# zakat
Calculate Zakat - Authentic Fiqhi Formula Approved By All 4 Sunni Madhabs
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Zakat Calculator — Based on All Four Sunni Madhabs</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.44.0/tabler-icons.min.css">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --teal-50: #E1F5EE;
      --teal-100: #9FE1CB;
      --teal-400: #1D9E75;
      --teal-600: #0F6E56;
      --teal-800: #085041;
      --teal-900: #04342C;
      --amber-50: #FAEEDA;
      --amber-100: #FAC775;
      --amber-600: #854F0B;
      --amber-900: #412402;
      --gray-50: #F7F8F6;
      --gray-100: #EEEEE8;
      --gray-200: #D3D1C7;
      --gray-600: #5F5E5A;
      --gray-800: #2C2C2A;
      --border: #D3D1C7;
      --radius-sm: 6px;
      --radius-md: 10px;
      --radius-lg: 16px;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background: #F4F2EC;
      color: var(--gray-800);
      font-size: 15px;
      line-height: 1.6;
      min-height: 100vh;
    }

    /* ─── NAV ─── */
    nav {
      background: var(--teal-600);
      padding: 0 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 60px;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .nav-brand {
      font-family: 'Amiri', serif;
      font-size: 20px;
      color: var(--teal-50);
      letter-spacing: 0.02em;
    }

    .nav-links {
      display: flex;
      gap: 0;
      list-style: none;
    }

    .nav-links a {
      color: var(--teal-100);
      text-decoration: none;
      font-size: 14px;
      font-weight: 500;
      padding: 8px 16px;
      border-radius: var(--radius-sm);
      transition: background 0.15s, color 0.15s;
    }

    .nav-links a:hover, .nav-links a.active {
      background: rgba(255,255,255,0.12);
      color: #fff;
    }

    /* ─── HERO ─── */
    .hero {
      background: var(--teal-600);
      position: relative;
      overflow: hidden;
      text-align: center;
      padding: 3.5rem 2rem 5rem;
    }

    .hero-geo {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      opacity: 0.1;
      pointer-events: none;
    }

    .hero-inner { position: relative; z-index: 1; max-width: 680px; margin: 0 auto; }

    .bismillah {
      font-family: 'Amiri', serif;
      font-size: 28px;
      color: var(--teal-100);
      margin-bottom: 0.5rem;
      letter-spacing: 0.04em;
    }

    .hero-greeting {
      font-family: 'Amiri', serif;
      font-size: 20px;
      color: var(--teal-50);
      font-style: italic;
      margin-bottom: 1rem;
    }

    .hero-tagline {
      font-size: 15px;
      color: var(--teal-100);
      line-height: 1.65;
      max-width: 520px;
      margin: 0 auto;
    }

    /* ─── PAGE TABS ─── */
    .page-tabs {
      max-width: 820px;
      margin: -1.5rem auto 0;
      padding: 0 1.5rem;
      position: relative;
      z-index: 2;
      display: flex;
      gap: 8px;
    }

    .tab-btn {
      padding: 10px 22px;
      border-radius: var(--radius-md) var(--radius-md) 0 0;
      border: none;
      font-size: 14px;
      font-weight: 500;
      font-family: 'Inter', sans-serif;
      cursor: pointer;
      transition: all 0.15s;
      background: rgba(255,255,255,0.25);
      color: var(--teal-50);
    }

    .tab-btn.active {
      background: #fff;
      color: var(--teal-600);
    }

    /* ─── MAIN LAYOUT ─── */
    .main-wrap {
      max-width: 820px;
      margin: 0 auto;
      padding: 0 1.5rem 4rem;
    }

    .page { display: none; }
    .page.active { display: block; }

    /* ─── CARD ─── */
    .card {
      background: #fff;
      border: 0.5px solid var(--border);
      border-radius: 0 var(--radius-lg) var(--radius-lg) var(--radius-lg);
      padding: 2rem;
    }

    /* ─── SECTION LABEL ─── */
    .section-label {
      font-size: 10px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      color: var(--teal-600);
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 1rem;
    }

    .section-label::after {
      content: '';
      flex: 1;
      height: 0.5px;
      background: var(--teal-600);
      opacity: 0.25;
    }

    .star-divider {
      text-align: center;
      color: var(--teal-400);
      font-size: 14px;
      letter-spacing: 10px;
      margin: 0.25rem 0 1.5rem;
    }

    /* ─── INFO BOXES ─── */
    .info-box {
      background: var(--teal-50);
      border: 0.5px solid var(--teal-100);
      border-radius: var(--radius-md);
      padding: 14px 16px;
      display: flex;
      gap: 12px;
      align-items: flex-start;
      margin-bottom: 1.25rem;
    }

    .info-box .ii { color: var(--teal-600); font-size: 20px; flex-shrink: 0; margin-top: 1px; }

    .info-box .ic { font-size: 13px; color: var(--teal-800); line-height: 1.65; }
    .info-box .ic strong { font-size: 13px; font-weight: 600; display: block; margin-bottom: 4px; color: var(--teal-900); }

    /* ─── NISAB TOGGLE ─── */
    .nisab-toggle { display: flex; gap: 10px; margin-bottom: 0.5rem; }

    .nisab-btn {
      flex: 1;
      padding: 10px 14px;
      border-radius: var(--radius-md);
      border: 0.5px solid var(--border);
      background: var(--gray-50);
      color: var(--gray-600);
      font-size: 13px;
      cursor: pointer;
      text-align: center;
      transition: all 0.15s;
      font-family: 'Inter', sans-serif;
    }

    .nisab-btn.active {
      background: var(--teal-50);
      border-color: var(--teal-600);
      color: var(--teal-800);
      font-weight: 600;
    }

    .nisab-explainer {
      font-size: 12px;
      color: var(--gray-600);
      margin-bottom: 1.25rem;
      line-height: 1.5;
    }

    /* ─── INPUTS ─── */
    .input-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 14px;
      margin-bottom: 1.25rem;
    }

    .input-group { display: flex; flex-direction: column; gap: 5px; }

    .input-group label {
      font-size: 13px;
      color: var(--gray-600);
      font-weight: 500;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .input-group input {
      border: 1px solid var(--border);
      border-radius: var(--radius-sm);
      padding: 9px 13px;
      font-size: 15px;
      font-family: 'Inter', sans-serif;
      color: var(--gray-800);
      background: var(--gray-50);
      width: 100%;
      transition: border-color 0.15s, box-shadow 0.15s;
    }

    .input-group input:focus {
      outline: none;
      border-color: var(--teal-600);
      box-shadow: 0 0 0 3px rgba(15,110,86,0.1);
      background: #fff;
    }

    .input-group input[readonly] { opacity: 0.6; cursor: not-allowed; background: var(--gray-100); }
    .hint { font-size: 11px; color: #888; }
    .enter-prompt { font-size: 11px; color: var(--teal-600); font-style: italic; }

    /* ─── TOOLTIP ─── */
    .tip {
      display: inline-flex; align-items: center; justify-content: center;
      width: 16px; height: 16px; border-radius: 50%;
      background: var(--teal-600); color: #fff;
      font-size: 9px; font-weight: 700;
      cursor: pointer; position: relative; flex-shrink: 0;
    }

    .tip .tiptext {
      display: none;
      position: absolute;
      bottom: calc(100% + 8px);
      left: 50%;
      transform: translateX(-50%);
      background: var(--teal-900);
      color: var(--teal-50);
      font-size: 12px;
      font-style: normal;
      font-weight: 400;
      border-radius: var(--radius-sm);
      padding: 9px 12px;
      width: 210px;
      line-height: 1.5;
      z-index: 50;
    }

    .tip .tiptext::after {
      content: '';
      position: absolute;
      top: 100%; left: 50%;
      transform: translateX(-50%);
      border: 5px solid transparent;
      border-top-color: var(--teal-900);
    }

    .tip:hover .tiptext { display: block; }

    /* ─── DIVIDER ─── */
    .divider { height: 0.5px; background: var(--border); margin: 1.5rem 0; }

    /* ─── CURRENCY ROW ─── */
    .currency-row {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 1.5rem;
    }

    .currency-row label { font-size: 13px; color: var(--gray-600); font-weight: 500; }

    select {
      padding: 8px 12px;
      border-radius: var(--radius-sm);
      border: 1px solid var(--border);
      background: var(--gray-50);
      color: var(--gray-800);
      font-size: 14px;
      font-family: 'Inter', sans-serif;
      cursor: pointer;
    }

    select:focus { outline: none; border-color: var(--teal-600); }

    /* ─── CALC BUTTON ─── */
    .calc-btn {
      width: 100%;
      padding: 12px;
      background: var(--teal-600);
      color: #fff;
      border: none;
      border-radius: var(--radius-md);
      font-size: 15px;
      font-weight: 600;
      font-family: 'Inter', sans-serif;
      cursor: pointer;
      margin-top: 1.25rem;
      transition: background 0.15s, transform 0.1s;
    }

    .calc-btn:hover { background: var(--teal-800); }
    .calc-btn:active { transform: scale(0.99); }

    /* ─── RESULTS ─── */
    .result-area {
      background: var(--gray-50);
      border: 0.5px solid var(--border);
      border-radius: var(--radius-lg);
      padding: 1.5rem;
      margin-top: 1.5rem;
    }

    .nisab-status {
      border-radius: var(--radius-md);
      padding: 12px 16px;
      font-size: 13px;
      display: flex;
      align-items: flex-start;
      gap: 10px;
      margin-bottom: 1.25rem;
      line-height: 1.5;
    }

    .nisab-status.eligible { background: var(--teal-50); color: var(--teal-800); border: 0.5px solid var(--teal-100); }
    .nisab-status.ineligible { background: var(--amber-50); color: var(--amber-600); border: 0.5px solid var(--amber-100); }
    .nisab-status i { font-size: 18px; flex-shrink: 0; margin-top: 1px; }

    .result-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      margin-bottom: 1.25rem;
    }

    .result-card {
      background: #fff;
      border: 0.5px solid var(--border);
      border-radius: var(--radius-md);
      padding: 12px 14px;
      text-align: center;
    }

    .rc-label { font-size: 11px; color: #888; margin-bottom: 5px; }
    .rc-value { font-size: 18px; font-weight: 600; color: var(--gray-800); }

    .result-highlight {
      text-align: center;
      margin-bottom: 1rem;
    }

    .zakat-due-card {
      display: inline-block;
      background: var(--teal-600);
      border-radius: var(--radius-lg);
      padding: 1.25rem 2.5rem;
      text-align: center;
      min-width: 240px;
    }

    .zakat-due-card .zdl { font-size: 12px; color: var(--teal-100); margin-bottom: 6px; }
    .zakat-due-card .zdv { font-size: 28px; font-weight: 700; color: #fff; }

    .formula-note {
      font-size: 12px;
      color: #888;
      text-align: center;
      line-height: 1.6;
      font-style: italic;
      margin-top: 0.75rem;
    }

    /* ─── ABOUT PAGE ─── */
    .about-hero {
      background: var(--teal-50);
      border: 0.5px solid var(--teal-100);
      border-radius: var(--radius-lg) var(--radius-lg) 0 0;
      padding: 2rem;
      text-align: center;
    }

    .about-hero h2 {
      font-family: 'Amiri', serif;
      font-size: 26px;
      color: var(--teal-800);
      margin-bottom: 0.5rem;
    }

    .about-hero p { font-size: 14px; color: var(--teal-600); line-height: 1.6; max-width: 520px; margin: 0 auto; }

    .about-card {
      background: #fff;
      border: 0.5px solid var(--border);
      border-top: none;
      border-radius: 0 0 var(--radius-lg) var(--radius-lg);
      padding: 2rem;
    }

    .about-section { margin-bottom: 2rem; }
    .about-section:last-child { margin-bottom: 0; }

    .about-section h3 {
      font-size: 16px;
      font-weight: 600;
      color: var(--teal-800);
      margin-bottom: 0.75rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .about-section h3 i { color: var(--teal-600); font-size: 18px; }

    .about-section p {
      font-size: 14px;
      color: var(--gray-600);
      line-height: 1.75;
      margin-bottom: 0.75rem;
    }

    .about-section p:last-child { margin-bottom: 0; }

    .pillars-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: 10px;
      margin-top: 0.75rem;
    }

    .pillar-card {
      background: var(--teal-50);
      border: 0.5px solid var(--teal-100);
      border-radius: var(--radius-md);
      padding: 12px 14px;
      text-align: center;
    }

    .pillar-card .pnum { font-family: 'Amiri', serif; font-size: 22px; color: var(--teal-600); font-weight: 700; }
    .pillar-card .pname { font-size: 13px; font-weight: 600; color: var(--teal-800); margin: 2px 0; }
    .pillar-card .pdesc { font-size: 11px; color: var(--teal-600); line-height: 1.4; }

    .madhab-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: 10px;
      margin-top: 0.75rem;
    }

    .madhab-card {
      background: var(--gray-50);
      border: 0.5px solid var(--border);
      border-radius: var(--radius-md);
      padding: 12px 14px;
    }

    .madhab-card .mname { font-size: 14px; font-weight: 600; color: var(--teal-800); margin-bottom: 4px; }
    .madhab-card .mfound { font-size: 11px; color: var(--gray-600); margin-bottom: 6px; }
    .madhab-card .mnote { font-size: 12px; color: var(--gray-600); line-height: 1.4; }

    .conditions-list {
      list-style: none;
      margin-top: 0.75rem;
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .conditions-list li {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      font-size: 13px;
      color: var(--gray-600);
      line-height: 1.5;
    }

    .conditions-list li i { color: var(--teal-600); font-size: 16px; flex-shrink: 0; margin-top: 2px; }
    .conditions-list li strong { color: var(--gray-800); }

    .ayah-box {
      background: var(--teal-900);
      border-radius: var(--radius-lg);
      padding: 1.5rem 2rem;
      text-align: center;
      margin-top: 2rem;
    }

    .ayah-arabic { font-family: 'Amiri', serif; font-size: 22px; color: var(--teal-100); line-height: 1.8; margin-bottom: 0.5rem; }
    .ayah-trans { font-size: 13px; color: var(--teal-100); font-style: italic; opacity: 0.8; }
    .ayah-ref { font-size: 11px; color: var(--teal-400); margin-top: 4px; }

    /* ─── FOOTER ─── */
    footer {
      text-align: center;
      padding: 2rem 1rem;
      font-size: 12px;
      color: #888;
      font-style: italic;
      font-family: 'Amiri', serif;
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 600px) {
      .result-grid { grid-template-columns: 1fr 1fr; }
      .result-grid .result-card:last-child { grid-column: 1 / -1; }
      .card, .about-card { padding: 1.25rem; }
      nav { padding: 0 1rem; }
      .nav-brand { font-size: 17px; }
      .nav-links a { padding: 8px 10px; font-size: 13px; }
      .hero { padding: 2.5rem 1.25rem 4rem; }
      .bismillah { font-size: 22px; }
      .nisab-toggle { flex-direction: column; }
      .madhab-grid, .pillars-grid { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-brand">الزكاة — Zakat Calculator</div>
    <ul class="nav-links">
      <li><a href="#" class="active" onclick="showPage('calculator', this)">Calculator</a></li>
      <li><a href="#" onclick="showPage('about', this)">About Zakat</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <svg class="hero-geo" viewBox="0 0 900 260" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <pattern id="starPat" x="0" y="0" width="90" height="90" patternUnits="userSpaceOnUse">
          <polygon points="45,5 53,32 80,32 58,50 66,77 45,61 24,77 32,50 10,32 37,32" fill="none" stroke="white" stroke-width="0.9"/>
          <polygon points="45,18 50,33 65,33 54,43 58,58 45,50 32,58 36,43 25,33 40,33" fill="none" stroke="white" stroke-width="0.4"/>
          <circle cx="45" cy="45" r="3" fill="none" stroke="white" stroke-width="0.6"/>
        </pattern>
        <pattern id="hexPat" x="0" y="0" width="44" height="52" patternUnits="userSpaceOnUse">
          <polygon points="22,2 40,12 40,32 22,42 4,32 4,12" fill="none" stroke="white" stroke-width="0.5"/>
        </pattern>
      </defs>
      <rect width="900" height="260" fill="url(#starPat)"/>
      <rect width="900" height="260" fill="url(#hexPat)" opacity="0.45"/>
      <path d="M0,200 Q225,165 450,185 Q675,205 900,172 L900,260 L0,260 Z" fill="rgba(0,0,0,0.18)"/>
    </svg>
    <div class="hero-inner">
      <div class="bismillah">بِسْمِ ٱللَّٰهِ ٱلرَّحْمَٰنِ ٱلرَّحِيمِ</div>
      <div class="hero-greeting">As-salāmu ʿalaykum wa-raḥmatu llāhi wa-barakātuh</div>
      <div class="hero-tagline">Your Zakat Calculator, based on the authentic fiqhi formula as agreed upon by all four Sunni Madhabs — Ḥanafi, Mālikī, Shāfiʿī, and Ḥanbalī.</div>
    </div>
  </div>

  <!-- TABS -->
  <div class="page-tabs">
    <button class="tab-btn active" id="tab-calculator" onclick="showPage('calculator', null)">Calculator</button>
    <button class="tab-btn" id="tab-about" onclick="showPage('about', null)">About Zakat</button>
  </div>

  <!-- MAIN -->
  <div class="main-wrap">

    <!-- ══════════ CALCULATOR PAGE ══════════ -->
    <div id="page-calculator" class="page active">
      <div class="card">
        <div class="star-divider">✦ ✦ ✦</div>

        <!-- Currency -->
        <div class="currency-row">
          <label for="currencySelect">Currency:</label>
          <select id="currencySelect" onchange="updateCurrency()">
            <option value="INR" data-symbol="₹">INR — Indian Rupee</option>
            <option value="AED" data-symbol="د.إ">AED — UAE Dirham</option>
            <option value="SAR" data-symbol="﷼">SAR — Saudi Riyal</option>
            <option value="USD" data-symbol="$">USD — US Dollar</option>
            <option value="GBP" data-symbol="£">GBP — British Pound</option>
            <option value="EUR" data-symbol="€">EUR — Euro</option>
            <option value="MYR" data-symbol="RM">MYR — Malaysian Ringgit</option>
            <option value="SGD" data-symbol="S$">SGD — Singapore Dollar</option>
            <option value="QAR" data-symbol="﷼">QAR — Qatari Riyal</option>
          </select>
        </div>

        <!-- Step 1: Nisab -->
        <div class="section-label">Step 1 — Choose your Nisab standard</div>

        <div class="info-box">
          <i class="ti ti-info-circle ii"></i>
          <div class="ic">
            <strong>What is Nisab?</strong>
            Nisab is the <em>minimum amount of wealth</em> you must own before Zakat becomes obligatory. Think of it as a threshold — if your total savings and assets are above this amount and have stayed there for a full lunar year, you are required to pay Zakat. If you are below it, Zakat is not yet due. Scholars calculate this threshold using either the price of gold or silver.
          </div>
        </div>

        <div class="nisab-toggle">
          <button class="nisab-btn active" id="btn-gold" onclick="setNisab('gold')">
            <div style="font-size:15px; margin-bottom:3px;">☽ Gold standard</div>
            <div style="font-size:11px; opacity:0.8;">Nisab = current price of 85g of gold</div>
          </button>
          <button class="nisab-btn" id="btn-silver" onclick="setNisab('silver')">
            <div style="font-size:15px; margin-bottom:3px;">◇ Silver standard</div>
            <div style="font-size:11px; opacity:0.8;">Nisab = current price of 595g of silver</div>
          </button>
        </div>

        <div class="nisab-explainer" id="nisabExplainer">
          The gold standard is used by most scholars today for its stability. The silver standard (preferred by scholars like Sheikh al-Qaradawi) sets a lower threshold, meaning more people give Zakat and more wealth reaches the poor.
        </div>

        <div class="input-grid" style="grid-template-columns:1fr 1fr;">
          <div class="input-group">
            <label id="metalPriceLabel">
              Gold price per gram (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext" id="metalTipText">The current market price of one gram of gold. Check Google Finance, a jewellery app, or your bank app for today's rate.</span></span>
            </label>
            <input type="number" id="metalPrice" value="7400" min="0" oninput="calculate()">
            <div class="enter-prompt" id="enterPrompt">↳ Enter the current price of gold per gram.</div>
          </div>
          <div class="input-group">
            <label>
              Your Nisab threshold (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">Auto-calculated. This is the minimum wealth you must hold for Zakat to be due on you. You don't need to type anything here.</span></span>
            </label>
            <input type="number" id="nisabValue" value="629000" readonly>
            <div class="hint">Auto-calculated from the price you entered above.</div>
          </div>
        </div>

        <div class="divider"></div>

        <!-- Step 2: Assets -->
        <div class="section-label">Step 2 — Enter your assets</div>

        <div class="info-box">
          <i class="ti ti-coins ii"></i>
          <div class="ic">
            <strong>What counts as a Zakatable asset?</strong>
            Zakat applies to wealth that is "growing" or has earning potential — cash savings, gold and silver you own as an investment, goods you sell in business, and money others owe you. Your home, car, clothes, furniture, and tools you use for work are <em>not</em> subject to Zakat.
          </div>
        </div>

        <div class="input-grid">
          <div class="input-group">
            <label>Cash savings & bank balance (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">All money you have in bank accounts, wallets, and at home — including fixed deposits and savings accounts.</span></span>
            </label>
            <input type="number" id="cash" value="0" min="0" oninput="calculate()">
          </div>
          <div class="input-group">
            <label>Gold & silver you own (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">Enter the current market value of gold or silver you own as savings or investment. Jewellery you wear every day is generally excluded under the Mālikī and Shāfiʿī schools.</span></span>
            </label>
            <input type="number" id="goldSilver" value="0" min="0" oninput="calculate()">
            <div class="hint">Daily-wear jewellery is generally excluded (Mālikī / Shāfiʿī view).</div>
          </div>
          <div class="input-group">
            <label>Business stock / trade goods (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">If you own a shop or sell goods, enter the current market value of your inventory — what you could sell it for today.</span></span>
            </label>
            <input type="number" id="inventory" value="0" min="0" oninput="calculate()">
          </div>
          <div class="input-group">
            <label>Investments & shares (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">Include investments, mutual funds, or shares. When in doubt, apply 2.5% on the full current market value. Ask a scholar for your specific portfolio.</span></span>
            </label>
            <input type="number" id="investments" value="0" min="0" oninput="calculate()">
            <div class="hint">Include only the zakatable portion of your portfolio.</div>
          </div>
          <div class="input-group">
            <label>Money owed to you (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">If someone owes you money that you genuinely expect to get back — a loan, unpaid invoice, etc. — include it here.</span></span>
            </label>
            <input type="number" id="receivables" value="0" min="0" oninput="calculate()">
            <div class="hint">Only include debts you are confident will be repaid.</div>
          </div>
        </div>

        <div class="divider"></div>

        <!-- Step 3: Debts -->
        <div class="section-label">Step 3 — Subtract your debts</div>

        <div class="info-box">
          <i class="ti ti-receipt-off ii"></i>
          <div class="ic">
            <strong>Can I deduct debts?</strong>
            Yes — you may subtract debts that are due within this year. Scholars generally agree you can deduct the installment of any loan due in the coming year (not the full loan amount), credit card balances you owe, and bills you have already been charged but not yet paid.
          </div>
        </div>

        <div class="input-grid" style="grid-template-columns:1fr 1fr;">
          <div class="input-group">
            <label>Debts due within this year (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">Loans, credit card balances, or any money you owe that must be paid within the next 12 months.</span></span>
            </label>
            <input type="number" id="debts" value="0" min="0" oninput="calculate()">
          </div>
          <div class="input-group">
            <label>Bills currently outstanding (<span class="cs">₹</span>)
              <span class="tip">?<span class="tiptext">Rent, utility bills, or other expenses you have already been billed for but not yet paid.</span></span>
            </label>
            <input type="number" id="bills" value="0" min="0" oninput="calculate()">
          </div>
        </div>

        <button class="calc-btn" onclick="calculate()">Calculate my Zakat →</button>

        <!-- Results -->
        <div class="result-area" id="resultArea" style="display:none;">
          <div class="nisab-status eligible" id="nisabStatusEl">
            <i class="ti ti-check"></i>
            <span id="nisabStatusText"></span>
          </div>
          <div class="result-grid">
            <div class="result-card">
              <div class="rc-label">Total assets</div>
              <div class="rc-value" id="rTotalAssets">₹0</div>
            </div>
            <div class="result-card">
              <div class="rc-label">Total liabilities</div>
              <div class="rc-value" id="rLiabilities">₹0</div>
            </div>
            <div class="result-card">
              <div class="rc-label">Net zakatable wealth</div>
              <div class="rc-value" id="rNetWealth">₹0</div>
            </div>
          </div>
          <div class="result-highlight">
            <div class="zakat-due-card">
              <div class="zdl">Zakat due (2.5% of net wealth)</div>
              <div class="zdv" id="rZakat">₹0</div>
            </div>
          </div>
          <div class="formula-note">
            Formula: (Total assets − Liabilities) × 2.5% &nbsp;·&nbsp; Agreed upon by all four Sunni Madhabs.<br>
            Your wealth must have been above the Nisab for a full lunar year (ḥawl) for Zakat to be obligatory.
          </div>
        </div>

      </div>
    </div>

    <!-- ══════════ ABOUT PAGE ══════════ -->
    <div id="page-about" class="page">
      <div class="about-hero">
        <h2>What is Zakat?</h2>
        <p>A plain-language guide to one of the five pillars of Islam — who must pay it, how it is calculated, and why it matters.</p>
      </div>
      <div class="about-card">

        <div class="about-section">
          <h3><i class="ti ti-star"></i> The Five Pillars of Islam</h3>
          <p>Zakat is the third of the five pillars of Islam — the core acts of worship that every Muslim is called to observe. Understanding its place among the pillars helps appreciate its importance.</p>
          <div class="pillars-grid">
            <div class="pillar-card">
              <div class="pnum">١</div>
              <div class="pname">Shahādah</div>
              <div class="pdesc">Declaration of faith — "There is no god but Allāh, and Muḥammad is His messenger."</div>
            </div>
            <div class="pillar-card">
              <div class="pnum">٢</div>
              <div class="pname">Ṣalāh</div>
              <div class="pdesc">The five daily prayers performed at fixed times throughout the day.</div>
            </div>
            <div class="pillar-card">
              <div class="pnum">٣</div>
              <div class="pname">Zakāh</div>
              <div class="pdesc">Obligatory annual charity given on qualifying wealth to those in need.</div>
            </div>
            <div class="pillar-card">
              <div class="pnum">٤</div>
              <div class="pname">Ṣawm</div>
              <div class="pdesc">Fasting during the holy month of Ramaḍān from dawn to sunset.</div>
            </div>
            <div class="pillar-card">
              <div class="pnum">٥</div>
              <div class="pname">Ḥajj</div>
              <div class="pdesc">Pilgrimage to Makkah, obligatory once in a lifetime for those able to do so.</div>
            </div>
          </div>
        </div>

        <div class="divider"></div>

        <div class="about-section">
          <h3><i class="ti ti-help-circle"></i> What exactly is Zakat?</h3>
          <p>Zakat (Arabic: زَكَاة, meaning "purification" or "growth") is an obligatory annual payment made by Muslims who possess wealth above a minimum threshold. It is not a tax in the conventional sense — it is an act of worship and a form of social welfare built directly into Islamic law.</p>
          <p>The Quran mentions Zakat alongside prayer (Ṣalāh) more than 80 times, showing how central it is to the faith. It is considered both a personal act of worship and a communal obligation — a mechanism for redistributing wealth from the rich to the poor.</p>
          <p>The rate is fixed at <strong>2.5%</strong> of your total net zakatable wealth — that is, one fortieth (1/40th). This rate has been agreed upon by all four major Sunni schools of Islamic jurisprudence (madhabs) since the early centuries of Islam.</p>
        </div>

        <div class="divider"></div>

        <div class="about-section">
          <h3><i class="ti ti-checklist"></i> The conditions for Zakat to be obligatory</h3>
          <p>Not every Muslim is required to pay Zakat. The following conditions must all be met:</p>
          <ul class="conditions-list">
            <li><i class="ti ti-circle-check"></i><span><strong>Being Muslim</strong> — Zakat is an obligation on Muslims only.</span></li>
            <li><i class="ti ti-circle-check"></i><span><strong>Reaching the Nisab</strong> — Your net wealth must equal or exceed the Nisab threshold (the value of 85g of gold or 595g of silver, depending on the standard used).</span></li>
            <li><i class="ti ti-circle-check"></i><span><strong>One full lunar year (Ḥawl)</strong> — Your wealth must have remained above the Nisab for a complete lunar year. The Islamic calendar is used, not the Gregorian calendar.</span></li>
            <li><i class="ti ti-circle-check"></i><span><strong>Full ownership (Milk al-tām)</strong> — You must fully own the wealth. Money that is not truly yours — such as a trust held for someone else — does not attract Zakat.</span></li>
            <li><i class="ti ti-circle-check"></i><span><strong>Growth potential (Namāʾ)</strong> — The wealth must be of a "productive" or "growing" nature — cash, gold, trade goods, investments. Your home, car, and personal belongings do not qualify.</span></li>
          </ul>
        </div>

        <div class="divider"></div>

        <div class="about-section">
          <h3><i class="ti ti-building-mosque"></i> The four Sunni Madhabs on Zakat</h3>
          <p>A madhab is a school of Islamic jurisprudence. There are four major Sunni madhabs, and all four agree on the core formula for Zakat — 2.5% on net zakatable wealth above the Nisab held for one lunar year. Minor differences exist on a few details (such as whether daily-wear jewellery is zakatable), but the essential calculation is the same across all four.</p>
          <div class="madhab-grid">
            <div class="madhab-card">
              <div class="mname">Ḥanafi</div>
              <div class="mfound">Founded by Imām Abū Ḥanīfah (d. 767 CE)</div>
              <div class="mnote">Predominant in South Asia, Turkey, Central Asia. Holds that gold jewellery is zakatable regardless of personal use.</div>
            </div>
            <div class="madhab-card">
              <div class="mname">Mālikī</div>
              <div class="mfound">Founded by Imām Mālik ibn Anas (d. 795 CE)</div>
              <div class="mnote">Predominant in North and West Africa. Daily-wear jewellery is generally not zakatable.</div>
            </div>
            <div class="madhab-card">
              <div class="mname">Shāfiʿī</div>
              <div class="mfound">Founded by Imām al-Shāfiʿī (d. 820 CE)</div>
              <div class="mnote">Widespread in Southeast Asia and East Africa. Jewellery in normal personal use is not zakatable.</div>
            </div>
            <div class="madhab-card">
              <div class="mname">Ḥanbalī</div>
              <div class="mfound">Founded by Imām Aḥmad ibn Ḥanbal (d. 855 CE)</div>
              <div class="mnote">Predominant in Saudi Arabia and Gulf states. Known for strict adherence to hadith; gold jewellery is zakatable.</div>
            </div>
          </div>
        </div>

        <div class="divider"></div>

        <div class="about-section">
          <h3><i class="ti ti-heart"></i> Who receives Zakat?</h3>
          <p>The Quran (9:60) specifies eight categories of people eligible to receive Zakat: the poor (fuqarāʾ), the needy (masākīn), those employed to administer Zakat, those whose hearts are to be reconciled, those in bondage, those in debt, those in the cause of Allāh, and the stranded traveller. In practice, most Zakat today goes to the first two categories — those living in poverty and those in acute need.</p>
        </div>

        <div class="about-section">
          <h3><i class="ti ti-info-circle"></i> A note on this calculator</h3>
          <p>This calculator applies the standard formula agreed upon by all four Sunni Madhabs. It is a guide to help you estimate your Zakat liability. For complex situations — large business assets, multiple currencies, shares and funds, or inherited wealth — we encourage you to consult a qualified Islamic scholar or a certified Zakat institution in your country.</p>
        </div>

        <div class="ayah-box">
          <div class="ayah-arabic">وَأَقِيمُوا الصَّلَاةَ وَآتُوا الزَّكَاةَ وَارْكَعُوا مَعَ الرَّاكِعِينَ</div>
          <div class="ayah-trans">"And establish prayer and give Zakat and bow with those who bow [in worship and obedience]."</div>
          <div class="ayah-ref">— Sūrat al-Baqarah (2:43)</div>
        </div>

      </div>
    </div>

  </div>

  <!-- FOOTER -->
  <footer>
    <div>جَعَلَ اللهُ زَكَاتَكُمْ مَقْبُولَةً — May Allāh accept your Zakat.</div>
    <div style="margin-top:6px; font-family:'Inter',sans-serif; font-style:normal; font-size:11px; color:#aaa;">This calculator is provided as a guide. For complex situations, please consult a qualified Islamic scholar.</div>
  </footer>

  <script>
    let nisabMode = 'gold';
    let currSymbol = '₹';
    const GOLD_W = 85, SILVER_W = 595;

    function showPage(page, navEl) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.querySelectorAll('.tab-btn').forEach(t => t.classList.remove('active'));
      document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
      document.getElementById('page-' + page).classList.add('active');
      document.getElementById('tab-' + page).classList.add('active');
      if (navEl) navEl.classList.add('active');
      window.scrollTo({ top: 0, behavior: 'smooth' });
      return false;
    }

    function updateCurrency() {
      const sel = document.getElementById('currencySelect');
      currSymbol = sel.options[sel.selectedIndex].getAttribute('data-symbol');
      document.querySelectorAll('.cs').forEach(el => el.textContent = currSymbol);
      calculate();
    }

    function setNisab(mode) {
      nisabMode = mode;
      document.getElementById('btn-gold').classList.toggle('active', mode === 'gold');
      document.getElementById('btn-silver').classList.toggle('active', mode === 'silver');
      const lbl = document.getElementById('metalPriceLabel');
      const tip = document.getElementById('metalTipText');
      const exp = document.getElementById('nisabExplainer');
      const prompt = document.getElementById('enterPrompt');
      if (mode === 'gold') {
        lbl.childNodes[0].textContent = 'Gold price per gram (';
        tip.textContent = 'The current market price of one gram of gold. Check Google Finance, a jewellery app, or your bank for today\'s rate.';
        exp.textContent = 'The gold standard is used by most scholars today for its stability. The silver standard sets a lower threshold, meaning more people give Zakat and more wealth reaches the poor.';
        prompt.textContent = '↳ Enter the current price of gold per gram.';
        document.getElementById('metalPrice').value = document.getElementById('metalPrice').dataset.prevGold || 7400;
      } else {
        document.getElementById('metalPrice').dataset.prevGold = document.getElementById('metalPrice').value;
        lbl.childNodes[0].textContent = 'Silver price per gram (';
        tip.textContent = 'The current market price of one gram of silver. You can check this on Google or a precious metals website.';
        exp.textContent = 'Many contemporary scholars (including Sheikh Yusuf al-Qaradawi) prefer the silver standard because its lower threshold means more Muslims are included and more wealth reaches the poor.';
        prompt.textContent = '↳ Enter the current price of silver per gram.';
        document.getElementById('metalPrice').value = document.getElementById('metalPrice').dataset.prevSilver || 95;
      }
      calculate();
    }

    function fmt(n) {
      return currSymbol + Math.round(n).toLocaleString('en-IN');
    }

    function calculate() {
      const metalPrice = parseFloat(document.getElementById('metalPrice').value) || 0;
      const weight = nisabMode === 'gold' ? GOLD_W : SILVER_W;
      const nisab = metalPrice * weight;
      document.getElementById('nisabValue').value = Math.round(nisab);

      const cash         = parseFloat(document.getElementById('cash').value) || 0;
      const goldSilver   = parseFloat(document.getElementById('goldSilver').value) || 0;
      const inventory    = parseFloat(document.getElementById('inventory').value) || 0;
      const investments  = parseFloat(document.getElementById('investments').value) || 0;
      const receivables  = parseFloat(document.getElementById('receivables').value) || 0;
      const debts        = parseFloat(document.getElementById('debts').value) || 0;
      const bills        = parseFloat(document.getElementById('bills').value) || 0;

      const totalAssets = cash + goldSilver + inventory + investments + receivables;
      const totalLiab   = debts + bills;
      const net         = Math.max(0, totalAssets - totalLiab);
      const eligible    = net >= nisab && nisab > 0;
      const zakat       = eligible ? net * 0.025 : 0;

      document.getElementById('resultArea').style.display = 'block';
      document.getElementById('rTotalAssets').textContent = fmt(totalAssets);
      document.getElementById('rLiabilities').textContent = fmt(totalLiab);
      document.getElementById('rNetWealth').textContent   = fmt(net);
      document.getElementById('rZakat').textContent       = fmt(zakat);

      const statusEl   = document.getElementById('nisabStatusEl');
      const statusText = document.getElementById('nisabStatusText');

      if (nisab === 0) {
        statusEl.className = 'nisab-status ineligible';
        statusEl.querySelector('i').className = 'ti ti-alert-triangle';
        statusText.textContent = 'Please enter the current metal price above so we can calculate your Nisab threshold.';
      } else if (eligible) {
        statusEl.className = 'nisab-status eligible';
        statusEl.querySelector('i').className = 'ti ti-check';
        statusText.textContent = 'Your net wealth (' + fmt(net) + ') is above the Nisab threshold (' + fmt(nisab) + '). Zakat is obligatory on you — may Allāh accept it.';
      } else {
        statusEl.className = 'nisab-status ineligible';
        statusEl.querySelector('i').className = 'ti ti-info-circle';
        statusText.textContent = 'Your net wealth (' + fmt(net) + ') is below the Nisab threshold (' + fmt(nisab) + '). Zakat is not yet due, but voluntary Ṣadaqah (charity) is always deeply rewarded.';
      }
    }

    calculate();
  </script>
</body>
</html>
