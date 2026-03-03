# rita-ruahnma-site
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Um Caminho de Volta</title>
  <style>
    :root{
      --bg1:#0b0b12;
      --bg2:#141425;
      --card:#101020cc;
      --ink:#f3f1ff;
      --muted:#b9b6d3;
      --accent:#ff4d7d;
      --accent2:#7cf0ff;
      --ok:#6df0a8;
      --warn:#ffd36d;
      --shadow: 0 18px 60px rgba(0,0,0,.55);
      --radius: 22px;
      --border: 1px solid rgba(255,255,255,.10);
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
      color:var(--ink);
      min-height:100vh;
      background:
        radial-gradient(1200px 800px at 15% 20%, rgba(255,77,125,.25), transparent 55%),
        radial-gradient(1000px 700px at 85% 25%, rgba(124,240,255,.18), transparent 60%),
        radial-gradient(900px 700px at 50% 95%, rgba(109,240,168,.12), transparent 65%),
        linear-gradient(180deg, var(--bg1), var(--bg2));
      overflow-x:hidden;
    }

    .wrap{
      max-width: 980px;
      margin: 0 auto;
      padding: 22px 16px 70px;
    }

    header{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      padding: 6px 4px 18px;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:10px;
      opacity:.95;
    }
    .seal{
      width:38px;height:38px;
      border-radius: 14px;
      background:
        radial-gradient(circle at 30% 30%, rgba(255,255,255,.35), transparent 55%),
        linear-gradient(135deg, rgba(255,77,125,.95), rgba(124,240,255,.75));
      box-shadow: 0 10px 30px rgba(255,77,125,.18);
      border: var(--border);
      position:relative;
    }
    .seal:after{
      content:"";
      position:absolute; inset:10px;
      border-radius: 12px;
      border: 1px dashed rgba(255,255,255,.45);
      opacity:.7;
    }
    .brand h1{
      font-size: 15px;
      letter-spacing: .16em;
      text-transform: uppercase;
      margin:0;
      color: rgba(243,241,255,.9);
    }
    .brand p{
      margin:0;
      color: var(--muted);
      font-size: 12px;
      letter-spacing:.04em;
    }

    .progress{
      display:flex; align-items:center; gap:10px;
      color: var(--muted);
      font-size: 12px;
    }
    .dots{
      display:flex; gap:6px;
    }
    .dot{
      width:8px;height:8px;border-radius:99px;
      background: rgba(255,255,255,.18);
      border: 1px solid rgba(255,255,255,.14);
    }
    .dot.on{ background: rgba(255,77,125,.8); border-color: rgba(255,77,125,.7); box-shadow: 0 0 0 6px rgba(255,77,125,.12); }

    .card{
      background: var(--card);
      border: var(--border);
      box-shadow: var(--shadow);
      border-radius: var(--radius);
      padding: 18px;
      backdrop-filter: blur(10px);
    }

    .hero{
      display:grid;
      grid-template-columns: 1.15fr .85fr;
      gap:16px;
      align-items:stretch;
    }
    @media (max-width: 860px){
      .hero{grid-template-columns: 1fr; }
    }

    .title{
      font-size: 28px;
      line-height: 1.15;
      margin: 4px 0 10px;
      letter-spacing: -0.02em;
    }
    .subtitle{
      color: var(--muted);
      margin:0 0 14px;
      line-height:1.55;
      font-size: 14px;
    }

    .poem{
      padding: 14px;
      border-radius: 18px;
      border: 1px solid rgba(255,255,255,.10);
      background: linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
      color: rgba(243,241,255,.92);
      line-height:1.65;
      font-size: 14px;
      position:relative;
      overflow:hidden;
    }
    .poem:before{
      content:"";
      position:absolute; inset:-2px;
      background:
        radial-gradient(400px 180px at 20% 10%, rgba(255,77,125,.18), transparent 60%),
        radial-gradient(400px 180px at 90% 90%, rgba(124,240,255,.14), transparent 60%);
      opacity:.8;
      pointer-events:none;
    }
    .poem blockquote{
      margin:0;
      position:relative;
    }
    .poem small{
      display:block;
      margin-top:10px;
      color: rgba(185,182,211,.9);
      letter-spacing:.04em;
    }

    .panel{
      display:flex;
      flex-direction:column;
      gap:12px;
      height:100%;
    }

    .btnrow{
      display:flex;
      flex-wrap:wrap;
      gap:10px;
      margin-top: 14px;
    }
    button{
      appearance:none;
      border: none;
      cursor:pointer;
      border-radius: 16px;
      padding: 12px 14px;
      font-weight: 650;
      letter-spacing:.02em;
      color: rgba(11,11,18,.95);
      background: linear-gradient(135deg, rgba(255,77,125,.95), rgba(124,240,255,.85));
      box-shadow: 0 16px 35px rgba(0,0,0,.35);
      transition: transform .08s ease, filter .2s ease;
      user-select:none;
    }
    button:hover{ filter: brightness(1.05); }
    button:active{ transform: translateY(1px) scale(.99); }

    .ghost{
      background: rgba(255,255,255,.07);
      color: var(--ink);
      border: 1px solid rgba(255,255,255,.16);
      box-shadow: none;
    }
    .ok{
      background: linear-gradient(135deg, rgba(109,240,168,.95), rgba(124,240,255,.75));
    }
    .warn{
      background: rgba(255,211,109,.18);
      color: rgba(255,233,190,.96);
      border: 1px solid rgba(255,211,109,.32);
      box-shadow:none;
    }

    .mini{
      font-size: 12px;
      color: var(--muted);
      line-height:1.5;
    }

    .stage{
      margin-top: 16px;
    }

    .game{
      margin-top: 14px;
      display:grid;
      gap:12px;
    }

    /* Memory */
    .grid{
      display:grid;
      grid-template-columns: repeat(4, minmax(0,1fr));
      gap:10px;
    }
    @media (max-width: 520px){
      .grid{ grid-template-columns: repeat(3, minmax(0,1fr)); }
    }
    .tile{
      position:relative;
      aspect-ratio: 1 / 1;
      border-radius: 18px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      overflow:hidden;
      display:flex; align-items:center; justify-content:center;
      font-size: 22px;
      user-select:none;
      cursor:pointer;
      transition: transform .12s ease, background .2s ease, border-color .2s ease;
    }
    .tile:hover{ transform: translateY(-1px); }
    .tile.revealed{
      background: rgba(255,77,125,.10);
      border-color: rgba(255,77,125,.35);
    }
    .tile.matched{
      background: rgba(109,240,168,.10);
      border-color: rgba(109,240,168,.35);
      cursor:default;
    }
    .tile .face{
      position:absolute; inset:0;
      display:flex; align-items:center; justify-content:center;
      opacity:0;
      transform: scale(.9);
      transition: opacity .16s ease, transform .16s ease;
    }
    .tile.revealed .face, .tile.matched .face{
      opacity:1; transform: scale(1);
    }
    .tile .back{
      position:absolute; inset:0;
      display:flex; align-items:center; justify-content:center;
      opacity:1;
      transition: opacity .16s ease;
      color: rgba(243,241,255,.65);
      font-size: 16px;
      letter-spacing:.12em;
      text-transform:uppercase;
    }
    .tile.revealed .back, .tile.matched .back{ opacity:0; }

    /* Drag hearts */
    .dragzone{
      border-radius: 20px;
      border: 1px dashed rgba(255,255,255,.25);
      background: rgba(255,255,255,.05);
      padding: 14px;
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:12px;
      align-items:stretch;
    }
    @media (max-width: 720px){
      .dragzone{ grid-template-columns: 1fr; }
    }
    .bucket{
      border-radius: 18px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.18);
      padding: 12px;
      min-height: 140px;
      position:relative;
    }
    .bucket h3{
      margin: 0 0 8px;
      font-size: 13px;
      color: rgba(243,241,255,.86);
      letter-spacing:.08em;
      text-transform: uppercase;
    }
    .bucket p{
      margin:0 0 10px;
      color: var(--muted);
      font-size: 13px;
      line-height:1.5;
    }
    .chips{
      display:flex; flex-wrap:wrap; gap:8px;
    }
    .chip{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding: 10px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      cursor: grab;
      user-select:none;
      font-weight: 650;
      font-size: 13px;
      color: rgba(243,241,255,.9);
    }
    .chip:active{ cursor:grabbing; }
    .chip .heart{ filter: drop-shadow(0 8px 14px rgba(0,0,0,.35)); }

    .footer{
      margin-top: 14px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:10px;
      flex-wrap:wrap;
    }

    .toast{
      position:fixed;
      left:50%;
      bottom:18px;
      transform: translateX(-50%);
      background: rgba(0,0,0,.55);
      border: 1px solid rgba(255,255,255,.16);
      color: rgba(243,241,255,.92);
      padding: 10px 12px;
      border-radius: 14px;
      box-shadow: 0 16px 40px rgba(0,0,0,.55);
      opacity:0;
      pointer-events:none;
      transition: opacity .2s ease, transform .2s ease;
      max-width:min(92vw, 720px);
      font-size: 13px;
      backdrop-filter: blur(10px);
    }
    .toast.on{ opacity:1; transform: translateX(-50%) translateY(-2px); }

    .final{
      text-align:center;
      padding: 20px 14px;
    }
    .final h2{
      margin: 0 0 8px;
      font-size: 26px;
      letter-spacing:-.02em;
    }
    .final p{
      margin: 0 auto 14px;
      max-width: 62ch;
      color: var(--muted);
      line-height:1.6;
    }

    .badge{
      display:inline-flex;
      align-items:center;
      gap:8px;
      padding: 8px 12px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.06);
      color: rgba(243,241,255,.86);
      font-size: 12px;
      letter-spacing:.04em;
    }
    .spark{
      width:10px;height:10px;border-radius:99px;
      background: rgba(255,77,125,.9);
      box-shadow: 0 0 0 6px rgba(255,77,125,.12);
    }

    .hidden{ display:none !important; }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="seal" aria-hidden="true"></div>
        <div>
          <h1>UM CAMINHO DE VOLTA</h1>
          <p>uma história interativa, curta e sincera</p>
        </div>
      </div>
      <div class="progress">
        <span id="stepLabel">Etapa 1/4</span>
        <div class="dots" aria-hidden="true">
          <div class="dot on" id="d1"></div>
          <div class="dot" id="d2"></div>
          <div class="dot" id="d3"></div>
          <div class="dot" id="d4"></div>
        </div>
      </div>
    </header>

    <section class="card hero">
      <div>
        <div class="badge"><span class="spark"></span><span id="badgeText">Capítulo I — A Carta Que Eu Não Enviei</span></div>
        <h2 class="title" id="title">Oi… eu fiz isso pra você, com cuidado.</h2>
        <p class="subtitle" id="subtitle">
          Não é pressão. Não é insistência. É só um caminho bonito, com algumas escolhas, pra você sentir o que eu sinto
          — e, se não fizer sentido, tudo bem.
        </p>

        <div class="poem" id="poemBox">
          <blockquote id="poem">
            Eu não vim pedir “volta” como quem cobra.<br/>
            Vim pedir um minuto de paz<br/>
            pra te dizer: eu aprendi.<br/><br/>
            Se o amor é casa, eu quis reformar por dentro.<br/>
            Se for pra voltar, que seja melhor.<br/>
            Se não for, que você saia daqui leve.
            <small>— com respeito, do começo ao fim</small>
          </blockquote>
        </div>

        <div class="btnrow">
          <button id="btnStart">Começar o joguinho</button>
          <button class="ghost" id="btnSkip">Pular para o final</button>
        </div>

        <p class="mini" style="margin-top:10px">
          Dica: você pode personalizar com nomes e lembranças (com moderação).
          Se quiser, depois eu adapto o texto pro seu caso.
        </p>
      </div>

      <div class="panel">
        <div class="card" style="padding:14px">
          <div style="display:flex;align-items:center;justify-content:space-between;gap:10px;">
            <div>
              <div style="font-weight:800; letter-spacing:.06em; text-transform:uppercase; font-size:12px; color:rgba(243,241,255,.85)">Regras do jogo</div>
              <div class="mini" id="rules" style="margin-top:6px">
                1) Sem pressa. 2) Sem culpa. 3) No fim, você escolhe.
              </div>
            </div>
            <div class="badge" title="tempo estimado"><span>⏳</span><span>2–4 min</span></div>
          </div>
        </div>

        <div class="card" style="padding:14px">
          <div style="font-weight:800; letter-spacing:.06em; text-transform:uppercase; font-size:12px; color:rgba(243,241,255,.85)">O que eu quero comunicar</div>
          <ul class="mini" style="margin:10px 0 0; padding-left: 18px; line-height:1.6">
            <li>eu reconheço erros sem justificar</li>
            <li>eu respeito seus limites</li>
            <li>eu ainda escolho você — mas só se for recíproco</li>
          </ul>
        </div>

        <div class="card" style="padding:14px">
          <div style="font-weight:800; letter-spacing:.06em; text-transform:uppercase; font-size:12px; color:rgba(243,241,255,.85)">O “final feliz” aqui é</div>
          <p class="mini" style="margin:10px 0 0; line-height:1.6">
            recomeçar com maturidade: conversa, calma, presença, e um sim que seja livre.
          </p>
        </div>
      </div>
    </section>

    <!-- STAGE AREA -->
    <section class="card stage hidden" id="stage">
      <!-- Stage content changes per step -->
      <div id="stageInner"></div>

      <div class="footer">
        <button class="ghost" id="btnBack">Voltar</button>
        <div class="mini" id="hint"></div>
        <button id="btnNext">Continuar</button>
      </div>
    </section>

    <!-- FINAL -->
    <section class="card stage hidden" id="final">
      <div class="final">
        <div class="badge"><span class="spark"></span><span>Última página</span></div>
        <h2>Você quer viver esse final feliz?</h2>
        <p>
          Não é promessa vazia — é convite pra recomeçar do jeito certo: com conversa,
          respeito e escolhas claras. Se você disser não, eu vou respeitar e seguir em paz.
        </p>

        <div class="poem" style="max-width:720px;margin:0 auto 14px;">
          <blockquote>
            Eu não quero te convencer.<br/>
            Quero te encontrar.<br/><br/>
            Se o “nós” ainda couber em você,<br/>
            eu topo construir devagar.<br/><br/>
            Se não couber, eu te desejo luz.<br/>
            E guardo o que foi bonito sem te prender.
            <small>— resposta certa é a que te faz bem</small>
          </blockquote>
        </div>

        <div class="btnrow" style="justify-content:center">
          <button class="ok" id="btnYes">Sim, eu quero</button>
          <button class="warn" id="btnNo">Não, prefiro não</button>
        </div>

        <p class="mini" id="finalMsg" style="margin-top:12px"></p>
      </div>
    </section>

    <div class="toast" id="toast" role="status" aria-live="polite"></div>
  </div>

  <script>
    // ---------- Utilities ----------
    const $ = (id) => document.getElementById(id);
    const toastEl = $("toast");
    let toastTimer = null;

    function toast(msg){
      toastEl.textContent = msg;
      toastEl.classList.add("on");
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => toastEl.classList.remove("on"), 2400);
    }

    function setDots(step){
      ["d1","d2","d3","d4"].forEach((d,i)=> $(d).classList.toggle("on", i < step));
      $("stepLabel").textContent = `Etapa ${step}/4`;
    }

    // ---------- Steps content ----------
    let step = 0; // 0 intro, 1..3 stages, 4 final
    const stage = $("stage");
    const stageInner = $("stageInner");
    const final = $("final");
    const btnNext = $("btnNext");
    const btnBack = $("btnBack");
    const hint = $("hint");

    const steps = [
      null,
      {
        badge:"Capítulo II — O Que Eu Aprendi",
        title:"Escolhe com o coração: qual palavra merece voltar?",
        subtitle:"Toque em duas cartas iguais para formar pares. Quando completar, você desbloqueia o próximo trecho.",
        poem:`Eu não aprendi tarde.<br/>
              Eu aprendi de verdade.<br/><br/>
              Que amor sem cuidado vira peso,<br/>
              e carinho sem presença vira saudade.<br/>
              Eu quero ser presença.`,
        type:"memory"
      },
      {
        badge:"Capítulo III — O Que Eu Ofereço",
        title:"Arraste os corações para onde eles pertencem.",
        subtitle:"Sem prometer o impossível: só o que eu consigo sustentar com atitudes.",
        poem:`Eu não trago fogos — trago constância.<br/>
              Não trago discurso — trago mudança.<br/><br/>
              Se você topar, eu topo o simples:<br/>
              conversa limpa, respeito e esperança.`,
        type:"drag"
      },
      {
        badge:"Capítulo IV — O Que Eu Peço",
        title:"Escolha uma porta. (Sem pegadinha.)",
        subtitle:"Cada porta é um jeito de recomeçar. Você pode mudar de ideia a qualquer momento.",
        poem:`Se for pra voltar,<br/>
              que seja com verdade.<br/><br/>
              Um “sim” tranquilo vale mais<br/>
              que mil “talvez” apressados.`,
        type:"choice"
      }
    ];

    // ---------- Renderers ----------
    function renderStep(n){
      const s = steps[n];
      $("badgeText").textContent = s.badge;
      $("title").textContent = s.title;
      $("subtitle").textContent = s.subtitle;
      $("poem").innerHTML = `${s.poem}<small>— página ${n} de 4</small>`;

      setDots(n);
      stage.classList.remove("hidden");
      final.classList.add("hidden");
      hint.textContent = "";

      if(s.type === "memory") renderMemory();
      if(s.type === "drag") renderDrag();
      if(s.type === "choice") renderChoice();

      btnBack.classList.toggle("hidden", n === 1);
      btnNext.disabled = true;
      btnNext.style.filter = "grayscale(.25)";
      btnNext.title = "Complete o desafio para continuar";
    }

    // ---------- Memory game ----------
    let mem = { first:null, lock:false, matched:0 };

    function renderMemory(){
      mem = { first:null, lock:false, matched:0 };

      const words = ["Respeito","Calma","Verdade","Cuidado","Respeito","Calma","Verdade","Cuidado"];
      // shuffle
      for(let i=words.length-1;i>0;i--){
        const j = Math.floor(Math.random()*(i+1));
        [words[i],words[j]] = [words[j],words[i]];
      }

      stageInner.innerHTML = `
        <div class="game">
          <div class="mini">Encontre os pares: <b>Respeito</b>, <b>Calma</b>, <b>Verdade</b>, <b>Cuidado</b>.</div>
          <div class="grid" id="grid"></div>
        </div>
      `;

      const grid = $("grid");
      words.forEach((w, idx)=>{
        const t = document.createElement("div");
        t.className = "tile";
        t.dataset.value = w;
        t.dataset.index = idx;
        t.innerHTML = `
          <div class="back">⋆</div>
          <div class="face">${w}</div>
        `;
        t.addEventListener("click", () => onFlip(t));
        grid.appendChild(t);
      });

      hint.textContent = "Dica: sem pressa. O importante aqui é lembrar o que sustenta um recomeço.";
    }

    function onFlip(tile){
      if(mem.lock) return;
      if(tile.classList.contains("matched")) return;
      if(tile.classList.contains("revealed")) return;

      tile.classList.add("revealed");

      if(!mem.first){
        mem.first = tile;
        return;
      }

      const a = mem.first;
      const b = tile;
      mem.lock = true;

      if(a.dataset.value === b.dataset.value){
        setTimeout(()=>{
          a.classList.remove("revealed");
        