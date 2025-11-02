<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bruno Wegelius</title>
  <meta name="theme-color" content="#ffffff" />

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;500;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg: #ffffff;
      --fg: #0f0f10;
      --muted: #6b7280;
      --border: #e5e7eb;
      --maxw: 860px;
      --small: 13px;
      --base: 15px;
      --lh: 1.55;
    }
    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body {
      margin: 0;
      background: var(--bg);
      color: var(--fg);
      font-family: "Roboto Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
      font-size: var(--base);
      line-height: var(--lh);
      -webkit-font-smoothing: antialiased;
      text-rendering: optimizeLegibility;
    }
    a { color: #111; text-decoration: none; }
    a:hover { text-decoration: underline; }

    .wrap { display: grid; grid-template-columns: 220px 1fr; min-height: 100%; }

    nav {
      border-right: 1px solid var(--border);
      padding: 28px 18px 28px 22px;
      position: sticky;
      top: 0;
      align-self: start;
      height: 100dvh;
      display: flex;
      flex-direction: column;
      gap: 28px;
    }
    .brand { font-weight: 600; letter-spacing: 0.5px; }
    .tabs { display: flex; flex-direction: column; gap: 10px; }
    .tab { font-size: var(--small); text-transform: lowercase; letter-spacing: 0.4px; opacity: 0.7; transition: opacity 120ms ease; }
    .tab[aria-current="page"] { opacity: 1; }

    main { padding: 40px 28px; }
    .container { max-width: var(--maxw); }

    h1 { font-weight: 500; margin: 0 0 12px 0; font-size: 22px; }
    .section { display: none; animation: fade 160ms ease; }
    .section.active { display: block; }

    @media (max-width: 880px) {
      .wrap { grid-template-columns: 1fr; }
      nav { position: static; height: auto; border-right: none; border-bottom: 1px solid var(--border); padding: 18px 16px; }
      main { padding: 24px 16px; }
    }

    @keyframes fade { from { opacity: 0 } to { opacity: 1 } }
  </style>
</head>
<body>
  <div class="wrap">
    <nav aria-label="Primary">
      <div class="brand">Bruno Wegelius</div>
      <div class="tabs" role="tablist">
        <a class="tab" id="tab-portfolio" href="#portfolio" role="tab" aria-controls="portfolio" aria-selected="true">portfolio</a>
        <a class="tab" id="tab-about" href="#about" role="tab" aria-controls="about" aria-selected="false">about</a>
        <a class="tab" id="tab-links" href="#links" role="tab" aria-controls="links" aria-selected="false">links</a>
      </div>
    </nav>

    <main>
      <div class="container">
        <section id="portfolio" class="section active" role="tabpanel" aria-labelledby="tab-portfolio">
          <h1>Selected work</h1>
        </section>

        <section id="about" class="section" role="tabpanel" aria-labelledby="tab-about">
          <h1>About</h1>
        </section>

        <section id="links" class="section" role="tabpanel" aria-labelledby="tab-links">
          <h1>Links</h1>
        </section>
      </div>
    </main>
  </div>

  <script>
    (function() {
      const sections = document.querySelectorAll('.section');
      const tabs = document.querySelectorAll('.tab');

      function activate(hash) {
        const id = (hash || '#portfolio').replace('#', '');
        sections.forEach(s => s.classList.toggle('active', s.id === id));
        tabs.forEach(t => {
          const isActive = t.getAttribute('href') === '#' + id;
          t.setAttribute('aria-current', isActive ? 'page' : 'false');
          t.setAttribute('aria-selected', isActive ? 'true' : 'false');
        });
        document.title = `Bruno Wegelius — ${id}`;
      }

      window.addEventListener('hashchange', () => activate(location.hash));
      activate(location.hash);
    })();
  </script>
</body>
</html>
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bruno Wegelius</title>
  <meta name="theme-color" content="#ffffff" />

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;500;700&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg: #ffffff;
      --fg: #0f0f10;
      --muted: #6b7280;
      --border: #e5e7eb;
      --maxw: 860px;
      --small: 13px;
      --base: 15px;
      --lh: 1.55;
    }
    * { box-sizing: border-box; }
    html, body { height: 100%; }
    body {
      margin: 0;
      background: var(--bg);
      color: var(--fg);
      font-family: "Roboto Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
      font-size: var(--base);
      line-height: var(--lh);
      -webkit-font-smoothing: antialiased;
      text-rendering: optimizeLegibility;
    }
    a { color: #111; text-decoration: none; }
    a:hover { text-decoration: underline; }

    .wrap { display: grid; grid-template-columns: 220px 1fr; min-height: 100%; }

    nav {
      border-right: 1px solid var(--border);
      padding: 28px 18px 28px 22px;
      position: sticky;
      top: 0;
      align-self: start;
      height: 100dvh;
      display: flex;
      flex-direction: column;
      gap: 28px;
    }
    .brand { font-weight: 600; letter-spacing: 0.5px; }
    .tabs { display: flex; flex-direction: column; gap: 10px; }
    .tab { font-size: var(--small); text-transform: lowercase; letter-spacing: 0.4px; opacity: 0.7; transition: opacity 120ms ease; }
    .tab[aria-current="page"] { opacity: 1; }

    main { padding: 40px 28px; }
    .container { max-width: var(--maxw); }

    h1 { font-weight: 500; margin: 0 0 12px 0; font-size: 22px; }
    .section { display: none; animation: fade 160ms ease; }
    .section.active { display: block; }

    @media (max-width: 880px) {
      .wrap { grid-template-columns: 1fr; }
      nav { position: static; height: auto; border-right: none; border-bottom: 1px solid var(--border); padding: 18px 16px; }
      main { padding: 24px 16px; }
    }

    @keyframes fade { from { opacity: 0 } to { opacity: 1 } }
  </style>
</head>
<body>
  <div class="wrap">
    <nav aria-label="Primary">
      <div class="brand">Bruno Wegelius</div>
      <div class="tabs" role="tablist">
        <a class="tab" id="tab-portfolio" href="#portfolio" role="tab" aria-controls="portfolio" aria-selected="true">portfolio</a>
        <a class="tab" id="tab-about" href="#about" role="tab" aria-controls="about" aria-selected="false">about</a>
        <a class="tab" id="tab-links" href="#links" role="tab" aria-controls="links" aria-selected="false">links</a>
      </div>
    </nav>

    <main>
      <div class="container">
        <section id="portfolio" class="section active" role="tabpanel" aria-labelledby="tab-portfolio">
          <h1>Selected work</h1>
        </section>

        <section id="about" class="section" role="tabpanel" aria-labelledby="tab-about">
          <h1>About</h1>
        </section>

        <section id="links" class="section" role="tabpanel" aria-labelledby="tab-links">
          <h1>Links</h1>
        </section>
      </div>
    </main>
  </div>

  <script>
    (function() {
      const sections = document.querySelectorAll('.section');
      const tabs = document.querySelectorAll('.tab');

      function activate(hash) {
        const id = (hash || '#portfolio').replace('#', '');
        sections.forEach(s => s.classList.toggle('active', s.id === id));
        tabs.forEach(t => {
          const isActive = t.getAttribute('href') === '#' + id;
          t.setAttribute('aria-current', isActive ? 'page' : 'false');
          t.setAttribute('aria-selected', isActive ? 'true' : 'false');
        });
        document.title = `Bruno Wegelius — ${id}`;
      }

      window.addEventListener('hashchange', () => activate(location.hash));
      activate(location.hash);
    })();
  </script>
</body>
</html>
