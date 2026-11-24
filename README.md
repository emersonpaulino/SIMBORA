<!DOCTYPE html>

<html lang="pt-BR">

<head>

  <meta charset="utf-8" />

  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <meta name="theme-color" content="#faf8f5" />

  <title>Algumas lembranças nunca foram embora</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">

  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600&family=Inter:wght@300;400&display=swap" rel="stylesheet">

  <style>

    :root {

      --bg: #faf8f5;

      --text: #2b2928;

      --muted: #77716c;

      --shadow: 0 20px 45px rgba(0,0,0,.12);

    }

    * { box-sizing: border-box; }

    html, body { min-height: 100%; }

    body {

      margin: 0;

      padding: 24px;

      min-height: 100vh;

      display: flex;

      align-items: center;

      justify-content: center;

      background: var(--bg);

      color: var(--text);

      font-family: Inter, system-ui, sans-serif;

    }

    .wrap {

      width: 100%;

      max-width: 680px;

      text-align: center;

      position: relative;

    }

    .intro {

      position: fixed;

      inset: 0;

      z-index: 5;

      display: flex;

      align-items: center;

      justify-content: center;

      padding: 32px;

      background: var(--bg);

      opacity: 1;

      transition: opacity 1.5s ease;

    }

    .intro h1 {

      max-width: 620px;

      margin: 0;

      font: 400 clamp(2rem, 6vw, 3.1rem)/1.22 "Cormorant Garamond", serif;

    }

    .intro.hidden {

      opacity: 0;

      pointer-events: none;

    }

    main {

      opacity: 0;

      transition: opacity 1.5s ease;

      padding: 10px 0;

    }

    main.visible { opacity: 1; }

    .photo {

      width: 100%;

      max-width: 430px;

      margin: 0 auto;

      border-radius: 18px;

      overflow: hidden;

      box-shadow: var(--shadow);

      background: #e8e4df;

    }

    .photo img {

      display: block;

      width: 100%;

      height: auto;

    }

    .caption {

      margin: 22px 8px 0;

      font: 400 clamp(1.45rem, 4.5vw, 1.9rem)/1.3 "Cormorant Garamond", serif;

    }

    .controls {

      margin: 26px 0 0;

      display: flex;

      justify-content: center;

    }

    .play {

      display: inline-block;

      padding: 14px 25px;

      border-radius: 999px;

      background: #fff;

      color: var(--text);

      text-decoration: none;

      font: 400 1rem Inter, sans-serif;

      box-shadow: 0 10px 30px rgba(0,0,0,.08);

      transition: transform .2s ease;

    }

    .play:hover { transform: translateY(-2px); }

    .heart {

      margin-top: 20px;

      color: #9b8f87;

      font-size: 1.25rem;

    }

    @media (max-width: 480px) {

      body { padding: 18px; }

      .photo { max-width: 100%; }

      .caption { margin-top: 18px; }

    }

    @media (prefers-reduced-motion: reduce) {

      *, *::before, *::after {

        transition-duration: .01ms !important;

      }

    }

  </style>

</head>

<body>

  <div class="intro" id="intro" role="dialog" aria-label="Mensagem de entrada">

    <h1>Vamos ficar somente entrando aqui e imaginando ou iremos criar coragem e realizar tudo o que um dia sonhamos?</h1>

  </div>

  <div class="wrap">

    <main id="content" aria-live="polite">

      <div class="photo">

        <img

          src="foto.jpg.jpeg"

          alt="Colagem de lembranças e fotografias de um casal"

        />

      </div>

      <p class="caption">até os mínimos detalhes trazem lembranças suas.🤍</p>

      <div class="controls">

        <a

          class="play"

          href="https://m.youtube.com/watch?v=2iUAbkwfxcY&list=RD2iUAbkwfxcY&start_radio=1&pp=ygUPY2FzbyBpbmRlZmluaWRvoAcB"

          target="_blank"

          rel="noopener noreferrer"

        >▶︎ Tocar nossa lembrança</a>

      </div>

      <div class="heart" aria-hidden="true">♡</div>

    </main>

  </div>

  <script>

    (() => {

      const intro = document.getElementById('intro');

      const content = document.getElementById('content');

      const reduceMotion = window.matchMedia(

        '(prefers-reduced-motion: reduce)'

      ).matches;

      function reveal() {

        intro.classList.add('hidden');

        content.classList.add('visible');

        window.setTimeout(() => {

          intro.style.display = 'none';

        }, reduceMotion ? 0 : 1500);

      }

      if (reduceMotion) {

        intro.style.display = 'none';

        content.classList.add('visible');

      } else {

        window.setTimeout(reveal, 2500);

      }

    })();

  </script>

</body>

</html>
