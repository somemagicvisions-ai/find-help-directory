# find-help-directory
This is a free, open-source tool built to help people experiencing homelessness or housing insecurity find resources nationwide. No data is collected, no account required, no ads.  All resources are verified and link directly to legitimate organizations — no middlemen, no tracking.
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Find Help — Nationwide Resource Directory</title>
<meta name="description" content="Free nationwide directory of housing, food, healthcare, jobs, and emergency resources for people experiencing homelessness or housing insecurity. No account required.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,600;1,400&family=Source+Sans+3:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #f6f4ef;
  --surface: #ffffff;
  --surface2: #eeebe3;
  --border: #dedad0;
  --border2: #c8c3b5;
  --text: #19180f;
  --text2: #5c5a52;
  --text3: #98958a;
  --accent: #1e4d35;
  --accent-hover: #163a28;
  --accent-light: #e4f0ea;
  --accent-mid: #b8d9c5;
  --red: #b83228; --red-bg: #fceeec;
  --blue: #17427a; --blue-bg: #eaf1fb;
  --green: #1a5430; --green-bg: #e8f3ec;
  --amber: #7a4500; --amber-bg: #fdf3e3;
  --purple: #452080; --purple-bg: #f2edfb;
  --teal: #0a4d5e; --teal-bg: #e3f3f7;
  --rose: #7a1f40; --rose-bg: #fbeaf0;
  --radius: 10px;
  --shadow: 0 1px 4px rgba(0,0,0,.07), 0 1px 2px rgba(0,0,0,.04);
  --shadow-md: 0 4px 16px rgba(0,0,0,.09);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'Source Sans 3',sans-serif;background:var(--bg);color:var(--text);font-size:15px;line-height:1.65;min-height:100vh}

/* ── HEADER ── */
.site-header{background:var(--accent);color:#fff;padding:2.75rem 1.5rem 2.25rem;text-align:center;position:relative;overflow:hidden}
.site-header::before{content:'';position:absolute;inset:0;background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");pointer-events:none}
.header-inner{position:relative;z-index:1}
.site-header h1{font-family:'Lora',serif;font-size:clamp(2rem,5vw,3rem);font-weight:600;letter-spacing:-.02em;margin-bottom:.5rem;line-height:1.15}
.site-header .tagline{font-size:.95rem;opacity:.8;max-width:480px;margin:0 auto .2rem;font-weight:300}
.hotline-bar{display:inline-flex;align-items:center;gap:8px;background:rgba(255,255,255,.14);border:1px solid rgba(255,255,255,.22);border-radius:999px;padding:7px 18px;font-size:.85rem;margin-top:1.1rem;font-weight:500;letter-spacing:.01em}
.hotline-bar a{color:#fff;text-decoration:none}
.hotline-bar a:hover{text-decoration:underline}

/* ── TOOLBAR ── */
.toolbar{background:var(--surface);border-bottom:1px solid var(--border);padding:.6rem 1rem;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap}
.toolbar-left{display:flex;align-items:center;gap:8px;flex:1;min-width:200px}
.search-wrap{position:relative;flex:1;max-width:500px}
.search-wrap svg{position:absolute;left:11px;top:50%;transform:translateY(-50%);color:var(--text3);pointer-events:none}
#global-search{width:100%;height:40px;padding:0 12px 0 36px;border:1.5px solid var(--border2);border-radius:var(--radius);font-family:inherit;font-size:14px;background:var(--bg);color:var(--text);outline:none;transition:border-color .15s}
#global-search:focus{border-color:var(--accent);background:var(--surface)}
#global-search::placeholder{color:var(--text3)}
.toolbar-right{display:flex;align-items:center;gap:8px}
.tool-btn{height:36px;padding:0 14px;border-radius:var(--radius);border:1.5px solid var(--border2);background:var(--surface);color:var(--text2);font-family:inherit;font-size:13px;font-weight:500;cursor:pointer;display:inline-flex;align-items:center;gap:6px;transition:all .15s;white-space:nowrap}
.tool-btn:hover{border-color:var(--border2);background:var(--surface2);color:var(--text)}
.tool-btn.lang-active{background:var(--accent-light);border-color:var(--accent-mid);color:var(--accent)}
@media print{.tool-btn{display:none!important}}

/* ── TABS ── */
.tab-nav-wrap{background:var(--surface);border-bottom:1px solid var(--border);position:sticky;top:0;z-index:50}
.tab-nav{display:flex;overflow-x:auto;max-width:1040px;margin:0 auto;padding:0 .75rem;scrollbar-width:none;gap:2px}
.tab-nav::-webkit-scrollbar{display:none}
.tab-btn{flex-shrink:0;padding:13px 16px;border:none;background:none;font-family:inherit;font-size:.875rem;font-weight:400;color:var(--text2);cursor:pointer;border-bottom:2.5px solid transparent;transition:all .15s;white-space:nowrap;display:flex;align-items:center;gap:5px;letter-spacing:.01em}
.tab-btn:hover{color:var(--text)}
.tab-btn.active{color:var(--accent);border-bottom-color:var(--accent);font-weight:600}

/* ── MAIN ── */
.main{max-width:1040px;margin:0 auto;padding:1.75rem 1.25rem 5rem}
.tab-panel{display:none}.tab-panel.active{display:block}

/* ── SECTIONS ── */
.section{margin-bottom:2.5rem}
.section-label{font-size:.7rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--text3);margin-bottom:3px;display:flex;align-items:center;gap:6px}
.section-note{font-size:.82rem;color:var(--text2);margin-bottom:.85rem;padding-bottom:.85rem;border-bottom:1px solid var(--border);line-height:1.5}

/* ── GRID ── */
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(268px,1fr));gap:10px}

/* ── CARDS ── */
.card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:.95rem 1.15rem;display:flex;flex-direction:column;gap:7px;box-shadow:var(--shadow);transition:border-color .15s,box-shadow .15s}
.card:hover{border-color:var(--border2);box-shadow:var(--shadow-md)}
.card-top{display:flex;align-items:flex-start;justify-content:space-between;gap:8px}
.card-name{font-size:.93rem;font-weight:600;color:var(--text);line-height:1.3}
.badge{font-size:.65rem;padding:2px 8px;border-radius:999px;white-space:nowrap;flex-shrink:0;font-weight:600;letter-spacing:.03em;text-transform:uppercase}
.b-emergency{background:var(--red-bg);color:var(--red)}
.b-housing{background:var(--blue-bg);color:var(--blue)}
.b-food{background:var(--green-bg);color:var(--green)}
.b-health{background:var(--red-bg);color:var(--red)}
.b-jobs{background:var(--amber-bg);color:var(--amber)}
.b-edu{background:var(--purple-bg);color:var(--purple)}
.b-immed{background:var(--purple-bg);color:var(--purple)}
.b-multi{background:var(--surface2);color:var(--text2)}
.b-group{background:var(--purple-bg);color:var(--purple)}
.b-sober{background:var(--green-bg);color:var(--green)}
.b-second{background:var(--blue-bg);color:var(--blue)}
.b-reentry{background:var(--amber-bg);color:var(--amber)}
.b-rehab{background:var(--red-bg);color:var(--red)}
.b-mental{background:var(--rose-bg);color:var(--rose)}
.b-standard{background:var(--surface2);color:var(--text2)}
.b-veterans{background:var(--green-bg);color:var(--green)}
.b-dv{background:var(--rose-bg);color:var(--rose)}
.b-youth{background:var(--purple-bg);color:var(--purple)}
.b-rental{background:var(--blue-bg);color:var(--blue)}
.b-longterm{background:var(--teal-bg);color:var(--teal)}
.b-directory{background:var(--surface2);color:var(--text2)}
.b-coliving{background:var(--teal-bg);color:var(--teal)}
.b-student{background:var(--amber-bg);color:var(--amber)}
.b-private{background:var(--teal-bg);color:var(--teal)}
.card-desc{font-size:.82rem;color:var(--text2);line-height:1.55}
.card-foot{display:flex;flex-wrap:wrap;align-items:center;gap:10px;margin-top:3px}
.card-link{font-size:.8rem;color:var(--accent);text-decoration:none;display:inline-flex;align-items:center;gap:3px;font-weight:600}
.card-link:hover{text-decoration:underline}
.phone-chip{font-size:.78rem;color:var(--text2);display:inline-flex;align-items:center;gap:4px}

