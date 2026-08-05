<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Algumas lembranças nunca foram embora</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600&family=Inter:wght@300;400&display=swap" rel="stylesheet" />
  <style>
    :root{--bg:#FAF8F5;--text:#2b2b2b;--muted:#666;--radius:18px;--card-shadow:0 20px 45px rgba(0,0,0,.12);--btn-shadow:0 10px 30px rgba(0,0,0,.08);}
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%}
    body{background:var(--bg);display:flex;align-items:center;justify-content:center;min-height:100vh;font-family:Inter,system-ui,Segoe UI,Roboto,Arial;padding:1.25rem}
    .wrap{width:100%;max-width:720px;text-align:center;position:relative}
    #intro{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;background:var(--bg);transition:opacity 1.8s ease;z-index:10;padding:2rem}
    #intro.hidden{opacity:0;pointer-events:none}
    #intro h1{font-family:"Cormorant Garamond",serif;font-size:2.125rem;font-weight:400;color:var(--text);line-height:1.25;text-align:center}
    #conteudo{opacity:0;transition:opacity 1.8s ease;padding:1.5rem}
    #conteudo.visible{opacity:1}
    .card-image{width:100%;max-width:430px;margin:0 auto;border-radius:var(--radius);box-shadow:var(--card-shadow);overflow:hidden;height:min(72vh,650px);background:#ddd}
    .card-image img{width:100%;height:100%;object-fit:cover;object-position:center;display:block}
    .frase{margin-top:1.25rem;font-family:"Cormorant Garamond",serif;font-size:1.375rem;color:var(--text)}
    .controls{margin-top:1.75rem;display:flex;align-items:center;justify-content:center;gap:1rem;flex-wrap:wrap}
    button.play-btn{padding:.9rem 1.75rem;border-radius:999px;border:none;background:#fff;font-size:1rem;cursor:pointer;box-shadow:var(--btn-shadow);transition:transform .18s}
    button.play-btn:hover{transform:scale(1.03)}
    button.play-btn:focus{outline:2px solid #333;outline-offset:2px}
    .final{margin-top:1.25rem;font-size:.95rem;color:var(--muted);font-style:italic;opacity:.95;line-height:1.6}
    .coracao{margin-top:1rem;font-size:1.25rem;opacity:.6}
    @media (max-width:480px){#intro h1{font-size:1.625rem}.frase{font-size:1.125rem}.card-image{height:56vh}}
    @media (prefers-reduced-motion: reduce){#intro,#conteudo{transition:none!important}}
  </style>
</head>
<body>
  <div class="wrap">
    <div id="intro" role="dialog" aria-label="Introdução">
      <h1>Algumas lembranças<br>nunca foram embora.</h1>
    </div>

    <main id="conteudo" aria-live="polite">
      <div class="card-image" aria-hidden="false">
        <img src="foto.jpg" alt="Duas pessoas abraçadas, sorrindo, em uma lembrança pessoal" />
      </div>

      <div class="frase">Algumas lembranças nunca foram embora.</div>

      <div class="controls">
        <!-- Botão principal: abre o YouTube em nova aba -->
        <button id="playBtn" class="play-btn" type="button" aria-label="Abrir música no YouTube">▶︎ Tocar nossa lembrança</button>

        <!-- Link direto caso o usuário prefira abrir no YouTube manualmente -->
        <a id="openDirect" href="https://www.youtube.com/watch?v=n0NbNrYaNpg" target="_blank" rel="noopener noreferrer" style="align-self:center;color:var(--muted);text-decoration:none;font-size:.95rem;">Abrir diretamente no YouTube</a>
      </div>

      <div class="final">Às vezes a vida só precisava nos fazer crescer para nos apresentar novamente.</div>
      <div class="coracao" aria-hidden="true">♡</div>
    </main>
  </div>

  <script>
    (function(){
      const intro = document.getElementById('intro');
      const conteudo = document.getElementById('conteudo');
      const playBtn = document.getElementById('playBtn');

      const YT_URL = 'https://www.youtube.com/watch?v=n0NbNrYaNpg';

      function reveal(){ intro.classList.add('hidden'); setTimeout(()=>{ intro.style.display='none'; conteudo.classList.add('visible'); }, 800); }
      window.addEventListener('load', ()=> setTimeout(reveal, 2500));
      const reduced = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
      if(reduced){ intro.style.display='none'; conteudo.classList.add('visible'); }

      // Abre o YouTube em nova aba ao clicar — essa interação vem do usuário (evita bloqueio de autoplay)
      playBtn.addEventListener('click', () => {
        window.open(YT_URL, '_blank', 'noopener,noreferrer');
      });

      // Se quiser: ao pressionar ALT+clicar, abrir com start_radio etc. (opcional)
    })();
  </script>
</body>
</html>
<img
    src="./foto.jpeg"
    alt="Nossa lembrança"
    loading="eager">
