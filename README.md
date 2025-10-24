<!doctype html>
<html lang="pt-br">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Demétrius Ian da Costa Santos — Portfólio</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --blue-900: #0d2540;
      --blue-700: #004b8d;
      --blue-500: #2b6ea3;
      --muted: #f4f7fb;
      --card-bg: #ffffff;
      --text: #1f2a44;
      --muted-text: #526070;
      --radius: 12px;
      --container: 1100px;
    }

    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%}
    body{
      font-family: 'Poppins', sans-serif;
      background: #ffffff;
      color:var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      scroll-behavior:smooth;
    }

    /* ===== NAV ===== */
    .topbar{
      position:fixed;
      top:0;left:0;right:0;
      height:64px;
      display:flex;
      align-items:center;
      justify-content:center; /* menu centered horizontally */
      background: #fff;
      box-shadow: 0 2px 10px rgba(8,18,40,0.06);
      z-index:999;
    }
    .nav {
      width:100%;
      max-width:var(--container);
      display:flex;
      justify-content:center; /* center links across full row */
      gap:32px;
      padding:0 20px;
    }
    .nav a{
      color:var(--blue-900);
      text-decoration:none;
      font-weight:600;
      font-size:0.95rem;
      padding:8px 6px;
      transition: color .18s, transform .18s;
    }
    .nav a:hover{ color:var(--blue-700); transform: translateY(-2px); }

    /* push down content under fixed nav */
    .spacer{height:64px;}

    /* ===== HERO ===== */
    .hero{
      max-width:var(--container);
      margin: 32px auto 40px;
      padding:32px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:30px;
    }

    /* left column: text */
    .hero-left{
      flex:1 1 420px;
      min-width:260px;
      padding:24px;
    }
    .name{
      font-size:1.9rem;
      font-weight:700;
      color:var(--blue-900);
      margin-bottom:8px;
    }
    .subtitle{
      color:var(--muted-text);
      font-weight:500;
      margin-bottom:18px;
    }
    .hero-cta{
      margin-top:14px;
      display:flex;
      gap:12px;
      flex-wrap:wrap;
    }
    .btn{
      border-radius:8px;
      padding:10px 18px;
      font-weight:600;
      cursor:pointer;
      border:0;
      transition:transform .15s, box-shadow .15s;
    }
    .btn-primary{
      background:var(--blue-700);
      color:#fff;
      box-shadow: 0 6px 18px rgba(3,64,130,0.12);
    }
    .btn-primary:hover{ transform:translateY(-3px); }
    .btn-outline{
      background:transparent;
      color:var(--blue-700);
      border:2px solid var(--blue-700);
    }
    .btn-outline:hover{
      background:var(--blue-700);
      color:#fff;
      transform:translateY(-3px);
    }

    /* right column: circular photo centered vertically in hero */
    .hero-right{
      flex:0 0 300px;
      display:flex;
      align-items:center;
      justify-content:center;
    }
    .profile-wrap{
      width:240px;
      height:240px;
      border-radius:50%;
      display:flex;
      align-items:center;
      justify-content:center;
      background: linear-gradient(180deg, rgba(11,37,70,0.03), rgba(43,110,163,0.04));
      border:6px solid rgba(4,75,141,0.15);
      box-shadow: 0 8px 30px rgba(20,45,80,0.06);
      overflow:hidden;
    }
    .profile-wrap img{
      width:100%;
      height:100%;
      object-fit:cover;
      display:block;
    }

    /* ===== SECTIONS ===== */
    .section{
      max-width:var(--container);
      margin: 34px auto;
      padding: 28px;
    }
    .card{
      background:var(--card-bg);
      border-radius:var(--radius);
      box-shadow: 0 6px 20px rgba(18,32,82,0.04);
      padding:20px;
    }

    .section-title{
      display:flex;
      align-items:center;
      gap:12px;
      margin-bottom:18px;
    }
    .section-title .bar{
      width:6px;height:34px;background:var(--blue-700);border-radius:2px;
    }
    .section-title h2{
      font-size:1.25rem;
      color:var(--blue-900);
      font-weight:700;
    }

    /* Skills grid */
    .grid{
      display:grid;
      gap:16px;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      margin-top:10px;
    }
    .skill{
      display:flex;
      gap:12px;
      align-items:flex-start;
    }
    .skill .dot{
      width:48px;height:48px;border-radius:10px;background:linear-gradient(180deg,var(--muted),#eef6fb);
      display:flex;align-items:center;justify-content:center;color:var(--blue-700);font-weight:700;
      box-shadow: inset 0 -6px 12px rgba(2,48,86,0.02);
    }
    .skill p{ font-size:0.95rem;color:var(--muted-text); }

    /* Projects cards */
    .projects-grid{
      display:grid;
      gap:18px;
      grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
      margin-top:10px;
    }
    .project{
      padding:16px;border-radius:10px;background:linear-gradient(180deg, #ffffff, #fbfdff);
      border:1px solid rgba(34,64,110,0.03);
    }
    .project h3{ color:var(--blue-900); margin-bottom:8px; font-size:1.05rem; }
    .project p{ color:var(--muted-text); font-size:0.95rem; }

    /* Experience list */
    .exp-list{ margin-top:8px; display:grid; gap:12px; }
    .exp-item{ padding:14px; border-radius:10px; background: #fff; border-left:4px solid rgba(0,75,141,0.06); }
    .exp-item h4{ font-size:1rem; color:var(--blue-900); margin-bottom:6px; }
    .exp-item p{ color:var(--muted-text); font-size:0.95rem; }

    /* Contact */
    .contact-row{ display:flex; gap:16px; flex-wrap:wrap; margin-top:12px; }
    .contact-box{ padding:14px 16px; border-radius:10px; background:#fff; min-width:220px; box-shadow: 0 6px 18px rgba(13,38,70,0.03); }
    .contact-box strong{ display:block; margin-bottom:6px; color:var(--blue-900); }

    /* small screens */
    @media (max-width:900px){
      .hero{ padding:18px; margin-top:18px; gap:18px; }
      .hero-left{ padding:12px; text-align:center }
      .hero-right{ order:2; width:100%; margin-top:6px; display:flex; justify-content:center }
      .hero-left .name{ font-size:1.6rem }
      .nav{ gap:18px }
      .topbar{ height:56px }
      .spacer{ height:56px }
    }
    @media (max-width:520px){
      .profile-wrap{ width:200px; height:200px; border-width:5px }
      .hero-left .name{ font-size:1.4rem }
      .nav a{ font-size:0.9rem }
      .grid{ grid-template-columns: 1fr }
      .projects-grid{ grid-template-columns: 1fr }
    }

  </style>
</head>
<body>

  <!-- NAV -->
  <div class="topbar" role="navigation" aria-label="Menu principal">
    <nav class="nav">
      <a href="#sobre">Sobre</a>
      <a href="#habilidades">Habilidades</a>
      <a href="#projetos">Projetos</a>
      <a href="#experiencia">Experiência</a>
      <a href="#contato">Contato</a>
    </nav>
  </div>

  <!-- push content under fixed nav -->
  <div class="spacer" aria-hidden="true"></div>

  <!-- HERO -->
  <main>
    <section class="hero" aria-label="Apresentação principal">
      <div class="hero-left" role="region" aria-labelledby="hero-name">
        <div id="hero-name" class="name">Demétrius Ian da Costa Santos</div>
        <div class="subtitle">Técnico em Edificações | Acadêmico de Engenharia Civil</div>

        <div class="hero-cta">
          <a class="btn btn-primary" href="#projetos" title="Ver Projetos">Ver Projetos</a>
          <a class="btn btn-outline" href="#contato" title="Entrar em contato">Contato</a>
        </div>
      </div>

      <div class="hero-right" aria-hidden="false">
        <div class="profile-wrap" aria-hidden="false">
          <!-- Coloque aqui o arquivo da sua foto com o nome 'foto.jpg' na mesma pasta do index.html -->
          <img src="foto.jpg" alt="Foto de Demétrius Ian da Costa Santos — perfil">
        </div>
      </div>
    </section>

    <!-- SOBRE -->
    <section id="sobre" class="section" aria-labelledby="sobre-title">
      <div class="section-title">
        <div class="bar" aria-hidden="true"></div>
        <h2 id="sobre-title">Sobre mim</h2>
      </div>

      <div class="card">
        <p>
          Sou Técnico em Edificações e atualmente curso Engenharia Civil. Tenho experiência em acompanhamento de obras, fiscalização, elaboração de desenhos técnicos no AutoCAD e controle de quantitativos.
          Busco soluções que integrem sustentabilidade, segurança e eficiência construtiva, sempre com foco em qualidade e cumprimento de prazos.
        </p>
      </div>
    </section>

    <!-- HABILIDADES -->
    <section id="habilidades" class="section" aria-labelledby="habilidades-title">
      <div class="section-title">
        <div class="bar" aria-hidden="true"></div>
        <h2 id="habilidades-title">Habilidades</h2>
      </div>

      <div class="grid">
        <div class="card skill">
          <div class="dot">CAD</div>
          <div>
            <strong>AutoCAD / Desenho Técnico</strong>
            <p>Elaboração de plantas, cortes, fachadas e detalhamentos construtivos.</p>
          </div>
        </div>

        <div class="card skill">
          <div class="dot">3D</div>
          <div>
            <strong>SketchUp / Modelagem</strong>
            <p>Modelagem para apresentações, volumetria e detalhamento rápido.</p>
          </div>
        </div>

        <div class="card skill">
          <div class="dot">EX</div>
          <div>
            <strong>Excel Técnico</strong>
            <p>Controle de quantitativos, orçamentos e cronogramas simples.</p>
          </div>
        </div>

        <div class="card skill">
          <div class="dot">LE</div>
          <div>
            <strong>Leitura de Projetos</strong>
            <p>Interpretação técnica de projetos arquitetônicos e estruturais.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- PROJETOS -->
    <section id="projetos" class="section" aria-labelledby="projetos-title">
      <div class="section-title">
        <div class="bar" aria-hidden="true"></div>
        <h2 id="projetos-title">Projetos em destaque</h2>
      </div>

      <div class="projects-grid">
        <article class="project">
          <h3>Residência Sustentável — Natal/RN</h3>
          <p>Projeto arquitetônico com estratégias passivas de conforto térmico, aproveitamento de iluminação natural e sistema de reuso de águas pluviais.</p>
        </article>

        <article class="project">
          <h3>Fiscalização de obras — Certa Construções</h3>
          <p>Atuação na fiscalização e controle de qualidade, elaboração de relatórios técnicos e apoio na coordenação de etapas construtivas.</p>
        </article>

        <article class="project">
          <h3>Sistema de aproveitamento de água pluvial (acadêmico)</h3>
          <p>Estudo e dimensionamento de reservatórios e conduções para redução do consumo de água potável em edificações residenciais.</p>
        </article>
      </div>
    </section>

    <!-- EXPERIÊNCIA -->
    <section id="experiencia" class="section" aria-labelledby="experiencia-title">
      <div class="section-title">
        <div class="bar" aria-hidden="true"></div>
        <h2 id="experiencia-title">Experiência profissional</h2>
      </div>

      <div class="exp-list">
        <div class="exp-item">
          <h4>Certa Construções — Estagiário (2022)</h4>
          <p>Suporte técnico em obras: acompanhamento, emissão de relatórios, verificação de conformidade e apoio em desenhos AutoCAD.</p>
        </div>

        <div class="exp-item">
          <h4>Dean — Colaboração em projetos</h4>
          <p>Participação no desenvolvimento de projetos técnicos com foco em detalhamento construtivo e compatibilização de disciplinas.</p>
        </div>
      </div>
    </section>

    <!-- CONTATO -->
    <section id="contato" class="section" aria-labelledby="contato-title">
      <div class="section-title">
        <div class="bar" aria-hidden="true"></div>
        <h2 id="contato-title">Contato</h2>
      </div>

      <div class="card">
        <p>Gostaria de conversar sobre um projeto, vaga ou parceria? Entre em contato.</p>

        <div class="contact-row" role="group" aria-label="Informações de contato">
          <div class="contact-box">
            <strong>Email</strong>
            <span>demetriusian@email.com</span>
          </div>

          <div class="contact-box">
            <strong>Telefone</strong>
            <span>(84) 9xxxx-xxxx</span>
          </div>

          <div class="contact-box">
            <strong>Redes</strong>
            <span><a href="#" style="color:var(--blue-700);text-decoration:none">LinkedIn</a> · <a href="#" style="color:var(--blue-700);text-decoration:none">Instagram</a></span>
          </div>
        </div>

      </div>
    </section>

  </main>

  <!-- no footer as requested -->

</body>
</html>