/* ── HERO STRIP ── */
.hero-strip{background:var(--accent-light);border:1px solid var(--accent-mid);border-radius:var(--radius);padding:1.15rem 1.4rem;margin-bottom:1.75rem;display:flex;align-items:flex-start;gap:14px}
.hero-icon{font-size:1.8rem;flex-shrink:0;line-height:1}
.hero-strip h2{font-family:'Lora',serif;font-size:1.05rem;font-weight:600;color:var(--accent);margin-bottom:4px}
.hero-strip p{font-size:.83rem;color:#225438;line-height:1.55}

/* ── ABOUT TAB ── */
.about-wrap{max-width:680px}
.about-wrap h2{font-family:'Lora',serif;font-size:1.5rem;font-weight:600;color:var(--text);margin-bottom:.75rem;line-height:1.25}
.about-wrap p{font-size:.9rem;color:var(--text2);line-height:1.7;margin-bottom:1rem}
.about-wrap h3{font-family:'Lora',serif;font-size:1.05rem;font-weight:600;color:var(--text);margin:.25rem 0 .5rem}
.about-list{list-style:none;padding:0;margin-bottom:1.25rem}
.about-list li{font-size:.88rem;color:var(--text2);padding:.3rem 0 .3rem 1.4rem;position:relative;border-bottom:1px solid var(--border);line-height:1.5}
.about-list li::before{content:'→';position:absolute;left:0;color:var(--accent);font-weight:600}
.about-divider{border:none;border-top:1px solid var(--border);margin:1.75rem 0}
.contact-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px;margin-top:.75rem}
.contact-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);padding:.9rem 1rem}
.contact-card strong{display:block;font-size:.82rem;font-weight:600;color:var(--text);margin-bottom:3px}
.contact-card span{font-size:.8rem;color:var(--text2)}
.contact-card a{color:var(--accent);text-decoration:none;font-size:.8rem}
.contact-card a:hover{text-decoration:underline}

/* ── NO RESULTS ── */
.no-results{text-align:center;padding:3.5rem 1rem;color:var(--text3);font-size:.9rem}
.no-results strong{color:var(--text2)}

/* ── FOOTER ── */
.site-footer{text-align:center;padding:1.5rem 1rem 2.5rem;font-size:.78rem;color:var(--text3);border-top:1px solid var(--border)}
.site-footer a{color:var(--text3);text-decoration:underline}

/* ── PRINT ── */
@media print{
  .site-header{background:#1e4d35!important;-webkit-print-color-adjust:exact;print-color-adjust:exact}
  .tab-nav-wrap,.toolbar{display:none!important}
  .tab-panel{display:block!important}
  .main{padding:0}
  .card{break-inside:avoid;border:1px solid #ccc!important;box-shadow:none!important}
  .site-footer{display:none}
}

/* ── MOBILE ── */
@media(max-width:520px){
  .site-header{padding:2rem 1rem 1.75rem}
  .main{padding:1.1rem .875rem 3.5rem}
  .grid{grid-template-columns:1fr}
  .tab-btn{padding:11px 12px;font-size:.82rem}
  .toolbar{padding:.5rem .75rem}
  .hero-strip{flex-direction:column;gap:8px}
}
</style>
</head>
<body>

<header class="site-header">
  <div class="header-inner">
    <h1 data-en="Find Help Near You" data-es="Encuentra Ayuda Cerca de Ti">Find Help Near You</h1>
    <p class="tagline" data-en="Free nationwide resource directory — no account, no fees, no judgment" data-es="Directorio nacional gratuito — sin cuenta, sin costo, sin juicio">Free nationwide resource directory — no account, no fees, no judgment</p>
    <div class="hotline-bar">
      📞 <strong><span data-en="Dial or text" data-es="Llama o envía texto">Dial or text</span> <a href="tel:211">211</a></strong> — <span data-en="free 24/7 helpline for any need" data-es="línea gratuita 24/7 para cualquier necesidad">free 24/7 helpline for any need</span>
    </div>
  </div>
</header>

<div class="toolbar">
  <div class="toolbar-left">
    <div class="search-wrap">
      <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" aria-hidden="true"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
      <input type="search" id="global-search" placeholder="Search all resources…" oninput="filterAll()" autocomplete="off" aria-label="Search all resources">
    </div>
  </div>
  <div class="toolbar-right">
    <button class="tool-btn" id="lang-btn" onclick="toggleLang()" aria-label="Switch to Spanish">
      🌐 <span id="lang-label">Español</span>
    </button>
    <button class="tool-btn" onclick="window.print()" aria-label="Print this page">
      🖨️ <span data-en="Print" data-es="Imprimir">Print</span>
    </button>
  </div>
</div>

<nav class="tab-nav-wrap" aria-label="Resource categories">
  <div class="tab-nav" id="tab-nav"></div>
</nav>

<main class="main" id="main-content" role="main"></main>

<footer class="site-footer">
  <span data-en="Resources verified May 2025 · Always call ahead — hours change · For emergencies call 911 · This directory is free to use, share, and embed." data-es="Recursos verificados mayo 2025 · Llame antes — los horarios cambian · En emergencias llame al 911 · Este directorio es gratuito para usar, compartir e integrar.">Resources verified May 2025 · Always call ahead — hours change · For emergencies call 911 · This directory is free to use, share, and embed.</span>
</footer>

<script>
let lang = 'en';

const TABS = [
  { id:'start',     en:'Start Here',        es:'Empezar Aquí',    icon:'⚡' },
  { id:'housing',   en:'Housing',           es:'Vivienda',         icon:'🏠' },
  { id:'group',     en:'Group & Recovery',  es:'Grupos y Recuperación', icon:'🏘️' },
  { id:'food',      en:'Food',              es:'Alimentos',        icon:'🍎' },
  { id:'health',    en:'Healthcare',        es:'Salud',            icon:'❤️' },
  { id:'jobs',      en:'Jobs',              es:'Empleo',           icon:'💼' },
  { id:'education', en:'Education',         es:'Educación',        icon:'📚' },
  { id:'immediate', en:'Immediate Help',    es:'Ayuda Inmediata',  icon:'🔧' },
  { id:'about',     en:'About & Donate',    es:'Acerca & Donar',   icon:'ℹ️' },
];

const DATA = {

start: { hero:true, sections:[
  { en:'Best first contacts', es:'Primeros contactos', note_en:"These cover the widest range of needs — start here if you're not sure where to go.", note_es:'Estos cubren la mayor variedad de necesidades — empiece aquí si no sabe adónde ir.', cards:[
    { name:'211.org', badge:'b-immed', en:'Call, text, or search online to find verified local resources for any need — shelter, food, health, utilities, and more. Available nationwide, 24/7, in multiple languages.', es:'Llame, envíe un texto o busque en línea para encontrar recursos locales verificados — refugio, alimentos, salud, servicios y más. Disponible en todo el país, 24/7, en varios idiomas.', url:'https://www.211.org', link:'211.org', phone:'Dial or text 211' },
    { name:'Crisis Text Line', badge:'b-immed', en:'Free, confidential crisis support by text 24/7. No phone call needed — works on any basic phone.', es:'Apoyo confidencial gratuito por texto, 24/7. No se necesita llamada telefónica.', url:'https://www.crisistextline.org', link:'crisistextline.org', phone:'Text HOME to 741741' },
    { name:'USA.gov – Emergency Housing', badge:'b-emergency', en:'Official federal guide linking to local shelters, public housing, rental assistance, and programs for veterans, youth, and domestic violence survivors.', es:'Guía federal oficial con enlaces a refugios locales, vivienda pública, asistencia de alquiler y programas para veteranos, jóvenes y sobrevivientes de violencia doméstica.', url:'https://www.usa.gov/emergency-housing', link:'usa.gov/emergency-housing' },
    { name:'Benefits.gov', badge:'b-multi', en:'Find every federal benefit you may qualify for — SNAP, Medicaid, housing vouchers, utility assistance, and more. Answer a short questionnaire. No account required.', es:'Encuentre todos los beneficios federales para los que puede calificar — SNAP, Medicaid, vales de vivienda y más. Responda un cuestionario corto. Sin cuenta requerida.', url:'https://www.benefits.gov', link:'benefits.gov' },
    { name:'FindHelp.org', badge:'b-directory', en:'ZIP-code search for free and reduced-cost housing, food, financial aid, and healthcare. One of the most comprehensive social services directories in the U.S.', es:'Búsqueda por código postal para vivienda, alimentos, ayuda financiera y atención médica gratuita o de bajo costo.', url:'https://www.findhelp.org', link:'findhelp.org' },
    { name:'988 Suicide & Crisis Lifeline', badge:'b-health', en:'Free, confidential 24/7 crisis support by call or text. Also provides referrals to local mental health services and emergency housing.', es:'Apoyo confidencial gratuito 24/7 por llamada o texto. También proporciona referencias a servicios de salud mental locales.', url:'https://988lifeline.org', link:'988lifeline.org', phone:'Call or text 988' },
  ]},
]},

housing: { sections:[
  { en:'Shelter finders', es:'Buscadores de refugio', note_en:'Search for emergency shelter and housing by ZIP code.', note_es:'Busque refugio de emergencia y vivienda por código postal.', cards:[
    { name:'HUD Find Shelter', badge:'b-housing', en:'Official U.S. government shelter search. Enter any ZIP to find emergency shelters, transitional housing, healthcare, and clothing resources. Covers every state.', es:'Búsqueda oficial de refugios del gobierno de EE.UU. Ingrese cualquier código postal para encontrar refugios de emergencia, vivienda transitoria, atención médica y ropa.', url:'https://www.hud.gov/findshelter', link:'hud.gov/findshelter' },
    { name:'Homeless Shelter Directory', badge:'b-directory', en:'Nationwide database of shelters, soup kitchens, food banks, Section 8, and public housing. Also lists volunteer and donation opportunities.', es:'Base de datos nacional de refugios, comedores, bancos de alimentos, Sección 8 y vivienda pública.', url:'https://www.homelessshelterdirectory.org', link:'homelessshelterdirectory.org' },
    { name:'Shelter Listings', badge:'b-directory', en:'Community-maintained database of 3,000+ programs — emergency shelters, day shelters, halfway houses, and low-income housing. Filter by city, state, type, or ZIP.', es:'Base de datos de más de 3,000 programas — refugios de emergencia, refugios diurnos, casas a mitad de camino y vivienda de bajos ingresos.', url:'https://www.shelterlistings.org', link:'shelterlistings.org' },
    { name:'LowIncomeHousing.us', badge:'b-housing', en:'Directory of HUD, Section 8, public housing, senior housing, and income-based housing listings across all 50 states. Search by city and state.', es:'Directorio de viviendas HUD, Sección 8, vivienda pública, vivienda para personas mayores y vivienda basada en ingresos en los 50 estados.', url:'https://www.lowincomehousing.us', link:'lowincomehousing.us' },
  ]},
  { en:'Rental assistance & long-term housing', es:'Asistencia de alquiler y vivienda a largo plazo', note_en:'Programs that help pay rent or secure affordable permanent housing.', note_es:'Programas que ayudan a pagar el alquiler o asegurar vivienda permanente asequible.', cards:[
    { name:'Section 8 / Housing Choice Voucher', badge:'b-rental', en:'The main federal rent subsidy. A voucher pays part of your rent in private housing. Apply through your local Public Housing Agency. Waitlists are common — apply at multiple PHAs.', es:'El principal subsidio federal de alquiler. Un vale paga parte de su alquiler en vivienda privada. Solicite a través de su Agencia de Vivienda Pública local.', url:'https://www.hud.gov/topics/housing_choice_voucher_program_section_8', link:'hud.gov – Section 8' },
    { name:'HUD Resource Locator', badge:'b-rental', en:'Find your local Public Housing Agency, affordable housing listings, and HUD-funded programs — searchable by address or ZIP.', es:'Encuentre su Agencia de Vivienda Pública local, listados de vivienda asequible y programas financiados por HUD.', url:'https://resources.hud.gov', link:'resources.hud.gov' },
    { name:'National Low Income Housing Coalition', badge:'b-longterm', en:'Tracks affordable housing availability and emergency rental programs state by state. Direct assistance page links to housing and utility aid by state.', es:'Rastrea la disponibilidad de vivienda asequible y programas de alquiler de emergencia estado por estado.', url:'https://nlihc.org/direct-assistance', link:'nlihc.org/direct-assistance' },
    { name:'Emergency Housing Vouchers (HUD)', badge:'b-rental', en:'70,000 housing vouchers for people who are homeless, fleeing domestic violence, or at high risk of housing instability. Apply through your local Public Housing Authority.', es:'70,000 vales de vivienda para personas sin hogar, que huyen de violencia doméstica o en alto riesgo de inestabilidad habitacional.', url:'https://www.hud.gov/helping-americans', link:'hud.gov – EHV' },
  ]},
  { en:'Veterans', es:'Veteranos', note_en:'Specialized housing programs for veterans experiencing homelessness.', note_es:'Programas de vivienda especializados para veteranos sin hogar.', cards:[
    { name:'HUD-VASH Program', badge:'b-veterans', en:'Combines HUD rental vouchers with VA case management for homeless veterans. Contact your nearest VA medical center or the National Homeless Veteran Call Center to start.', es:'Combina vales de alquiler de HUD con gestión de casos de VA para veteranos sin hogar.', url:'https://www.hud.gov/helping-americans', link:'hud.gov – HUD-VASH', phone:'1-877-424-3838' },
    { name:'VA Homeless Programs', badge:'b-veterans', en:'Free 24/7 hotline for veterans facing homelessness. Connects to VA housing, emergency shelter, and local support anywhere in the country.', es:'Línea directa gratuita 24/7 para veteranos que enfrentan la falta de vivienda.', url:'https://www.va.gov/homeless', link:'va.gov/homeless', phone:'1-877-424-3838' },
    { name:'DVNF – Homeless to Housing', badge:'b-veterans', en:'Offers up to $2,000 for security deposits and first month\'s rent, plus household essentials. Open to all veterans.', es:'Ofrece hasta $2,000 para depósitos de seguridad y primer mes de alquiler. Abierto a todos los veteranos.', url:'https://www.dvnf.org/homeless-to-housing', link:'dvnf.org/homeless-to-housing' },
    { name:'National Coalition for Homeless Veterans', badge:'b-veterans', en:'Network of service providers across the U.S. Links veterans to local housing, employment, and legal services.', es:'Red de proveedores de servicios en los EE.UU. Conecta a veteranos con vivienda local, empleo y servicios legales.', url:'https://nchv.org', link:'nchv.org' },
  ]},
  { en:'Domestic violence survivors', es:'Sobrevivientes de violencia doméstica', note_en:'Safe housing options for people fleeing abuse.', note_es:'Opciones de vivienda segura para personas que huyen del abuso.', cards:[
    { name:'National DV Hotline – Safe Housing', badge:'b-dv', en:'Connects DV survivors to local emergency shelter, transitional housing, and safety planning. Confidential 24/7 by call, text, or chat. Multilingual.', es:'Conecta a sobrevivientes de VD con refugio de emergencia local, vivienda transitoria y planificación de seguridad. Confidencial 24/7.', url:'https://www.thehotline.org/resources/housing-resources', link:'thehotline.org', phone:'1-800-799-7233' },
    { name:'DOJ Transitional Housing Program', badge:'b-dv', en:'Funds local organizations to provide 6–24 months of transitional housing for DV, sexual assault, and stalking survivors, with counseling, childcare, and job training.', es:'Financia organizaciones locales para proporcionar de 6 a 24 meses de vivienda transitoria para sobrevivientes de VD.', url:'https://www.justice.gov/ovw/transitional-housing-program', link:'justice.gov – OVW' },
  ]},
  { en:'Youth & young adults', es:'Jóvenes y adultos jóvenes', note_en:'Housing resources for people under 25.', note_es:'Recursos de vivienda para personas menores de 25 años.', cards:[
    { name:'National Runaway Safeline', badge:'b-youth', en:'Free, confidential 24/7 support for runaway and homeless youth. Provides shelter referrals, free bus tickets home or to safe housing, and crisis counseling.', es:'Apoyo confidencial gratuito 24/7 para jóvenes fugitivos y sin hogar. Proporciona referencias de refugio, boletos de autobús gratuitos y asesoramiento de crisis.', url:'https://www.1800runaway.org', link:'1800runaway.org', phone:'1-800-786-2929' },
    { name:'True Colors United', badge:'b-youth', en:'Focuses on LGBTQ+ youth homelessness. National directory of affirming shelters and housing programs for LGBTQ+ young people.', es:'Se enfoca en la falta de vivienda de jóvenes LGBTQ+. Directorio nacional de refugios y programas de vivienda afirmativos.', url:'https://truecolorsunited.org/find-help', link:'truecolorsunited.org/find-help' },
  ]},
  { en:'Multi-service organizations', es:'Organizaciones de múltiples servicios', note_en:'Large networks offering shelter, food, case management, and more.', note_es:'Grandes redes que ofrecen refugio, alimentos, gestión de casos y más.', cards:[
    { name:'Salvation Army – Find Shelter', badge:'b-multi', en:'Operates emergency shelters, transitional living, and long-term supportive housing near every ZIP code. Serves individuals, families, youth, and veterans.', es:'Opera refugios de emergencia, vida transitoria y vivienda de apoyo a largo plazo cerca de cada código postal.', url:'https://www.salvationarmyusa.org/usn/find-help', link:'salvationarmyusa.org' },
    { name:'Catholic Charities USA', badge:'b-multi', en:'One of the largest nonprofit networks in the U.S. Local branches offer emergency shelter, transitional housing, and housing navigation. Open to all regardless of faith.', es:'Una de las redes sin fines de lucro más grandes de los EE.UU. Abierta a todos independientemente de la fe.', url:'https://www.catholiccharitiesusa.org/find-help', link:'catholiccharitiesusa.org/find-help' },
    { name:'NAEH – CoC Finder', badge:'b-multi', en:'Find your local Continuum of Care — the coordinated network of shelters and housing programs in your county. The official entry point to most federally funded housing help.', es:'Encuentre su Continuo de Atención local — la red coordinada de refugios y programas de vivienda en su condado.', url:'https://endhomelessness.org/how-to-get-help-experiencing-homelessness', link:'endhomelessness.org' },
  ]},
]},

group: { sections:[
  { en:'Group housing & sober living', es:'Vivienda grupal y vida sobria', note_en:'Shared, affordable communal homes for people in recovery or needing stable housing.', note_es:'Hogares comunitarios compartidos y asequibles para personas en recuperación.', cards:[
    { name:'Oxford House', badge:'b-group', en:'Largest network of peer-run sober group homes in the U.S. — 2,900+ self-governing houses nationwide. Residents share expenses (~$400/mo including utilities), stay as long as they remain sober. Homes for men, women, and women with children.', es:'La red más grande de hogares grupales sobrios dirigidos por pares en EE.UU. — más de 2,900 casas autogobernadas. Los residentes comparten gastos (~$400/mes incluyendo servicios).', url:'https://www.oxfordhouse.org', link:'oxfordhouse.org' },
    { name:'Sober House Directory', badge:'b-sober', en:'Nationwide searchable directory of sober living homes, Oxford Houses, and recovery residences. Search by state and city. Strictly sober living only.', es:'Directorio de búsqueda nacional de hogares de vida sobria, Oxford Houses y residencias de recuperación.', url:'https://soberhousedirectory.com', link:'soberhousedirectory.com' },
    { name:'Shelter Listings – Group Homes', badge:'b-directory', en:'Database of 3,000+ programs including group homes, rooming houses, halfway houses, and low-income shared housing. Filter by type, city, state, or ZIP.', es:'Base de datos de más de 3,000 programas que incluye hogares grupales, casas de habitaciones y vivienda compartida de bajos ingresos.', url:'https://www.shelterlistings.org/type/group-homes.html', link:'shelterlistings.org – group homes' },
    { name:'NARR – State Affiliate Finder', badge:'b-standard', en:'The National Alliance for Recovery Residences certifies 2,500+ homes across 30 states. Use the finder to locate vetted, certified group homes in your state.', es:'La Alianza Nacional para Residencias de Recuperación certifica más de 2,500 hogares en 30 estados.', url:'https://narronline.org/affiliate-services/find-a-recovery-residence', link:'narronline.org' },
  ]},
  { en:'Private sector room rentals & co-living', es:'Alquiler de habitaciones y co-living del sector privado', note_en:'Market-rate room rental platforms — often 40–50% cheaper than renting alone. No lease required on many listings.', note_es:'Plataformas de alquiler de habitaciones a precio de mercado — a menudo entre 40 y 50% más baratas que alquilar solo.', cards:[
    { name:'PadSplit', badge:'b-private', en:'The largest workforce co-living marketplace in the U.S. — 30,000+ furnished rooms in shared homes across 30+ cities. Weekly payments, no lease, no deposit, no minimum credit score. Utilities and WiFi included. Designed specifically for low-income workers.', es:'El mayor mercado de co-living para trabajadores en EE.UU. — más de 30,000 habitaciones amuebladas en 30+ ciudades. Pagos semanales, sin contrato, sin depósito, sin puntaje de crédito mínimo.', url:'https://www.padsplit.com', link:'padsplit.com' },
    { name:'SpareRoom', badge:'b-coliving', en:'Search for rooms and roommates across the U.S. One of the largest room-rental marketplaces — post and browse listings for free. Good for finding shared houses quickly.', es:'Busque habitaciones y compañeros de cuarto en todo EE.UU. Uno de los mercados de alquiler de habitaciones más grandes — publicar y explorar listados es gratuito.', url:'https://www.spareroom.com', link:'spareroom.com' },
    { name:'Roomies.com', badge:'b-coliving', en:'Room rental marketplace with listings nationwide. Filters for furnished, utilities-included, LGBTQ+-friendly, and pet-friendly rooms. Month-to-month leases common.', es:'Mercado de alquiler de habitaciones con listados en todo el país. Filtros para habitaciones amuebladas, con servicios incluidos, aptas para LGBTQ+ y mascotas.', url:'https://www.roomies.com', link:'roomies.com' },
    { name:'Roomster', badge:'b-coliving', en:'Over 21,000 rooms for rent nationwide. Search by city, price, and move-in date. Includes roommate matching and background check options.', es:'Más de 21,000 habitaciones en alquiler en todo el país. Búsqueda por ciudad, precio y fecha de entrada.', url:'https://roomster.com', link:'roomster.com' },
    { name:'Coliving.com', badge:'b-coliving', en:'Aggregates co-living spaces nationwide — furnished rooms with individual leases, utilities included, flexible terms. Useful for people moving to a new city without a local rental history.', es:'Agrega espacios de co-living en todo el país — habitaciones amuebladas con arrendamientos individuales, servicios incluidos, términos flexibles.', url:'https://coliving.com', link:'coliving.com' },
    { name:'PadMapper', badge:'b-coliving', en:'Aggregates listings from Zillow, Craigslist, Apartments.com, and more onto an interactive map. Filter by room type and price. Good for a fast visual overview of affordable rooms in any city.', es:'Agrega listados en un mapa interactivo. Filtre por tipo de habitación y precio. Bueno para una visión rápida de habitaciones asequibles en cualquier ciudad.', url:'https://www.padmapper.com', link:'padmapper.com' },
  ]},
  { en:'Second step & step-up housing', es:'Segundo paso y vivienda escalonada', note_en:'Bridge programs between emergency shelter and permanent housing.', note_es:'Programas puente entre el refugio de emergencia y la vivienda permanente.', cards:[
    { name:'HUD Rapid Re-Housing', badge:'b-second', en:'Short-term rental assistance and support services to move people quickly from homelessness into stable housing. Available through local CoCs. Call 211 to find your local program.', es:'Asistencia de alquiler a corto plazo y servicios de apoyo para mover a las personas rápidamente del desamparo a una vivienda estable.', url:'https://www.hud.gov/topics/homelessness/rrh', link:'hud.gov – RRH', phone:'Dial 211' },
    { name:'HUD Permanent Supportive Housing', badge:'b-second', en:'Affordable housing with ongoing support services — mental health care, substance use treatment, case management — for people with chronic homelessness. Apply through your local CoC or 211.', es:'Vivienda asequible con servicios de apoyo continuos para personas con falta de vivienda crónica.', url:'https://www.hud.gov/topics/homelessness/psh', link:'hud.gov – PSH' },
    { name:'SAMHSA – PATH Program', badge:'b-second', en:'Projects for Assistance in Transition from Homelessness. Funds street outreach, case management, and housing placement for people with serious mental illness. Find your state\'s contact through SAMHSA.', es:'Proyectos de Asistencia en la Transición del Desamparo. Financia trabajo de calle, gestión de casos y colocación de vivienda.', url:'https://www.samhsa.gov/homelessness-programs-resources/hpsa-programs/path', link:'samhsa.gov – PATH' },
    { name:'NAEH – CoC Finder (Step-Up Gateway)', badge:'b-second', en:'Your local Continuum of Care is the coordinated gateway to step-up housing — from emergency shelter to transitional, then permanent housing. Second-step placements typically originate here.', es:'Su Continuo de Atención local es la puerta de entrada coordinada a la vivienda escalonada.', url:'https://endhomelessness.org/how-to-get-help-experiencing-homelessness', link:'endhomelessness.org' },
  ]},
  { en:'Reentry & post-incarceration housing', es:'Vivienda de reinserción post-encarcelamiento', note_en:'Housing for people leaving jail, prison, or detention.', note_es:'Vivienda para personas que salen de la cárcel, prisión o detención.', cards:[
    { name:'BOP Residential Reentry Centers', badge:'b-reentry', en:'Federal Bureau of Prisons halfway houses nationwide. Provide structured housing, employment counseling, job placement, and financial management for people nearing release from federal prison.', es:'Casas a mitad de camino de la Oficina Federal de Prisiones en todo el país.', url:'https://www.bop.gov/about/facilities/residential_reentry_management_centers.jsp', link:'bop.gov – RRC Locator' },
    { name:'ReentryPrograms.com', badge:'b-reentry', en:'State-by-state directory of reentry programs including transitional housing, halfway houses, and residential reentry centers for people leaving incarceration.', es:'Directorio estado por estado de programas de reinserción que incluye vivienda transitoria y casas a mitad de camino.', url:'https://www.reentryprograms.com', link:'reentryprograms.com' },
    { name:'Second Chance Act – DOJ', badge:'b-reentry', en:'Federal program funding nonprofit and government reentry organizations providing transitional housing, job training, and substance use treatment for people leaving incarceration.', es:'Programa federal que financia organizaciones de reinserción que proporcionan vivienda transitoria, capacitación laboral y tratamiento por uso de sustancias.', url:'https://bja.ojp.gov/programs/reentry', link:'bja.ojp.gov/programs/reentry' },
  ]},
  { en:'Rehabilitation & recovery housing', es:'Vivienda de rehabilitación y recuperación', note_en:'Structured residential programs for addiction and mental health recovery.', note_es:'Programas residenciales estructurados para la recuperación de adicciones y salud mental.', cards:[
    { name:'SAMHSA Treatment Locator', badge:'b-rehab', en:'Official federal locator for residential treatment — detox, rehab, and recovery housing for substance use and mental health. Search by ZIP, service type, and payment accepted (including no-cost). Updated continuously.', es:'Localizador federal oficial de tratamiento residencial — desintoxicación, rehabilitación y vivienda de recuperación.', url:'https://findtreatment.gov', link:'findtreatment.gov', phone:'1-800-662-4357' },
    { name:'HUD Recovery Housing Program', badge:'b-rehab', en:'Federal funds to states to develop transitional housing for people in addiction recovery. Contact your state housing authority to find RHP placements in your area.', es:'Fondos federales para los estados para desarrollar vivienda transitoria para personas en recuperación de adicciones.', url:'https://www.hud.gov/program_offices/comm_planning/rhp', link:'hud.gov – RHP' },
    { name:'NAMI – Housing Resources', badge:'b-mental', en:'National Alliance on Mental Illness state-by-state guide to residential and supportive housing for people with serious mental illness — group homes, board-and-care, and supported housing.', es:'Guía estado por estado de NAMI sobre vivienda residencial y de apoyo para personas con enfermedades mentales graves.', url:'https://www.nami.org/Support-Education/NAMI-HelpLine', link:'nami.org', phone:'1-800-950-6264' },
    { name:'American Addiction Centers – Halfway House Finder', badge:'b-rehab', en:'Guides people through the differences between halfway houses, sober living homes, and residential treatment — with a directory and admissions navigators available by phone.', es:'Guía a las personas a través de las diferencias entre casas a mitad de camino, hogares de vida sobria y tratamiento residencial.', url:'https://americanaddictioncenters.org/sober-living/halfway-house', link:'americanaddictioncenters.org' },
  ]},
  { en:'College students: housing insecurity resources', es:'Estudiantes universitarios: recursos de inseguridad de vivienda', note_en:'Nearly 1 in 2 college students experiences housing insecurity. These resources are specifically for students.', note_es:'Casi 1 de cada 2 estudiantes universitarios experimenta inseguridad de vivienda. Estos recursos son específicamente para estudiantes.', cards:[
    { name:'Hope Center for Student Basic Needs', badge:'b-student', en:'Temple University research center with a nationwide resource guide for college students experiencing housing insecurity or homelessness. Includes emergency fund info, campus program guidance, and a state-by-state resource list.', es:'Centro de investigación de la Universidad de Temple con una guía de recursos nacional para estudiantes universitarios que experimentan inseguridad de vivienda.', url:'https://hope.temple.edu/resources', link:'hope.temple.edu/resources' },
    { name:'Your Campus Financial Aid Office', badge:'b-student', en:'If you\'re a student experiencing homelessness, contact your college\'s financial aid office first. They can adjust your aid eligibility, connect you to emergency grants, and refer you to campus basic needs programs. Most campuses now have one.', es:'Si es un estudiante sin hogar, comuníquese primero con la oficina de ayuda financiera de su universidad. Pueden ajustar su elegibilidad para ayuda y conectarlo con becas de emergencia.', url:'https://studentaid.gov/help-center/answers/article/special-circumstances-unusual-enrollment-history', link:'studentaid.gov – special circumstances' },
    { name:'NAEHCY – Student Homeless Rights', badge:'b-student', en:'Under the McKinney-Vento Act, homeless students have the right to enroll in college without many standard documentation requirements. NAEHCY explains your legal rights and provides state-by-state contacts.', es:'Bajo la Ley McKinney-Vento, los estudiantes sin hogar tienen derecho a inscribirse en la universidad sin muchos requisitos de documentación estándar.', url:'https://naehcy.org', link:'naehcy.org' },
    { name:'Scholarship America – Emergency Grants', badge:'b-student', en:'Connects housing-insecure students with emergency grant programs — one-time grants up to $1,000 to cover unexpected expenses that threaten enrollment. Available at many colleges through Scholarship America partnerships.', es:'Conecta a estudiantes con inseguridad de vivienda con programas de becas de emergencia — becas únicas de hasta $1,000.', url:'https://scholarshipamerica.org', link:'scholarshipamerica.org' },
    { name:'Off-Campus Room Rentals (SpareRoom / Roomies)', badge:'b-student', en:'For students who need off-campus housing quickly: SpareRoom and Roomies.com both have filters for "students welcome" listings nationwide. Often cheaper than dorms and available month-to-month.', es:'Para estudiantes que necesitan vivienda fuera del campus rápidamente: SpareRoom y Roomies.com tienen filtros para listados de "estudiantes bienvenidos".', url:'https://www.spareroom.com', link:'spareroom.com' },
  ]},
]},

food: { sections:[
  { en:'Food directories & pantries', es:'Directorios de alimentos y despensas', note_en:'Find food banks, pantries, and meal programs near you.', note_es:'Encuentre bancos de alimentos, despensas y programas de comidas cerca de usted.', cards:[
    { name:'Feeding America', badge:'b-food', en:'Locate the nearest food bank or pantry anywhere in the country. Network of 200+ food banks and 60,000+ food pantries nationwide.', es:'Localice el banco de alimentos o despensa más cercano en todo el país. Red de más de 200 bancos de alimentos y 60,000+ despensas.', url:'https://www.feedingamerica.org/find-your-local-foodbank', link:'feedingamerica.org' },
    { name:'USDA Food Finder', badge:'b-food', en:'Find SNAP offices, WIC clinics, school meal sites, and summer food programs near you. Official USDA tool, all 50 states.', es:'Encuentre oficinas de SNAP, clínicas de WIC, sitios de comidas escolares y programas de comidas de verano.', url:'https://www.fns.usda.gov/food-finder', link:'fns.usda.gov/food-finder' },
    { name:'FoodPantries.org', badge:'b-food', en:'Directory of food pantries, soup kitchens, food banks, and food shelves organized by state and city. Community-maintained and updated regularly.', es:'Directorio de despensas de alimentos, comedores, bancos de alimentos y estantes de alimentos organizados por estado y ciudad.', url:'https://www.foodpantries.org', link:'foodpantries.org' },
    { name:'Meals on Wheels', badge:'b-food', en:'Free or low-cost meal delivery for seniors and people with disabilities who cannot leave home. Find your local program through the national locator.', es:'Entrega de comidas gratuita o de bajo costo para personas mayores y personas con discapacidades que no pueden salir de casa.', url:'https://www.mealsonwheelsamerica.org/find-meals', link:'mealsonwheelsamerica.org' },
    { name:'SNAP (Food Stamps) – USA.gov', badge:'b-food', en:'Apply for Supplemental Nutrition Assistance. Pre-screening tool tells you if you likely qualify. Provides monthly benefits to buy groceries.', es:'Solicite Asistencia Nutricional Suplementaria. La herramienta de pre-calificación le indica si probablemente califica.', url:'https://www.usa.gov/food-stamps', link:'usa.gov/food-stamps' },
    { name:'AmpleHarvest.org', badge:'b-food', en:'Helps people find food pantries that accept fresh produce donations. Also a good source for fresher food options beyond canned goods.', es:'Ayuda a las personas a encontrar despensas de alimentos que aceptan donaciones de productos frescos.', url:'https://www.ampleharvest.org', link:'ampleharvest.org' },
  ]},
]},

health: { sections:[
  { en:'Free & low-cost clinics', es:'Clínicas gratuitas y de bajo costo', note_en:'Medical care without insurance or ability to pay.', note_es:'Atención médica sin seguro ni capacidad de pago.', cards:[
    { name:'NAFC – Free Clinic Finder', badge:'b-health', en:'National Association of Free & Charitable Clinics directory. Find free medical, dental, and mental health clinics by state. No insurance required.', es:'Directorio de la Asociación Nacional de Clínicas Gratuitas y Caritativas. Sin seguro requerido.', url:'https://www.nafcclinics.org/find-clinic', link:'nafcclinics.org' },
    { name:'HRSA Health Center Finder', badge:'b-health', en:'Federally Qualified Health Centers offer care on a sliding-fee scale based on income. They cannot turn anyone away. Find the nearest one by address or ZIP.', es:'Los Centros de Salud Calificados Federalmente ofrecen atención en una escala de tarifas según ingresos. No pueden rechazar a nadie.', url:'https://findahealthcenter.hrsa.gov', link:'findahealthcenter.hrsa.gov' },
    { name:'NeedyMeds – Free Clinics', badge:'b-health', en:'Database of free and charitable clinics, patient assistance programs, and free/low-cost medication programs. Includes dental and mental health.', es:'Base de datos de clínicas gratuitas y caritativas, programas de asistencia a pacientes y programas de medicamentos gratuitos o de bajo costo.', url:'https://www.needymeds.org/free-clinics', link:'needymeds.org/free-clinics' },
  ]},
  { en:'Mental health & crisis', es:'Salud mental y crisis', note_en:'Free mental health support, crisis lines, and treatment locators.', note_es:'Apoyo gratuito de salud mental, líneas de crisis y localizadores de tratamiento.', cards:[
    { name:'SAMHSA Helpline & Treatment Locator', badge:'b-health', en:'Free, confidential 24/7 helpline and locator for mental health and substance use services. Multilingual. Nationwide.', es:'Línea directa confidencial gratuita 24/7 y localizador de servicios de salud mental y uso de sustancias. Multilingüe.', url:'https://findtreatment.gov', link:'findtreatment.gov', phone:'1-800-662-4357' },
    { name:'988 Suicide & Crisis Lifeline', badge:'b-health', en:'Free, confidential 24/7 crisis support by call or text. Provides referrals to local mental health services.', es:'Apoyo confidencial gratuito 24/7 por llamada o texto.', url:'https://988lifeline.org', link:'988lifeline.org', phone:'Call or text 988' },
    { name:'NAMI Helpline', badge:'b-mental', en:'National Alliance on Mental Illness helpline — information, referrals, and support for people living with mental illness and their families. Mon–Fri 10am–10pm ET.', es:'Línea de ayuda de la Alianza Nacional sobre Enfermedades Mentales.', url:'https://www.nami.org/help', link:'nami.org/help', phone:'1-800-950-6264' },
    { name:'Crisis Text Line', badge:'b-health', en:'Text-based crisis support, 24/7. No phone call needed.', es:'Apoyo en crisis por texto, 24/7. No se necesita llamada.', url:'https://www.crisistextline.org', link:'crisistextline.org', phone:'Text HOME to 741741' },
  ]},
  { en:'Dental & vision', es:'Dental y visión', note_en:'Free or low-cost dental and vision care.', note_es:'Atención dental y de visión gratuita o de bajo costo.', cards:[
    { name:'Dental Lifeline Network', badge:'b-health', en:'Free dental care for people with disabilities, the elderly, and those who are medically fragile. Find volunteer dentists in your state.', es:'Atención dental gratuita para personas con discapacidades, personas mayores y aquellas que son médicamente frágiles.', url:'https://dentallifeline.org/find-help', link:'dentallifeline.org/find-help' },
    { name:'ADA – Access to Care', badge:'b-health', en:'American Dental Association program listing free dental care events and state-level programs for adults.', es:'Programa de la Asociación Dental Americana que lista eventos de atención dental gratuita.', url:'https://www.ada.org/en/access-to-care', link:'ada.org/access-to-care' },
  ]},
]},

jobs: { sections:[
  { en:'Job centers & placement', es:'Centros de empleo y colocación', note_en:'Free job search help, training, and employment placement.', note_es:'Ayuda gratuita de búsqueda de empleo, capacitación y colocación laboral.', cards:[
    { name:'American Job Centers (CareerOneStop)', badge:'b-jobs', en:'DOL-funded job centers in every state offering free job search help, resume assistance, skills training, and employment referrals. Walk-ins welcome.', es:'Centros de empleo financiados por el DOL en cada estado que ofrecen ayuda gratuita de búsqueda de empleo, asistencia con currículum y capacitación en habilidades.', url:'https://www.careeronestop.org/LocalHelp/AmericanJobCenters/find-american-job-centers.aspx', link:'careeronestop.org' },
    { name:'Goodwill Career Centers', badge:'b-jobs', en:'Free career services, job placement, and skills training at locations nationwide. Walk-ins welcome.', es:'Servicios profesionales gratuitos, colocación laboral y capacitación en habilidades en ubicaciones de todo el país.', url:'https://www.goodwill.org/jobs-training/find-a-goodwill', link:'goodwill.org/jobs-training' },
    { name:'Salvation Army – Workforce Development', badge:'b-jobs', en:'Employment services, job training, and transitional work programs nationwide. Also connects to housing and food assistance simultaneously.', es:'Servicios de empleo, capacitación laboral y programas de trabajo transitorio en todo el país.', url:'https://www.salvationarmyusa.org/usn/workforce-development', link:'salvationarmyusa.org' },
  ]},
  { en:'Benefits & income support', es:'Beneficios y apoyo de ingresos', note_en:'Programs that help while you search for work.', note_es:'Programas que ayudan mientras busca trabajo.', cards:[
    { name:'USA.gov – Unemployment Benefits', badge:'b-jobs', en:'Find your state\'s unemployment insurance program, apply online, and track payment status.', es:'Encuentre el programa de seguro de desempleo de su estado, solicite en línea y rastree el estado de pago.', url:'https://www.usa.gov/unemployment-benefits', link:'usa.gov/unemployment-benefits' },
    { name:'Benefits.gov – Financial Assistance', badge:'b-multi', en:'Find all federal benefit programs you qualify for — emergency cash assistance, food, healthcare, and job training.', es:'Encuentre todos los programas de beneficios federales para los que califica.', url:'https://www.benefits.gov', link:'benefits.gov' },
  ]},
]},

education: { sections:[
  { en:'GED & adult education', es:'GED y educación para adultos', note_en:'Free GED prep, adult literacy, and basic education programs.', note_es:'Preparación gratuita para el GED, alfabetización de adultos y programas de educación básica.', cards:[
    { name:'Federal Adult Education Finder', badge:'b-edu', en:'State-by-state directory of free adult education — GED prep, ESL, basic literacy, and vocational training.', es:'Directorio estado por estado de educación para adultos gratuita — preparación para GED, ESL, alfabetización básica y formación vocacional.', url:'https://lincs.ed.gov/state-resources/federal-initiatives/led', link:'lincs.ed.gov' },
    { name:'Khan Academy', badge:'b-edu', en:'Completely free, self-paced learning for GED prep, math, reading, and job skills. Works on any device including smartphones with limited data.', es:'Aprendizaje completamente gratuito y a su propio ritmo para preparación de GED, matemáticas, lectura y habilidades laborales.', url:'https://www.khanacademy.org', link:'khanacademy.org' },
    { name:'GED Testing Service', badge:'b-edu', en:'Official GED program — find testing centers, free study materials, and information on fee waivers for low-income test takers.', es:'Programa oficial de GED — encuentre centros de prueba, materiales de estudio gratuitos e información sobre exenciones de tarifas.', url:'https://ged.com', link:'ged.com' },
  ]},
  { en:'Vocational & skills training', es:'Formación vocacional y de habilidades', note_en:'Free job skills, trades, and certification programs.', note_es:'Programas gratuitos de habilidades laborales, oficios y certificaciones.', cards:[
    { name:'Goodwill – Job Training Programs', badge:'b-edu', en:'Free vocational training, certificate programs, and job placement at Goodwill locations nationwide. Includes IT, healthcare, and skilled trades.', es:'Capacitación vocacional gratuita, programas de certificado y colocación laboral en ubicaciones de Goodwill en todo el país.', url:'https://www.goodwill.org/jobs-training', link:'goodwill.org/jobs-training' },
    { name:'Job Corps', badge:'b-edu', en:'Free education and vocational training for young adults ages 16–24. Includes housing, meals, healthcare, and job placement. 120+ campuses nationwide.', es:'Educación gratuita y formación vocacional para jóvenes adultos de 16 a 24 años. Incluye alojamiento, comidas, atención médica y colocación laboral.', url:'https://www.jobcorps.gov', link:'jobcorps.gov', phone:'1-800-733-5627' },
    { name:'WIOA Training Finder (CareerOneStop)', badge:'b-edu', en:'Locate free or subsidized vocational training programs funded by the Workforce Innovation and Opportunity Act. Includes trades, healthcare, IT, and more.', es:'Localice programas de capacitación vocacional gratuitos o subsidiados financiados por la Ley de Innovación y Oportunidad de la Fuerza Laboral.', url:'https://www.careeronestop.org/LocalHelp/find-local-help.aspx', link:'careeronestop.org – training finder' },
  ]},
  { en:'Youth education', es:'Educación juvenil', note_en:'Education support for homeless or at-risk youth and college students.', note_es:'Apoyo educativo para jóvenes sin hogar o en riesgo y estudiantes universitarios.', cards:[
    { name:'NAEHCY – Homeless Youth Education Rights', badge:'b-edu', en:'Explains legal rights under the McKinney-Vento Act for homeless students enrolling in school. State-by-state contacts provided.', es:'Explica los derechos legales bajo la Ley McKinney-Vento para estudiantes sin hogar que se inscriben en la escuela.', url:'https://naehcy.org', link:'naehcy.org' },
    { name:'Job Corps (Youth Ages 16–24)', badge:'b-youth', en:'Free residential education and job training program. Includes housing, meals, and healthcare. The most comprehensive free program for young adults without stable housing.', es:'Programa gratuito de educación residencial y capacitación laboral. Incluye alojamiento, comidas y atención médica.', url:'https://www.jobcorps.gov', link:'jobcorps.gov' },
  ]},
]},

immediate: { sections:[
  { en:'Right now', es:'Ahora mismo', note_en:'Hygiene, phone charging, WiFi, clothing, and other urgent non-shelter needs.', note_es:'Higiene, carga de teléfono, WiFi, ropa y otras necesidades urgentes fuera de refugio.', cards:[
    { name:'Public Libraries — Find Yours', badge:'b-immed', en:'Free WiFi, computer access, phone charging, restrooms, cooling/heating, and often social service referrals. No library card required to visit. Search "public library near me."', es:'WiFi gratuito, acceso a computadoras, carga de teléfono, baños, calefacción/refrigeración y a menudo referencias a servicios sociales. No se requiere tarjeta de biblioteca para visitar.', url:'https://www.imls.gov/research-tools/library-statistics', link:'Search: public library near me' },
    { name:'Free Mobile Showers & Laundry — via 211', badge:'b-immed', en:'Free mobile shower and laundry trucks operate in many cities. Call 211 and ask for "hygiene services" or "mobile showers" to find the schedule near you.', es:'Camiones de ducha y lavandería móviles gratuitos operan en muchas ciudades. Llame al 211 y solicite "servicios de higiene" para encontrar el horario cerca de usted.', url:'https://www.211.org', link:'211.org — ask for hygiene services', phone:'Dial 211' },
    { name:'Freecycle & Free Clothing Closets', badge:'b-immed', en:'Search Freecycle.org for free items in your area, or call 211 and ask for "clothing assistance" to find local free clothing closets run by churches and nonprofits.', es:'Busque en Freecycle.org artículos gratuitos en su área, o llame al 211 y solicite "asistencia de ropa" para encontrar armarios de ropa gratuita locales.', url:'https://www.freecycle.org', link:'freecycle.org' },
    { name:'Safe Parking Programs — via 211', badge:'b-immed', en:'If you\'re living in your vehicle, many cities have safe, legal parking programs with access to restrooms and services. Call 211 and ask specifically for "safe parking."', es:'Si vive en su vehículo, muchas ciudades tienen programas de estacionamiento seguros y legales con acceso a baños y servicios.', url:'https://www.211.org', link:'211.org — ask for safe parking', phone:'Dial 211' },
  ]},
  { en:'Utilities & emergency cash', es:'Servicios públicos y efectivo de emergencia', note_en:'Help with electricity, water, phone bills, and emergency funds.', note_es:'Ayuda con electricidad, agua, facturas de teléfono y fondos de emergencia.', cards:[
    { name:'LIHEAP – Energy Assistance', badge:'b-immed', en:'Low Income Home Energy Assistance pays heating and cooling bills for low-income households. Apply through your state. Funds run out seasonally — apply early.', es:'El Programa de Asistencia de Energía para Hogares de Bajos Ingresos paga las facturas de calefacción y refrigeración. Los fondos se agotan estacionalmente — solicite temprano.', url:'https://www.acf.hhs.gov/ocs/programs/liheap', link:'acf.hhs.gov/ocs/liheap' },
    { name:'LifeLine Phone Program', badge:'b-immed', en:'Free or deeply discounted phone and internet service for people on qualifying government assistance programs (Medicaid, SNAP, etc.).', es:'Servicio de teléfono e internet gratuito o con grandes descuentos para personas en programas de asistencia gubernamental calificados.', url:'https://www.lifelinesupport.org', link:'lifelinesupport.org' },
    { name:'Salvation Army – Emergency Financial Aid', badge:'b-immed', en:'Local Salvation Army centers provide emergency cash assistance for rent, utilities, food, and transportation. Availability varies — call your nearest center.', es:'Los centros locales del Ejército de Salvación proporcionan asistencia en efectivo de emergencia para alquiler, servicios, alimentos y transporte.', url:'https://www.salvationarmyusa.org/usn/find-help', link:'salvationarmyusa.org/find-help' },
    { name:'St. Vincent de Paul – Emergency Aid', badge:'b-immed', en:'SVDP councils across the country provide emergency financial assistance, furniture, and clothing. Find your local council for person-to-person help.', es:'Los consejos de SVDP en todo el país proporcionan asistencia financiera de emergencia, muebles y ropa.', url:'https://www.svdpusa.org/find-help', link:'svdpusa.org/find-help' },
  ]},
  { en:'Disaster & extreme weather', es:'Desastre y clima extremo', note_en:'Emergency help during natural disasters and extreme weather events.', note_es:'Ayuda de emergencia durante desastres naturales y eventos de clima extremo.', cards:[
    { name:'American Red Cross', badge:'b-emergency', en:'Emergency shelter, disaster relief, and recovery assistance. Find open Red Cross shelters in real time during declared emergencies.', es:'Refugio de emergencia, socorro en caso de desastre y asistencia de recuperación. Encuentre refugios de la Cruz Roja abiertos en tiempo real durante emergencias declaradas.', url:'https://www.redcross.org/get-help', link:'redcross.org/get-help', phone:'1-800-733-2767' },
    { name:'FEMA DisasterAssistance.gov', badge:'b-emergency', en:'Apply for federal disaster assistance after a declared disaster — includes temporary housing, home repair, and emergency funds.', es:'Solicite asistencia federal por desastre después de un desastre declarado — incluye vivienda temporal, reparación del hogar y fondos de emergencia.', url:'https://www.disasterassistance.gov', link:'disasterassistance.gov', phone:'1-800-621-3362' },
  ]},
]},

about: { special:'about' },

};

let activeTab = 'start';

function buildTabs() {
  const nav = document.getElementById('tab-nav');
  nav.innerHTML = TABS.map(t => `
    <button class="tab-btn${t.id===activeTab?' active':''}" onclick="switchTab('${t.id}')"
      aria-selected="${t.id===activeTab}" role="tab">
      ${t.icon} ${lang==='es'?t.es:t.en}
    </button>`).join('');
}

function cardHTML(c) {
  const desc = lang==='es' ? (c.es||c.en) : c.en;
  return `<div class="card" data-search="${(c.name+' '+(c.en||'')+' '+(c.es||'')).toLowerCase()}">
    <div class="card-top">
      <div class="card-name">${c.name}</div>
      <span class="badge ${c.badge}">${c.badge.replace('b-','')}</span>
    </div>
    <div class="card-desc">${desc}</div>
    <div class="card-foot">
      <a class="card-link" href="${c.url}" target="_blank" rel="noopener">
        <svg width="11" height="11" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24" aria-hidden="true"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
        ${c.link}
      </a>
      ${c.phone?`<span class="phone-chip">📞 ${c.phone}</span>`:''}
    </div>
  </div>`;
}

function buildPanel(tabId) {
  const data = DATA[tabId];
  if (!data) return '';
  if (data.special === 'about') return buildAbout();
  let html = '';
  if (data.hero) {
    html += `<div class="hero-strip"><div class="hero-icon">🧭</div><div>
      <h2>${lang==='es'?'¿No sabe por dónde empezar?':'Not sure where to start?'}</h2>
      <p>${lang==='es'
        ? 'Los recursos a continuación cubren la mayor variedad de necesidades. <strong>Llamar o enviar texto al 211</strong> es siempre el primer paso más rápido — lo conectarán con el programa local correcto de inmediato, 24/7.'
        : 'The resources below cover the widest range of needs. <strong>Calling or texting 211</strong> is always the fastest first step — they\'ll connect you to the right local program immediately, 24/7.'
      }</p></div></div>`;
  }
  data.sections.forEach(s => {
    const label = lang==='es' ? (s.es||s.en) : s.en;
    const note  = lang==='es' ? (s.note_es||s.note_en) : s.note_en;
    html += `<div class="section">
      <div class="section-label">${label}</div>
      <div class="section-note">${note}</div>
      <div class="grid">${s.cards.map(cardHTML).join('')}</div>
    </div>`;
  });
  return html;
}

function buildAbout() {
  const isEs = lang === 'es';
  return `<div class="about-wrap">
    <h2>${isEs?'Acerca de Este Directorio':'About This Directory'}</h2>
    <p>${isEs
      ? 'Esta es una herramienta gratuita de código abierto construida para ayudar a personas que experimentan falta de vivienda o inseguridad de vivienda a encontrar recursos en todo el país. No se recopilan datos, no se requiere cuenta, no hay anuncios.'
      : 'This is a free, open-source tool built to help people experiencing homelessness or housing insecurity find resources nationwide. No data is collected, no account required, no ads.'
    }</p>
    <p>${isEs
      ? 'Todos los recursos son verificados y enlazan directamente a organizaciones legítimas — sin intermediarios, sin seguimiento.'
      : 'All resources are verified and link directly to legitimate organizations — no middlemen, no tracking.'
    }</p>
    <h3>${isEs?'Cómo usar esta herramienta':'How to use this tool'}</h3>
    <ul class="about-list">
      <li>${isEs?'Use el menú de pestañas para navegar por categoría':'Use the tab menu to navigate by category'}</li>
      <li>${isEs?'Escriba en el cuadro de búsqueda para buscar en todas las categorías a la vez':'Type in the search box to search across all categories at once'}</li>
      <li>${isEs?'Haga clic en el enlace verde de cualquier tarjeta para visitar el recurso directamente':'Click the green link on any card to visit the resource directly'}</li>
      <li>${isEs?'Use el botón Imprimir para una copia impresa cuando no hay internet disponible':'Use the Print button for a paper copy when internet isn\'t available'}</li>
      <li>${isEs?'Cambie a Español con el botón 🌐 arriba':'Switch to Spanish with the 🌐 button above'}</li>
    </ul>
    <hr class="about-divider">
    <h3>${isEs?'Compartir y donar esta herramienta':'Share & donate this tool'}</h3>
    <p>${isEs
      ? 'Esta herramienta es completamente gratuita para usar, compartir e integrar. Si desea donarla a una organización, simplemente comparta la URL o el archivo HTML con ellos.'
      : 'This tool is completely free to use, share, and embed. If you\'d like to donate it to an organization, simply share the URL or HTML file with them.'
    }</p>
    <div class="contact-grid">
      <div class="contact-card">
        <strong>${isEs?'Comparte la URL':'Share the URL'}</strong>
        <span>${isEs?'Envía el enlace a refugios, bibliotecas o coordinadores de servicios sociales':'Send the link to shelters, libraries, or social service coordinators'}</span>
      </div>
      <div class="contact-card">
        <strong>${isEs?'Dona a 211.org':'Donate to 211.org'}</strong>
        <a href="https://www.211.org/about/contact" target="_blank" rel="noopener">211.org/about/contact</a>
      </div>
      <div class="contact-card">
        <strong>${isEs?'Dona a NAEH':'Donate to NAEH'}</strong>
        <a href="https://endhomelessness.org/donate" target="_blank" rel="noopener">endhomelessness.org/donate</a>
      </div>
      <div class="contact-card">
        <strong>GitHub</strong>
        <span>${isEs?'Código abierto — disponible libremente para bifurcar y localizar':'Open source — freely available to fork and localize'}</span>
      </div>
    </div>
    <hr class="about-divider">
    <p style="font-size:.8rem;color:var(--text3)">${isEs
      ? 'Recursos verificados mayo 2025. Llame siempre antes — los horarios y la disponibilidad cambian. Para emergencias llame al 911.'
      : 'Resources verified May 2025. Always call ahead — hours and availability change. For emergencies call 911.'
    }</p>
  </div>`;
}

function switchTab(id) {
  activeTab = id;
  buildTabs();
  document.getElementById('global-search').value = '';
  renderActive();
  window.scrollTo({ top:0, behavior:'smooth' });
}

function renderActive() {
  document.getElementById('main-content').innerHTML = buildPanel(activeTab);
}

function filterAll() {
  const q = document.getElementById('global-search').value.toLowerCase().trim();
  if (!q) { renderActive(); return; }
  const seen = new Set();
  const results = [];
  Object.values(DATA).forEach(tabData => {
    if (!tabData.sections) return;
    tabData.sections.forEach(s => {
      s.cards.forEach(c => {
        if (!seen.has(c.url) && (c.name+' '+(c.en||'')+' '+(c.es||'')+' '+c.badge).toLowerCase().includes(q)) {
          seen.add(c.url);
          results.push(c);
        }
      });
    });
  });
  const main = document.getElementById('main-content');
  if (!results.length) {
    main.innerHTML = `<div class="no-results">No resources found for "<strong>${q}</strong>" — try a different term, or call 211 for direct help.</div>`;
    return;
  }
  main.innerHTML = `<div class="section">
    <div class="section-label">${lang==='es'?`Resultados para "${q}"`:`Search results for "${q}"`}</div>
    <div class="section-note">${results.length} ${lang==='es'?'recursos encontrados en todas las categorías':'resources found across all categories'}</div>
    <div class="grid">${results.map(cardHTML).join('')}</div>
  </div>`;
}

function toggleLang() {
  lang = lang==='en' ? 'es' : 'en';
  document.getElementById('lang-label').textContent = lang==='en' ? 'Español' : 'English';
  document.getElementById('lang-btn').classList.toggle('lang-active', lang==='es');
  document.getElementById('global-search').placeholder = lang==='es' ? 'Buscar todos los recursos…' : 'Search all resources…';
  // Update static translated elements
  document.querySelectorAll('[data-en]').forEach(el => {
    el.textContent = lang==='es' ? el.dataset.es : el.dataset.en;
  });
  buildTabs();
  const q = document.getElementById('global-search').value.trim();
  if (q) filterAll(); else renderActive();
}

buildTabs();
renderActive();
</script>
</body>
</html>
