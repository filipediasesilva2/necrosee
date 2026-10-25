<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no, viewport-fit=cover">
<title>NECROSE — Sobrevivência Zumbi</title>
<style>
  :root{
    --blood:#8f1a1a;
    --blood-bright:#c92a2a;
    --bone:#d8d0bd;
    --ink:#0a0908;
    --panel:#14100dcc;
    --sick:#7ea34a;
    font-family: 'Courier New', monospace;
  }
  html,body{
    height:100%; margin:0; padding:0; overflow:hidden; background:#000;
    -webkit-user-select:none; user-select:none;
    touch-action:none; overscroll-behavior:none;
    padding-top:env(safe-area-inset-top,0px);
    padding-bottom:env(safe-area-inset-bottom,0px);
  }
  #canvas-wrap{ position:fixed; inset:0; touch-action:none; }
  canvas{ display:block; width:100%; height:100%; touch-action:none; }

  /* ---------- START SCREEN ---------- */
  #start-screen{
    position:fixed; inset:0; z-index:50;
    background:
      radial-gradient(ellipse at 50% 20%, rgba(143,26,26,0.25), transparent 60%),
      linear-gradient(180deg, #100c0b 0%, #050403 100%);
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    color:var(--bone); text-align:center; padding:20px;
  }
  #start-screen h1{
    font-size:clamp(2.6rem,9vw,5.5rem);
    letter-spacing:0.08em;
    margin:0;
    color:var(--blood-bright);
    text-shadow: 0 0 18px rgba(201,42,42,0.6), 0 0 2px #000;
    font-weight:900;
    transform: skewX(-4deg);
    border-bottom:4px solid var(--blood);
    padding-bottom:10px;
  }
  #start-screen .tagline{
    margin-top:10px; color:#9a8f7d; font-size:0.95rem; letter-spacing:0.15em;
  }
  #start-screen .brief{
    max-width:520px; margin-top:28px; line-height:1.7; font-size:0.85rem; color:#c9c2b3;
    text-align:left; background:var(--panel); border:1px solid #3a2a22; padding:16px 20px;
  }
  #start-screen .brief b{ color:var(--blood-bright); }
  #playBtn{
    margin-top:30px; padding:14px 46px; font-size:1.1rem; letter-spacing:0.1em;
    background:var(--blood); color:#fff; border:2px solid #ffdada44;
    cursor:pointer; font-family:inherit; font-weight:bold;
    box-shadow:0 0 25px rgba(143,26,26,0.7);
  }
  #playBtn:hover{ background:var(--blood-bright); }
  #start-screen .hint{ margin-top:14px; font-size:0.75rem; color:#665; }

  /* ---------- HUD ---------- */
  #hud{ position:fixed; inset:0; pointer-events:none; z-index:20; display:none; }
  #crosshair{
    position:absolute; top:50%; left:50%; transform:translate(-50%,-50%);
    width:22px; height:22px;
  }
  #crosshair div{ position:absolute; background:var(--bone); opacity:0.85; }
  #crosshair .h{ width:22px; height:2px; top:10px; left:0; }
  #crosshair .v{ width:2px; height:22px; top:0; left:10px; }
  #crosshair .dot{ width:3px; height:3px; top:9.5px; left:9.5px; background:var(--blood-bright); }

  #bottom-bar{
    position:absolute; bottom:0; left:0; right:0;
    display:flex; justify-content:space-between; align-items:flex-end;
    padding:18px 24px calc(18px + env(safe-area-inset-bottom,0px)) 24px;
  }
  .stat-block{ background:var(--panel); border:1px solid #3a2a22; padding:10px 16px; min-width:170px; }
  #health-label{ font-size:0.7rem; letter-spacing:0.1em; color:#a99; margin-bottom:4px; }
  #health-bar-outer{ width:220px; height:16px; background:#1a1310; border:1px solid #4a3428; }
  #health-bar-inner{ height:100%; width:100%; background:linear-gradient(90deg,var(--blood),var(--blood-bright)); transition:width 0.15s; }
  #ammo-block{ text-align:right; color:var(--bone); }
  #ammo-count{ font-size:2rem; font-weight:bold; letter-spacing:0.02em; }
  #ammo-reserve{ font-size:1rem; color:#8a8070; }
  #weapon-name{ font-size:0.8rem; letter-spacing:0.15em; color:var(--sick); margin-bottom:2px; }
  #reload-msg{ color:var(--blood-bright); font-size:0.75rem; letter-spacing:0.1em; margin-top:4px; display:none; }

  #top-bar{ position:absolute; top:0; left:0; right:0; display:flex; justify-content:space-between; padding:16px 24px; }
  #wave-block, #score-block, #zombies-block{ background:var(--panel); border:1px solid #3a2a22; padding:8px 14px; color:var(--bone); font-size:0.85rem; letter-spacing:0.08em; }
  #wave-block b, #score-block b, #zombies-block b{ color:var(--blood-bright); }

  #hitmarker{
    position:absolute; top:50%; left:50%; width:30px; height:30px; transform:translate(-50%,-50%);
    opacity:0; pointer-events:none;
  }
  #hitmarker.headshot::before, #hitmarker.headshot::after,
  #hitmarker.show::before, #hitmarker.show::after{
    content:''; position:absolute; background:var(--blood-bright); width:14px; height:2px; top:14px;
  }
  #hitmarker.show::before{ left:0; transform:rotate(45deg); transform-origin:right; }
  #hitmarker.show::after{ right:0; transform:rotate(-45deg); transform-origin:left; }
  #hitmarker.headshot::before, #hitmarker.headshot::after{ background:#ffd23f; }

  #damage-vignette{
    position:absolute; inset:0; box-shadow: inset 0 0 0px rgba(180,0,0,0);
    transition:box-shadow 0.25s;
  }

  #scope-overlay{
    position:fixed; inset:0; z-index:25; display:none;
    background:radial-gradient(circle at center, transparent 27%, #000 27.5%);
  }
  #scope-overlay::before, #scope-overlay::after{
    content:''; position:fixed; background:#000; top:50%; left:0; right:0; height:2px; transform:translateY(-1px);
  }
  #scope-crosshair{
    position:fixed; top:50%; left:50%; width:1px; height:1px;
  }
  #scope-lines{ position:fixed; inset:0; pointer-events:none; }

  #kill-feed{
    position:absolute; top:70px; right:24px; display:flex; flex-direction:column; gap:4px; align-items:flex-end;
  }
  .kill-msg{ background:var(--panel); color:var(--bone); font-size:0.72rem; padding:4px 10px; border-left:3px solid var(--blood-bright); opacity:0; animation:fadein 0.2s forwards, fadeout 0.3s forwards 2.2s; }
  @keyframes fadein{ from{opacity:0; transform:translateX(10px);} to{opacity:1; transform:translateX(0);} }
  @keyframes fadeout{ to{opacity:0;} }

  #weapon-hint{
    position:absolute; bottom:70px; left:50%; transform:translateX(-50%);
    color:#887a68; font-size:0.7rem; letter-spacing:0.05em; text-align:center;
  }

  /* ---------- GAME OVER ---------- */
  #gameover-screen{
    position:fixed; inset:0; z-index:60; display:none;
    background:radial-gradient(ellipse at center, rgba(60,0,0,0.4), #000 75%);
    flex-direction:column; align-items:center; justify-content:center; color:var(--bone); text-align:center;
  }
  #gameover-screen h1{ font-size:clamp(2.4rem,8vw,4.5rem); color:var(--blood-bright); letter-spacing:0.1em; margin:0; }
  #gameover-stats{ margin-top:18px; font-size:1rem; color:#c9c2b3; line-height:1.8; }
  #restartBtn{
    margin-top:26px; padding:12px 40px; font-size:1rem; letter-spacing:0.1em;
    background:var(--blood); color:#fff; border:2px solid #ffdada44; cursor:pointer; font-family:inherit; font-weight:bold;
  }
  #restartBtn:hover{ background:var(--blood-bright); }

  /* ---------- VICTORY ---------- */
  #victory-screen{
    position:fixed; inset:0; z-index:60; display:none;
    background:
      radial-gradient(ellipse at 50% 30%, rgba(126,200,230,0.18), transparent 60%),
      radial-gradient(ellipse at center, rgba(10,20,15,0.9), #000 80%);
    flex-direction:column; align-items:center; justify-content:center; color:var(--bone); text-align:center;
    padding:20px;
  }
  #victory-ghost{
    font-size:clamp(4rem,16vw,7.5rem); line-height:1;
    animation:ghost-float 3s ease-in-out infinite;
    filter: drop-shadow(0 0 25px rgba(180,220,255,0.65));
  }
  @keyframes ghost-float{
    0%,100%{ transform:translateY(0) rotate(-2deg); }
    50%{ transform:translateY(-18px) rotate(2deg); }
  }
  #victory-screen h1{
    font-size:clamp(2.6rem,9vw,5rem); letter-spacing:0.1em; margin:14px 0 4px;
    color:#eaf6ff; text-shadow:0 0 20px rgba(150,210,255,0.8);
  }
  #victory-screen .v-sub{ color:#9fd0e0; font-size:0.95rem; letter-spacing:0.08em; margin-bottom:18px; }
  #victory-stats{ font-size:1rem; color:#c9c2b3; line-height:1.8; margin-bottom:10px; }
  #victoryRestartBtn{
    margin-top:22px; padding:12px 40px; font-size:1rem; letter-spacing:0.1em;
    background:#1c4a5a; color:#eaf6ff; border:2px solid #bfe8ff66; cursor:pointer;
    font-family:inherit; font-weight:bold;
  }
  #victoryRestartBtn:hover{ background:#276a80; }

  @media (prefers-color-scheme: light){ body{ background:#000; } }

  /* ---------- TOUCH CONTROLS (mobile) ---------- */
  #touch-controls{
    position:fixed; inset:0; z-index:22; display:none;
    pointer-events:none; /* zones re-enable per element below */
  }
  #touch-controls *{ -webkit-tap-highlight-color:transparent; -webkit-touch-callout:none; touch-action:none; }

  #joy-base{
    position:fixed; width:96px; height:96px; border-radius:50%;
    border:2px solid rgba(216,208,189,0.35); background:rgba(20,16,13,0.35);
    transform:translate(-50%,-50%); display:none; pointer-events:none;
  }
  #joy-knob{
    position:absolute; top:50%; left:50%; width:44px; height:44px; border-radius:50%;
    background:rgba(143,26,26,0.65); border:2px solid rgba(216,208,189,0.5);
    transform:translate(-50%,-50%);
  }

  .touch-btn{
    position:fixed; pointer-events:auto; display:flex; align-items:center; justify-content:center;
    border-radius:50%; background:rgba(20,16,13,0.55); border:2px solid rgba(216,208,189,0.35);
    color:var(--bone); font-size:1.1rem; user-select:none;
  }
  .touch-btn:active{ background:rgba(143,26,26,0.55); }

  #btn-fire{
    width:92px; height:92px; right:22px; bottom:calc(30px + env(safe-area-inset-bottom,0px));
    background:rgba(143,26,26,0.45); font-size:1.6rem;
  }
  #btn-aim{
    width:60px; height:60px; right:120px; bottom:calc(120px + env(safe-area-inset-bottom,0px));
    font-size:1.3rem;
  }
  #btn-reload{
    width:56px; height:56px; right:28px; bottom:calc(140px + env(safe-area-inset-bottom,0px));
    font-size:1.2rem;
  }
  #btn-fullscreen{
    width:44px; height:44px; right:20px; top:calc(20px + env(safe-area-inset-top,0px));
    font-size:1.1rem;
  }
  #weapon-btns{
    position:fixed; left:22px; top:calc(90px + env(safe-area-inset-top,0px));
    display:flex; flex-direction:column; gap:10px; pointer-events:auto;
  }
  .weapon-btn{
    width:48px; height:48px; border-radius:10px; background:rgba(20,16,13,0.55);
    border:2px solid rgba(216,208,189,0.35); color:var(--bone); font-weight:bold; font-size:0.95rem;
    display:flex; align-items:center; justify-content:center;
  }
  .weapon-btn.active{ background:rgba(126,163,74,0.5); border-color:var(--sick); }
</style>
</head>
<body>

<div id="canvas-wrap"></div>

<!-- START -->
<div id="start-screen">
  <h1>NECROSE</h1>
  <div class="tagline">SOBREVIVA À NOITE</div>
  <div class="brief">
    <b>WASD</b> move · <b>MOUSE</b> mira · <b>CLIQUE ESQUERDO</b> atira · <b>R</b> recarrega<br>
    <b>1 2 3</b> troca de arma · <b>CLIQUE DIREITO</b> mira de precisão (fuzil) · <b>SHIFT</b> corre<br><br>
    Tiro na <b>cabeça</b> mata na hora. Tiro no <b>peito</b> causa dano pesado. Tiro na <b>perna</b> derruba ou deixa lento.<br>
    Cuidado: rastejantes, corredores e andarilhos se comportam de formas diferentes.<br><br>
    <b>🎮 Controle</b> também funciona: analógico esquerdo move, direito mira, RT atira, LT mira de precisão, X/Y/B trocam de arma, LB recarrega, A corre, START reinicia após morrer.
  </div>
  <button id="playBtn">ENTRAR NO PESADELO</button>
  <div class="hint">clique para travar o mouse na tela</div>
</div>

<!-- GAME OVER -->
<div id="gameover-screen">
  <h1>VOCÊ MORREU</h1>
  <div id="gameover-stats"></div>
  <button id="restartBtn">TENTAR DE NOVO</button>
</div>

<!-- VICTORY -->
<div id="victory-screen">
  <div id="victory-ghost">👻</div>
  <h1>PARABÉNS!</h1>
  <div class="v-sub">Você sobreviveu às 15 ondas de NECROSE</div>
  <div id="victory-stats"></div>
  <button id="victoryRestartBtn">JOGAR NOVAMENTE</button>
</div>

<!-- HUD -->
<div id="hud">
  <div id="crosshair"><div class="h"></div><div class="v"></div><div class="dot"></div></div>
  <div id="hitmarker"></div>
  <div id="damage-vignette"></div>

  <div id="top-bar">
    <div id="wave-block">ONDA <b id="wave-num">1</b>/15</div>
    <div id="zombies-block">RESTAM <b id="zombies-num">10</b></div>
    <div id="score-block">ABATES <b id="score-num">0</b></div>
  </div>

  <div id="kill-feed"></div>

  <div id="weapon-hint">1 PISTOLA &nbsp; 2 ESCOPETA &nbsp; 3 FUZIL DE PRECISÃO &nbsp; 4 CORPO A CORPO (após coletar)</div>

  <div id="bottom-bar">
    <div class="stat-block">
      <div id="health-label">VIDA</div>
      <div id="health-bar-outer"><div id="health-bar-inner"></div></div>
    </div>
    <div id="ammo-block">
      <div id="weapon-name">PISTOLA</div>
      <div id="ammo-count">12</div>
      <div id="ammo-reserve">reserva: 48</div>
      <div id="reload-msg">RECARREGANDO...</div>
    </div>
  </div>
</div>

<div id="scope-overlay"></div>

<!-- TOUCH CONTROLS -->
<div id="touch-controls">
  <div id="joy-base"><div id="joy-knob"></div></div>
  <div id="weapon-btns">
    <div class="weapon-btn active" data-w="pistol">1</div>
    <div class="weapon-btn" data-w="shotgun">2</div>
    <div class="weapon-btn" data-w="sniper">3</div>
  </div>
  <div class="touch-btn" id="btn-reload">⟳</div>
  <div class="touch-btn" id="btn-aim">🎯</div>
  <div class="touch-btn" id="btn-fire">🔫</div>
  <div class="touch-btn" id="btn-fullscreen">⛶</div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
"use strict";

/* Runner-zombie face texture, embedded so the published page stays self-contained */
const RUNNER_FACE_DATA_URI = "data:image/png;base64,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";
const runnerFaceTexture = new THREE.TextureLoader().load(RUNNER_FACE_DATA_URI);
runnerFaceTexture.wrapS = THREE.ClampToEdgeWrapping;
runnerFaceTexture.wrapT = THREE.ClampToEdgeWrapping;

/* Boss face photo */
const BOSS_FACE_DATA_URI = "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAGAAYADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwC3IEbd8+4544J/xx+dShkePDAyehBztP6n9aju45FiM0lrImw8sUYf40ExzRjY6sDzgkHP+fpX6TF6H57UWo4zpErOys3Hfkj8azYb5sg3dlDLg/ei/dtj196s6greUQMEAdyRj/P4VUSMkY25JHPOcVojBsnSS0mRZLf7SvJDJMBwfYjqKnVd6EFc+454qjAiqx2HBPJXGOatQk7wR/F6iqJJfKSTG9SQBgAjnFXoJbqG2Fsj+dCBjbJyV/3fSqiMudoJwBzg5qyqh4JMt8y4wD0NS7A2WEMbIr8Z9x3pJf3m1igIHt0qDy3jlVJG2eYufmHBFK0nlHypDxnIOf60myGTbd3GOmQc1lalqosYXiQq5ZcEdhVLXddEMBSKTkcMw4rir3VkY7HdmL52gdSa4MRilH3UbQpN6l7UtSyjFpAEPbP6CuclD3MoluEKwZz5ZOC496ZcXiRrvmIMv8KDoh/rWBqmuSxxyTFicDp715FSot2d1KlKTshfFrK0DbQIkDfKgPQVxpvNhxGdx9qZd3t5qLnzpWK56dqIkij7jNedUq3eh7+Hw3s42luNInnYs7mrFvBGGG4ionmUDAIApguY153Csr9zo5X0NqIRquFwKtwzIiAGucGpKo4yaY+qSHhRj0zVqqkYyw85nXJfKo5IFSfboz1I9q4aW9uHHLkfSmx3M69JGqvrNjP+zm+p3aXscaSng5Uiq0V6kKfuziuRe7uZF27yB7U6Ke5/vE49aTxI1l9up32l6ztbMh4rdiubC6hy5CsB1ryn7ZcJ3Apw1S7X7smKtYtLcwnljb912PTXnsoVG3YeeM96gfUrfPygfSvOjqN6wy0pNNOo3Q7ij61HsJZZNbs9DGoQE5yBU8dzDvGWXFecDVbhfvAVYg1kjlg34GhYiJLy6aO/aRMnaQc+lQG5jBOSPxrkotcDDDFlpZtR3jCkHNDrREsHUT1Nq7Om3BKyIu49x1rG1GyubNjLbsZIeuO4qtHK5k3E1u2FwskOxj7c1CkpG/LKmY9pqCudrHa3vWxa3bo4ZHIx6GszWNKK5ubZeOpUVn2l60ZCs3FCm47lunGoro7QaqrgfaF3n1zg1Yt7lyC1rIfXY3X865m3u7ZgC0gq/banbRnIfJ9q0VRM5Z0Guh2GieIp7aQAOwYHof4a9e8BfE2a1ZLe6kEsPQqx/rXz7BqcE8oVoQFz98da2LeeW0dJC/mRNyr46exqmlNWZheVN3Wh9paHrNnrEAe0dXVhnGfmWrmZPMMco3Y6H1FfMXgzxdeabMkkVyVI5I/p9K9x8H+NNO1sRxzTJDcuOAT8p/wrgrYdx1jsehQxaqe7LRnYywgbdgGMZxSwEPbnja68EGmOXQklxx6UIVPIPPU1zHYSK+1OvPpQJ1JKmN89jQ6naCORSEMm1hIMHtQAok3DK49xQ24kFWI9xUkABlBKhhnnmo2j8u4domBUnlc5xQB85W9zqsCyCLUbgtnCCVhIB7YPb8KtQyzykPd7PMYfNhNoB9cHApswKsc72VugyP8AEfyqS3CxgFgwU99u0n+QNfo0bI+QqO7KephxHwSQDx24+lQWqhioCgsRwO5NTaiOFOMbjxkYBqvAXQMPmU8kfN+orVHOwdTHcgSq6HrhhVkD5lIGVIzx/PFRi91FeTPHcLswVmQZJ9SfWpDdBmJOneRKUAMqOdh/4D2pisSRODI2MHPquD+BrRtraSf5Lf53IyELct6gZ6/SsuKQMDnJI7CnzB5IV8uRhgggqcMp/nSltoJGil1PagxXCCe36mGTqp/2T2Ncz4m1hVZ4rYkRZyCTyam8S6zI1sqZJcgBnbBJP171w2rXLPII0OZSPvdAo9TXlYnEW92J0Qhfcq6rqEkk5jQ59f7q1jzXCwOxjkLyOPmf/D0qj4smeFIxbSMFA+bB61y02rSRLjJZ68apWs9T1KGFdRXR0V5eRxqXmkx6k1y+qXxvJNq8Rj9apSzTXDlpXJqCabHyJ+dcVStzHrYfCKGrHTT7AUj/ABNQosjdzUY65qwXG0EcHvXO5HoqFkMkQr/FmkRN2cdhml+/nnpTos8gdDUlWGiI43HpT5EAAIHanDAj5pckjGM0XAYUVRzQgHXFSpbSudzcDtVyCxd8EKSB1pcwWI4EVYw5A6ZOaczBIAFUBj1rQh02aVwioSD09K1IvC91P8xibHtUuaQ+Vs5AqzHFTCFAoLOGYdq6afwleoMpC5+gqi+jXlucSWrOPcUKaYcrMdhhfuge4OaSOIyHgYHqa1hbFSB9jwaiuYLhuBHtHsKfMLlMyZQH4qPbjmrUtvImSVNV2DZ5ouFhvOaVWZTkGngKe9NbrwKLiaTLEVyygZGTV61vkDDLYrIPvSZPrxVqpYynRUjuLK8jlUKSpzWRrWkN5vnWqgq3UDtWHb3EsMgZGIwa6XT9VLxjeQTW6mpqzOKVKdF3iZH9mXCLlximRBoZevTrXQ3dwZUz29KyGjDMxqXFLYqNRy3L9nKjJuXg+lbmlan5J2SANGwwVPeuRVZITuSr1pdB+vBHatYTsc9WkpHboxjHn2rloepH8Sf41t6F4gkt3Uo5BHII6fjXB2V68TAqTj61pO6unm23yydSmeDW/Nc4JUrM+kPAPxKbYtpqsnnRcBXP3h9PavWbK7tb22W4tZUkRuhU18QaZqzwyLh2RgemcEH2r1L4b+PbrS7oI0m6Jz8yk8H1/GuerQjLWO50UcTKnpPY+lkJwQQwoyuzBxWZ4e1O11WyW7tJ8qw+ZSeVNaihd/lyAYbua4GraM9NNSV0CLG3JLA+1IwbzmdFyCOTTsJG20Pz2pVfeDlc496Qz52LuDyeO+P/AK1MikYuHEqt9D0/Ln9aRkGc7duepYc/yNOS3uEcF4HAxuDCPcMfXnNfo0T5CW5S1Rnbbl8gdMEU6EAbCTuyKq6s24IwCg55GamsXOAvQj0IOa1RhItLHPJGWWF3Re+3PNEwUE/dUkDIzioE3iZ3hmmt5NuPlJGeakmdnYF2y7feJ4BPrmmQwQujgK/f1zTdUvltYtgIDvx9PpUF1MtvCzSfwnjNctqF2Z5Wlkbco5OT0rkxddU42W5cIczGajencTjcScBc9TXP6lcrbxlOsjnLtn9KsXl1Gm+RyfMb7nsK5XXb9Uibn5m/SvAqVLas9CjSc5JIo+KNURYPJjwXYY57VyY5JZjUl5N5kpdicdqqvIW9hXk1anMz6bC0PZwsPZ2f5V6Uhi+UH1pEYYxVkDcoA5FY3OtKxScEUq8CrLx4yKYkO44BB/ClcrcjTduGOan2lcAck+laOm6PPdMFjU898V2mg+BiQryqZN3UDjFRKaQ1Bs4a0025umCpGTXU6d4QuNqmRMZ9q9Q0PwXHFCCkIGf4q6zT/DsZjw8BLZwp7CueVd9DWNLueT6f4Ma4ARYwcdTitux8BMhAKcHnO2vYtL0eC1hVVUE55JHetSO0hwAQN2eoWsnUkzZU0eWW3gdIwpWIErg8itqz8KSf88AMdgOK7+ONQHMcJYqeuKtwRsQpMbAkdam7ZXKkcHH4U8z5Qi7sdKRvBKSp+8RTju1eiRRIWPQHuSKnFrF1D4qlETSPH9R+H8LOGFshXpkLisW88EwRkq9u2DxnFe/JCrA79rD3AqC50y2uB9wcdadn0ZNkfM2r+CUw3lp17Yridb8JTwEssZP4V9aX/hy3bJVcDFcprXhPMZZYwwHtVKpJbkyppnyjd6ZPC33SPUVU8pgcGvdvEXhWJiweLaRnkDBrz/xH4XmtkMkPzj24IraNRMwcGjijGNpytRMhxxVq4hlgkKurA+9MRt3y960IIWjCqMnn0p9nOY5ACcKetJMNp55qEfSqTsTKKkrM6NJQYxjmjZntisqyvTE22Rdy/wAqvjUIOucVspJnDKlJMvRQh+DiorrTmX54Tg+1QLqUQ6MBSrrESvg5Iq04mbjPsSWt0Q5ilBV19R1rRiumVcqeahkhg1KHfEQsgHDDt7VQWWW3kMEy4ce9VexlKKkbomW5wG+SQDhq0dMvnglVZPvD8jXNLKz42qQQa0LHzHyCx3jkZrSMjKcFbU96+FfjGawu0eRy8T4WQE8fT619CWNxBf20c9u+9HXcpr4p8O6g4kU7wCpwVNfQfwe8VbCmmXEoKyEbMk5DVnXpc0eZCw1Z05cj2PXBJsH72NsD+LFK6AfMhyrUPuaMZPXqKVAdm1SMjoK4D0z5xFw5B2TGQE4ILhv05qWC71G3uPM+2SCMgjy3A2jjggcVQOqziCT7RpVlMd/ATKKR/jVtbgTIMQ+UpHCf3fbIr9EjqfJTVmQa5efarWJZoR9qTgyKuA6+4qhp0jD723I/2cGl1FlZwoKhgM8nH61DZna+cq2f7rg5reKsjnluau5SxzgHtzTbo7IN52gZ54xUSybCc5Az3FYPiTU2bESMML0weDWVesqUbijHmZV1nUt7tHnAB+WuburwZZg42L0zzuNU9SvZbiZo0baAf3j5x+ArKvbxSyoMFVGBivnK1dzd2elSoWRPe32VaRzzXI63dlycnlvfoKu6hcFiWJ+VRXM3czTTMx6Zrzq9XSx7OCw1ncZI+4+1MNL3FSBAVyRxXE2evbsRp1q/b9urE8ACq8UYdgFByfatnTrOUyBFGD+tJsLEK2kjEbxtz27103h/w61zImYjtPJOOK1fDnhzz5Q0qs4B/OvStI0ZIo1i2geoHasKlW2iNoQuYeieG2eSMRosaKOTjrXoOk6TFBEB5aj3IosYY4Aqop/Kti2gll6KcZrlbbOiMUh0CIDtUDA74q9GOOOtS22mSMepGfatWz0rA6H3OKVitChAjYyAT9atJG+3IWteKyC4BFWVtF6baaiHMjFWKYDO3bnrUyJL0rbW1UsCRk4pzWYYZxVcpNzDKPk/KfepQJCANuMVpNZj0FILfbwBVCbuUGyOvA9qT5ivBODWmLVu4B/rS/ZAwPr7UxGQ/nBRhcioZ1Zxhuh7VvxWRXqBinSWOSP3Y980Bc4DWNGgvEYlQr+3FcPr3hhwjboty/3gK9tudKV+QMewFZF9pMoQgKGX0qbWFZM+ZfFHhCOYMyDEnYjvXmeq6ZPp9wVkjI2n0r608QeHopNxWIxP6djXl3i7wyJNyzQ464YCtIVLbmc4Hh0se9N64x3FVgm05/Suj1zRp9PuGABK5rKkhWVCQMN7V0J3MbFBuDTakkUhulIFY+goFYZ3yaKldAEB71G6laLg0b2iXBSNVDVf1W2FzB5qcSr0PqK5mxuDC4zyK6qylDwgqQQRXVTd0ebXhySuZ+nXcZYI/wArCt2zeNXDcGuV1SE292SowDzV7TLtioVm+Yd60hJJ2MqlNuN0du0UUluL63GGTAkTuR611nhTUTbyRSiU5U5XJ9K8+0q+eCYNn5T1FdDA/wBnkSVCDBIcpjse4rqVmjy5ppn1x4G8QR63pEcgcGSMBZB36da6NfmHy/nXzf8ADXxU+majHKrcY2upPBWvofT7pbu2S5gw0brkEV5uIpcjutj1sLW9pGz3PnG5KhiwZUGc8Dj+lNLCRMhvow5z/OiXO3nax7AoOfyzUe1UPzbFyM8jFfoEdUfMT3K097fQuEgm8uNgSVKK2W9eeaW0uLqV0e4t7KTB+b9wFz9MdKbeFNkeAGIByOP0pls6gsAjDI9D/jV2J6DtTumNptS3WBs42h9w/CuL1u4WG3fzOZm+WM+5rprhheXPlxggA7cE9a5zxIyW0jST2xn8pvLQHkZx1rwsbVc52XQ3pJI43X0kgVVRsI4ycnvWKZ1RPnY5rS1ppJlM0nyKOAvpXOXcgLewrxqsrHu4anzRE1G7PlFF43VldTUszFpM0RpySTgAVwzldnr0oKKGbSegp6AjqKRc54JrU0eyku5ljHU1DdjYdpMO4rlCWbpgZJr0Pwn4ZnnYSzoYY+oH8Rq14T8OQwoJjGHdRlnY8LXTSa5pek8b/tbg/dT7o/Guecm9EXFJas3tC0gJEsdvB07/AP166jTtEkOPNkCeu3ivN5viLex4Sx09lj6ElePwNRr4312ebyxAIy3O7cW/+tUKk2V7RI9u0/SrOABiy8dyeTWzDFZKcK6jPoRzXgJ1/wAQk+a90JYScNGy4x9CKvWfiHWoZMJdgKekcnzAD2NX7EXtT6Ct44scYx9auQxL2rw7T/F2ppyLort+8gOQfcZrrNF8Z3aqFuGEsZGVdRyv19RS9m0HtD0sRDI4FSmIEcCuW0rxRb3O0bgJD/AT1+lbMerQOoKnvz3xU2sUpXNKJAB/Op1UEYwKo29xvBwTg1bR8mgAeIE4OMU1kUHjGPpT5G4xTUII9aAHrC+R8qhf51KsOODxSpKBj1HSntKuPeqJbGiIdcUGLtik8w9qUTE8kYoC4xoOKhlt1YHjmrRkGOlNaWIKcsPelYL2Me806GQYKDJ9a5LxF4Rju4mAUg9q7G91KzjO0TpvIJHNQHVrGUbBIskhIQADqe9LlK5j5v8AHPg65tNwmty0ZzhwOK8k1nQns5GniXMZPzAdq+4NbSz+ylbiGN9wxhsYryfxb4A03UFmuNGkjWQkhot2Vb6elVG8SJJM+U7u0kO50xgc4qi28d67nxp4evvD95Is9tJGm44OOK5CZ0DEYyK2RkQqflXJ6U6ckogxyck0YU/dFI57daAIGGPrW1oFwTujJzjpWMw71d0d9s5960puzMa8FKJq6xGHiDgcg1mQsUYMD0NbFxiSA1jEFH59a2k9bnJT2sb9lOJEBP410OjXauv2SY4jbp7H1rjNPuBG/JPNb1tNuwV4966Kc7nFiKR2ek3U1ndeU+QwI6dxXvvwc8VrJCulXUmGJ/dHPf0r5xtJzc2o2sonhH4sPSul8Ia01pdRypIVKEHIOCTWk4KcbHJTm6U00dJdeQ6jBJJP1H86ZIfLTchPy8Y5H9Kik1HR3ijlkh1S0UtjmMuT9famXrRF98SsUIyOecV9hB3PNnFpkEzhiAMZ7g0nKIz5wVXPJqG5dgQ4dtuBjKfzqC5mPklWZTuP3l6inUlyxbISHWO0XHmn5cZb0/KqB8u5icS5PmsXIb61bmlRLFw+TI2FUY65rJnn8olSMbR1r52Tu7ltdjiPHgjtVEKkAls4riCWkJx2rV8W6g17q87biQrbV+grGVisZx94968bETvLQ+swFFwpJy3G7SJMMcU+eT92IkxgHOccmo3cscnrRHya5j0USxAllABJJ6V6X4G0VLeD7fft5UR7nq3sK53wdozXUoupY1MatwDwCa9LsNNN2yGQ70XoucAfSspyGkQXt+12fsdurQWqAFVXq3uf8Ktabo0NzHnO/wBmGK6TTtGgUZEBT9a2raxijXKLgj04zWakirM5a20JY25jIwOR/Wpk0z7pK4x6DrXUSRKyccH+VRxx5BBxmrVSxPIc5cWjCJlTchA546iqRgK53jevVT6V1k8YOPUVkX9tg7k+oxT9oLkM07hslZBkcOB3FXrKeS1CspLw8hc9Rn1qFcH72P8ACmRynBiYk8/KaXOh8praddyltySMrK2QQfQ111hrbqFkLHbu+b8a4i0CrNg8buv1rXsJFCygg4znr/n1qW0x7HqGi6v5luwJB28iuhgvFIHPXpXkuh37xBwWJDD9K66zv8W8ZyT8oIrNuxpHU7BrgMetSwTKDjIrmrbUBJ8uQMDqavQ3I9eaXMVym6ZQTil8wdqyors/xZNTC5Q9Gp3JaLxkx3qOa42rnNUJLkp0xzWPq2rmKJiCQW+VPqaLgat/rSW0ZyTnHbmuM1vxfcMDHB8inOWPYCqOsXskt00SOQgQKff1rlr8F1lI6Zx17VaZmyzqmuTl/s8Fw63VxgEk/d9fwH866jQrqHTrWz81t0qoZCpPzE4OAT265/GvO7OIG8EsqscHJJPJ9BWjqN4XhJifDMPmYfyq7iLfiPxFe3d5Ji4Ty/u4BOPfH+NYp1G8RMwO8cfdgcZ/Ks2CGWSXL5ZRyc859q1IdPuZcK0exO+48Y+laRaMncztb1a41KAWV3bwXcH8W/5mx9a8q8YeGIoGa505GVed8Tc4+hr3JfD8zxMsCFVP8TCsnUvB8hibzjlehLLniqshJs+b+UYgggikLZHA5r0Txr4JNoDc24IUknBB5FcBPGInKlSrD1qSyDnvU1k224U9Ki4zSB8SAj1prcUldHSKd0dZtwvzH61dtnDRAg9arzj5jxXQ9jz46MgjBPTqK2NKlJG09qx87HyPxq9ZuQ4KtwetODsxVo3R0tjc+RKrqcevvWmk4t7sSJ8qP8y/1FcyjtnOa07Cfzojbynn+A+hrqUjzJ0z1G6jDKB8uFORhCP5CobmTbEVDEj3fP8AM0TkM3/LIDHPQVWOwjBZmPT73FfYxPKnuRzOpZRg8DuetVLuVfPXbkADABq3KBFG5YIVjGcdsVzzzrNdCRXYhD8wzwK48dU5YWHCNyzqVyfkhyABliPrWH4g1AQaVNI5AYKQD7065fDvNJ1fkAVyfji8JgjtgepzjNeFVqcsWzsw1D2lRI5UtucsTlmOSaRmUDHempjPNOIXGd2a8WTufWxVhhJIwUrT8N6Y+pajHbqDgnJwOgrPVDtJJ47V6V8MtIb7KLxxjzDwPUVEpWRSVzr/AA5pMNtEkUbKFAx93OK6+3tIyoGEB/2TiotMhEVuF8oLiryEY5TH0rkcrmyiW7YeWuBwB61I0qg9ee+Kz5LnaMAniqF3qSISWbFLmK5bm1LOgBOcZqAXKLxmuSvPEdqj7Uk3t2ABJP4CoRqOrXIzBpd0ynoduP50uYtQOsuLlSOGxWfPPlSGOT2Ga56V/EPJOkXOPwNVJNQvoc/abO4ix3ZDilzMOQ33kw/oKFZD1ArEt9Sjl6vmr8EoI+9wafMw5DagZTg+ner1sww3PWsa3lKYz92rscoKkqafOQ6Zs27rHFxwcVu2N0wQA8jGK5KKYkBD9M1q2lyQ20dM0nIajY621nIA9f5Vchuf3gIc5FYNpMSBWlC6bOCA1Tcuxsw3TE7eVHrUyz4VgW96z7ZGCnJOWqWUbUzRcLCy3e0EAk56VgardlpAN2RGcj3NWb5mBLZPTisG7uNzO3XmhSJcSCWZ18x2Y7mGBWROASqr07n1qzdTO1UnnUHHpVKZHswW3ZyTnGe9TSQIqhTjHoKpPO5OVyB7VNaiR2yAzZo57h7M0LOOKNlwgJrbsYM4baM9uKyrWObICqM9ua0bWe9ib5rR2XPVRzRzMfIjetozgL+lPnso5+GTdjpk8VXgn3AFsqT2brV+CZRwRnPpTVRkuByGv6J50T+eqmPkYIr59+Jvhc6ZfGeJf3T5IwOntX1lcpHKm1VGffmuF8f+F01XSZ4zF8+0lSq5wa3hUvuZuB8lFMN1oCKB1zVrV7d7W+lgkUhkYgj6VQLGtkZtGvpr7ogvpU84HWs7S5cOU9a0ZeUroi7o4akbSK0i5HvSQStCw9KeRUUgpJ2C10b9lcLMg6CtCBAWyMDFcnbTvC2a27a8coCPrit4TTOOrSa2PXTIijadgyOM5wf5VQuDHIVwY2I7f5zV2e4cEERo5A/vdaqPf3ITEmmae53bvkQqAMfzr7W9keC43KN2x8kgMQHPIFZ1zGLe1YRqC0h257/Wrl/cxSupihWBdgyinIB71mXUxMyopyqDP4mvFxdTnmawVkULgbUYE8AHrXn3iOczagQTnA6eld3q03lwM3civOr5w1xI5O4lq8jFS0PYy2HvORFGSD0p0oLDOc49qXBfHIUeppGAToxPtXnHuIkso2ubmKADO5gK928K2EUVrDGFxtUAEV5H4Gsxc64r7crGN1e2aMAikgYwvSuWs+htTVzdtmTYQG5Wm3Fxs74FVbRvkJPemXcmEOetYXN7FfU9QCA7SST0FZYsbjUJAZ5Gwf8Alkh5P1NTDdcTiOPls8n0ro9NjtrSMAsA3djSKsRaJ4bijIxHHCPYc109joMEmE5b3xWXJrllZKWdlO3rSQfEnSbV9wZDjoKtITub8vhUAbo8qPY4NYmq6TeQcN+9QdRIM5/Gr9t8VdHuAE3Rjtyea0o/EelamoUshye3er5UTdnmGpaVaTyMFgFvN2Q8fkay1tri1m2OpwK9L1zTbe4Vmjwfp2rmLq3OTFcDJXo3qKhxKTM6ByygZqxHIVPSofJCMRzxQzcdTUlGnayBweORWpZOoJNczFOyyBhkVr2MxfDbu9Sx2Ov09lMa+veuhsolADBK5vSckKOK7LSYC5Vc+lOJLJ44i0Y+U/lUF1CQDXRrbfJtKjFZup2oCk4NU1YlO5yl7wpHJNc3qDBN2fxrpNTHlg7R+tchq043EZ5NY6mljOu7onIHT6VnSzhclzii+uEjUs52jFYai+1a58u1BjizgyMP5VSTEzSOq28PV19s1csdYml5trG4n/3Iiau6B4YsLQiW5UO/d5ec11dvrGkaem1mjUDHfAFaRiQ2Ydrfa0ACuhXwX18urkfiUQt5d7aXNqfWRCorbj+I+hxMEEkR+gq1H438O6kDDMkOG4O8Aj8qpwXcV/IzrTVLKcAxyg5981cilAbeGJ/GsnXPDOj3ym88P3IsrjqFU5Rj7r2/CsDTtYvLG9bT9VjMc6ds8MPUH0rJ3RVkehR3O5cVXvVjaNs8kjkZNZVvfI4Bjarqzbo/c1SZm0fNnxw0dNO8WPLEqrHcoJBj17/rXnLg5r3L9pOxVbbTbxcb/MaMkDtjNeHNnNdsHeJzyVmPtX2TA1s5LKKwQSGzitmAvJErIOMV0QZx111HY+lRyDvUzJgdcmiOBmOTVtGCkVHVtuTV2wcugReTTZYQo5HNR20jW84YDI7ihaMJWaPbprzSnkRTJeoWX5Q0J6+57VnS/IruV3Ad8inXZIkZtq5B6KRn+VUnJ2hMFc9cnNfaVZOMGz5rQgunMcbybVZcc8Vz09+qSbCx3Hkj0roL/asHlkE7mAOD1Armdat0kJkhUhgOeMV4FSTbub0km7MzPEl8fJ2qccZ61ySI0jZyB7mrmsXG+Xy+uOKqxHHOM15VepzSPo8JSVOBLIqLGBuzVZmUDgU6d9x4GB7VF1IFczZ2o7/4YwfI9xj7xx+Ar1GxYKnua89+H0fladGD3Ga7y1B+XDcY6Vw1Ze8dNNaGopJXiqWpShQRnk095jGmAa57Wb0hj82T2qFqalo6nHYocHLHrWLqPidlJWJnZj2B6VzWtahJI3lISTnmtvwVo0Usnn3YLtwVB7V0U6dzOU+U5/xBrGpZVZXcFh8oPYVU8M6TqfiDV0s7ZbiUkF5PLxlEH3m5IHA9TXT/ABV0mWG8t7uOArAUC7h0zXNaTf3WmPI1sflmjKSKejL6GuuFKKepzTqSa0NPUfCuo23nXFrJctZxxLKJbiIwMys23hWPzYPXbn1rd0jTvEema9Lpsc/2tY0Ekc0edkqlQwIzzyD3rn73UPEt/ZpLe3kskGdqI7ZwP8OK9U+Buh3tyLjVboO6IgRT61c6dNrQzVWrHci0vxVc20ht71GVlOGDHmuiSSHUIhLEwJPIHetXxn4OtNQsTdRx+VcKDggYz9a8z06+uNF1A207fdOOT1+lcM4uB3UpKoro6a+tHA3jAx2NUyhKkjgiuh0+6tNQsWcMhkA5B6mstbcs5PAGcYrKRojMiQ+YR61rWSeXt+XNLFZp5hNaEFuFdUUZNQyjoNGbIQ9K7nRCdsfXmuQ0S32hfUV2mjqFYA/jmnHcTWh0S4KHk5rL1UYRiO4rShYdM1DfRrIhGM+latXRktzitSQSRMQucelcPqkGPMlcfQV6PcIIndWXGaw9SsI3ALAfKc81ikatnnS6Q9xm4uQSmfkTHWoru5tdJG0BfMA+6O1a/jTWFs9tnaD983y5xz+Aqr4R8JTajN9t1RW2dVRutbwp8zsjKc+VXZxniLxTqEdu9wqSCP8AhZuB+FcbYHxR4q1BrfTIprq42l/KjPzbR9TXrXxz0Ly/D9ubODbHFJlwB0FebeGPEel6Hol1Z3Okx3NxcTKXdkG/yx1VH6pn1HNdSoKO5ySrOWxgW9hrM1xJax+e16JPLW3VCWZweR9RzUlldaxa3cdvMZIpWAeM/wB4HpXQar44ingjgsdKXTLeK5W4jhj5HmbQC2TyM46Z5zS2kEmsavYPCod5LpSAFxjJ5HsPaiVODWhMas09TV8L+Mr3T5dlw7nsa7e7ng8S6csqSL9th+aNgOP90+xrjfiNoCafJ9rhUKCcMB/OsfwtrU9ncbA2UJ5ya5KkLHdF3R6PoOoFkwwwwOGrpLS5JPtXGWiAXnnwriOb5iB2NdFauVUdQPesdgaucb+0MBJ4XtpS3KXK8fUGvn9n55Fe5/Hq5VvDVvEDy1wD+QNeFMDurspP3TmnuDNzV/SrvYRC5+U9M1QABPNNOQa3jKzMJw5lY6hFVuT3qzHGNvSsPTbskLG2Bjity3cY9a64WZ5dWLixk0QKnis6VMHmtlwSM9KzblNrcCnJCpyPUb+VmbJYqOx6/wBaogs8oO/gfnUtwxd+oT/gVVoD+9DEjr3r6jGStGx4diTUAftESbSyqu78Sao63GsNjNKQFwpq5czA3cik/dIUenSsDxpdn+yJI0PzsK8ibtFsqknKaSPNrks0rORwTwaktwGUhj+FQxkliueKniEZb5RhgOueK8KTuz7CMbIjmO3gd6iXlgPWpZipanadF5t9EnYsKhmiPVPCcXl2sI/2RXa2cQKj1rmPD8eIo+ldpp0JZATXnTd2ddNaFC+LRqQq5OOK5+5sXmBMi5LdzXf/AGNWXLICfesrUrPDbgtEdCmcvp/hm3mYM6KxrqNJ8OeTgoMe1VLeUwMOCK27HVdpXB6VtGo0JwuXrzw/Df2X2O+DSIwzgdKwrf4U6E7FnlukBPA3dK6q31pfLw2Nx7kVbj1hWGFwT7AVqqr7mTpmJp/ws8Os6Pc311LGjAKmdv616ZpOnWWk6eljp0kEMOzgMDwf6muNOpBePMVT2+bJqVNUbAKkhj0Lnn8q0VYh0TqtV0fVbmy84Xdtsx0U4JFcTrnw5uNT1CS71GNGeQDZ5UioF/yK2rW7uLhgBNJIfY8D+gqxLOyx7JJcnuo/xqZSUkaQThscZF4KOgZlN/vB48oHdj3zTEtJPtBVMmIfxH1rppz5x+ZdkY6DHNUpdg+SMAVyzt0N1d7mfHBsIAwT7VqWFp8wZ85NJbxKpDMOa0LYndyMVJRp6bGsci10Vty/yjisK1QDBJ/HNbdrKOMdaaBm1bHCgk8mp2QnkmqlrKMAEdKteapBxWyMbamXqVp5qHHbnmsC7tWkRosEMK6iVwSe9Z97HuYOvDD9azZSPPNU8DQavcNfJOUvUOQrnA9sVtNFrFvaW1tKsRkjBUyoQC47bvcVvyRLKMoNr96zr+K6C4XLcfdPQ1vTlbYipHm3MzVNOu9W01rW7WMxygjJ615/c/BZpSbmK8ifdnajjkflXXXVzJbEgTzW5z0bLJ/9ao01iZAu5n2jo8T9a29p3MfZdjhNT+DOoXDRuur2IGMFfLxtx/Pmt3wN4JbwxL5lzKl3cKMJtGFU+v1rsItaEgBWWORCNu2QYNWIr6CTaZoAcdOc1DmgVN9Tk/E+gTavFJE4wrrjIFedah4B1HTD9oiLSxA/MuORXvgv7UIAgXI9azdVvIZAyqqDcDmsZSubrTQ828LkGAW0oC7fbmuk2qEGOmKd/YcMxM0OY3J6irA0+SKICTnHesWhnkfxz/5Blso/565/Q146V969m+PMeyxt8HI80fyNeNspBrro/CctTcYVA5plPJIqMk5rUyHoSrZU8it7SLpXTDE7hWBHzU8DmKQOpIxWsJWZhWpqaOvD5XAHWqt7Fxk06wl81FOeoqzcKrIc46V17o8r4ZWOuvbvTpZJktZLp3xyJFwB+PeqO8x85I9eabOsYYkcluegrN1aSSKAjkbyAPp3r18VUbepw8ib0Lkd1mIkkksSea53xbOGsX7N2NWo76PG0VkeJnBssjoWFefVn7rNsNStVRyvSnqSOhwaaQKUCvIe59KgYY961PDEBl1JMDODWWQc11PgSDdchiO9RJ6FxPTdBhbanYCu2sV+QKAB71z2kRqiLlcj2rpNLXe3tiuFnUjThgyvrxTJ7ESrnGa1LWENEqkdqtpaqq4wAPpSui7HFX+iOQWCdfSs1tNu4j8kbGvSvsgZM4yKibTkPJjzmmUeciC9Bx5b5FWoLTUXAOxgp7E4ruP7NhTkp1qaGzRR8qAD6VSEzk7PSrpyPnVT7c1s2WjpEuZ2LEdvWtyOyfdgJnPfFWodNZmDyHoegqris2UEjCfJAh/kKckIDb359eK25YERFwuKzL1gkbBcYpOZSiZOqygthcADgVRQFTkjin3j7mBHIPI9DUJkymM8CoG1YnEnzD0q7bMTjg9KyoiXPX2rWsQ2ARyKYGzZ8gMT271sWr7V471jWhycMcVs221gCACBQJmnbMSNoqyqsRjJ+lR2kPRvatqG0zGDnrWsUZt2ZjTA5wwqjKCCRniulmslCkmsbUbRkGUz6mpkhxZljCHp1q1FseLYwzuqu8bY4wadbMAQDU3LsU9T0eJ1dtgZT7fzrktR8MEuZLTMTZ6xvj9DXpkG1xg88VBeaYkvzKApNaqV0ZtWPHbnSNTgbkB/TPyn/CogNUhbDQzD8OPzFepSac6ONwGB2xRFYRZwUAz6cUnEfMeaRyahIwVo3z/uGtWy0y7lYF0JHuCK75dPiB+UY/CpltTt6Zx7VPIFzlYLAxKFZcVFexbVII4rqpYgAQVH5Vj6tbgqWXrStYDwT9oCDZosb4PEw5/OvDnIzmvo7422TXPg+6cKS0RD/QA185FB3FdNLY5au5A+c8UjDipW75qKQc1qYj4BnNS7abaDOan25OKtIzky9o1wVPlsa3GI8s4Irm7SCQzLtGOa3WJVMcV1U3oedXiua6OqcM9yysx4HequrojS2sTqMFWLVbgBa+cI5wD6ZqTVbIzX0cLybS8IZSO/PIr1KurPKlLlZxt3DsuSIxkZrP8AEbH7DtYdCMV2mp6Qkds0o/hFcV4mdDa4wc54rirQcYu524Woqk1Y51VYjgZpGJz6U+BsDFLKAGrynue8R5Oa7/4fwY2krXBxLumVfU16f4HjwnSs6uxpDc9C05BsUV0ulw52nNYGmLgA4rqNLHyr2HauJnVE3rVVVQD+FaMUG/iqFoqMBnqO9bNoADn1rM0GpAETaKclvv7VdSLcc9qtRQqBxwaaAyxZbmwQcfSp49OVSGC9K0wqgcnNSFDt+XrVpAULa3Ug70beTxjpUyxKowo6ValTG1k4Iqsd2x8jdk5BHYVVhlK8cANz2rltYMhgZUbBNdJcg/PuHSub1x1hhbJznmiwJnOR7oYVt97OU4yTmpIoJ3YCNSc9T2FLp6rLMXf7ue9dJaxps+RcCnYGzHhtGjOXOT1Na1ig2A4p88AJ4FTQRqkZB4AHWiwkNedUfJGMYrT067XGMnBrmdSuBFIeeD0qKz1TDrhgKBnqmlzDOGIINbMd0FwucCvOdN1c7lbqMc84raj1ZtuSwNWpWMpRuzrJrhGGC9UJplYkE1hHVCf4v1qE6hyH8zIzz7USlcajY0byA7N8fXPSqIUg9eavwXKTxArjFJPb+YNyj8qzLJrE8YPar8RB6isuyYqxU9a0I2bt92tIkMkkgVz0FQPajqOtX0xj8KUAN2qyTMNu2D1OKQR8ZFamwKOlROoyeKBXMqZAQcis2/hVkLAda3ZI164zVC+iHlnFZSKR5X4+sBcaPfQEAh4mAH4V8l3IMVw6nsSK+1fEttuifPQjFfHfi+0a08Q38DDaEnb+db0XoYVlqYznd2qFhzUhBx1qMjmtzBlmzX5Txmr8EO45NV7BQY+a04FAUGtoK5x1Z2J4kCrngUNlj1qORh0yaYJNo4OT6Vsjjlds7eyl/wBKkwobmtHU2DXFhKeCI2HI96x7dy13Iwi8tc9BzV69mJltF4+VWr1L3Z5eIjZsk1VmOnyEgdMYryjXpWcbT/f4r07UpSdPlBIHy15Xqb7pDn+8a5cY7ROvKY+8ygoOaeSC3NNxnpRjua8g+iJ7FQbpc+teq+DFCopFeV6b/wAfaV6v4ROI149Kyq7Fw3O/sSFwc10VgQoBPQ1y1m+SMV0OnOWCqK4mdUTqNP5Ud62rboMVgabkd+DW5Znc23PvUGhpJu6g8VahZicMMCoISNuKtIRlR600A9AN5T15qyitnPao4xiQHFTEjoCRjtWqEIQN2CPwqlOPLBQHqeKsyHuGqrcFXA3ckUAZ+osBFyfY1574suyDtB/iwK7vVf8AUNivKvGErC7TJ43cU0M0NPkBC+ldPaXCCNcEVwtjcbFHPFbFre/LjNNgzqpLmEIMsN2Kyr3VPJjOSMHpXOa3rtrp9u0t1cJEo7s1eVeJPiS0kzRaZA8gzjzJOAfoKLNi2PU9S1NJDzKMisxb/wCfCnj1BryeLxRr0r75Ioyp5OFPSuk8P6+LlxDMjRSHseh+lPlY1JHrukantjXJyMVrrqgI4avN7e+aNQVbNadrqJIyTik0M7d9SIXrmqcetbSY2bHPrXGa94ktdMtGkuJto7Ack/QV57dfEsfa8JZz+XnqWGaVmwTXU+mdF1hSoXcOeOtdVY3CvGMsDXzp4I8aWuo4WGfbJ3R+CK9T0bWCqrmTNRdrcppdDtrkhX3Jx3qzDJlQynrXPR6qkuQT261btbkFcBunvVxZm0bsdwA+CCT3q7G6sMqRXOeZ5nAdlYehq5aTYAV5MkfrWilchxNctknPPpzUcgzTInDDrTmYCqIIirBTzmqtzGChJNWwc8mopwCOlZyKOO8Qw5hfrXyH8YbbyPG18MYDkNj1yK+xfEKER4Ck54+lfKHx5gEfjLeR9+IVpR3M6p5oM5zTT16CpXG0n0qLqa6TmZoWHzADFaTttQL6Cs/S8Bl3cZ6VsiGN8HFdNNaHm13ZlHDv0qzBb56gZFWRFGvYfhS7RniteU53M6oRbNzcYJqnfSZv0UHAjjAB+taMit26E9Kyb6Mfb5nUk8BVUfTmu2LOPEL3mOu5t1s4yGGDurzW+I81sHIzxXeSLPGjlk+Ug5BHWuHvowztgY5PFcuLd0dmWJRkymozTmUAUu3HSkIwQeorzWe2TaepW5Rj616l4VkAhXHtXmi4ARxivQPDMuLdDWNXYuG53lnLhhmul0qT5kI61xVrN845rq9Hk4XNckkdMdzsLWXpituxYcNXL2snQ1uWM3yjmszY343zjFWo2Jx7VmwS/KCatxyDIZevce1NCNKKU4zTZrlUALOAMd6pmfGcHFQTzxnBkGe2K0TAtveowyjA1XkuCRgEZqqoVeI1xntTZjtXPGaLgR6hKBGwJ68V5b47Qkkx9V5Feg30xY4xzXJ6raG6dx68Zqkx2OGstTXZgtyOCPSrjasqwttOGxxVfVvCczyNJA7xt/eHesk+G9QLYN6+PcVQ7ENzpDatP51/cM5J4UngVZt/B2m/eaNSOgxV7T/D97uX/TGI+lbtlpkyDZLIW96adiGjGHh/T4YfkjBwO9ZV9pUaN5kK7XU5FehQ2MGzay5P1pp0KKVtw/UU+cnlOHtZJDH8wJYVftWkc8fLXSDw8u4/Lg98VNaaPHFKAV59zUt3KOOv9FW8YtP85PqK5zVPBSOxZPk9AK9hm0RT80bYrC1TT7tCwRd36UKVgsmeYW/h25sXWWMsrIcgqcGvSPCur3K2qC4b5wME+tYd1BqZfZ9lfFavh7QtRuZU8yJo0zzk1L941jZHfaJeS31wkMQJJ6+1deFeGMAgYHpVbw1o0GnWirGo3kct3NbEkJCc0rWJbuzLF46vneQPTFWbfUEZ8YOT61n6lGUfpj0NUFndHytJuw7JnbWd2cAFuKuiXcev61xlnqsYlVJH2sfat63uQQMHP0NWpmUom4pyMCo27iqkFypIXPNTNJkGk2TYytbUeSeM18pftFWxHiC2mAxmMj9a+r9TOYWz6V8s/tKZTV7XB6qa0pfEZ1djxxickHmkHqKTGWzTgK7EjkbLlgTwSelbEEhA5rGsTk4FaSOQM1003oefXV2XvMzS575qojk96kB961ucriegIAAwIzz3FUyka6vcIyFUba6n04q0N29vTPNQ6hldQQ7CC0Knnvya6qDujlxytNjNVVBYv8ufQ15prEXl3cgHrkV6PqEjfZHDn5e9cR4jVTMjr3XFTi43gPLJtT1MaONHj560sVk0ikjpT4oWxkVr6Uq7NpHSvEk7H0y1RixxMkhib8K7Lw05FuBu9KwtQtSs3mgYANanhxmBCjoTUN3RS0Z21k4LKc11WkzYA5ri7R8MOa6XTJeFwa5pI3gzs7Sc7RzWxYS9MniuXsZTxzxWzay4xg8VizdHTxTEDGcip47g5x3rFt5+RzkVZSTJ4BoQ7GoJy3Wo5J1U8HmqMl1sGOhqNJCx3Mxx6VaA00lbdv3c02eTcMZzVRbgDr0qCW53Z2timhEGoSMhLZ5FYsszE/L1qxr9x9nXzGycisH+0g4yAB61VmPmRfnl+XFU+rZ2j8qYl15uXwAtPWZccKc+tArlq3KKucdacX5yoxn9KoyTsw+Qgj+VTwOWwpPzEAc0ILk6MxOO9XreYgYI4qtbwNuJLDjvWjbWnmjbyPcUCI1uD5mAvy+tOPzvuHWra2DxnG0n+tSpZnfxn8qBKxAhOzDdajeNH+8g/GtZLMt2P5VLLYYTnBNOwXMaGygk/wCWa5+lbWkaagZSV6HtS2loqsC2MDtWzZAKeAMUIOYvxIioABwKkOCMYp0Zjx2pW2g5yKY7mTq1mZYzt61yd8Ht3IYH6130oBXr1rntes1eNiB171EolxZzVvcATAtziuj066QgAsAfc1x0zmGUo/GDVjTdSiknMUcis69R6VC0Kep6DbSrwwINWvOB71zVneuoXtWktzvTOarmM2iXU5QImPtXy3+0hN5mtQLx8oPSvo/U7j902T2r5Y+O12J/E5jVs7BW9DVnNW0R5zil7UYpa7TjLGn/AOs2561qFGA6cVi277Jlb3retpN65IzxW9M46+9yPBFSLn0qVlBP3aUDnpitEjl5jvp0InfHrVfUG2zWr/eIRlx7ZrRvoiJpMZwKxNRlxcW4PYMa6MLLQyzGFpC6hl7Vxt4xXIawoNpwDkHPSuqumLwn5eB6Vh3xja3dT/EK3rLmiceEfLIybC286IEcmtO30+YY2r+lZ+gXkMU/kSMAQe9dvazWwhBBU181WbjJn2FJKUTmb6BxCVdecVDomQwHTBrq7z7JLEehOK5ixAS9kVem7iojK45xsdHZOcjNdJpz/ItctbkjFdBpsnAB6UpIqB1Ony469RWzbzfLXOWjYwc1q20pJA7VhI6UbNrOVkrUjlO3PTisO3jMjAg4rRllCQ4J5pJDuPebe/J60stwqrjNZguBy+eKzL/Uf3hUGtlEzczWn1IIDljgflUEOpA5c8CsGScysEJ68mpFWSRhGBha05UZuTL2qXhu1wiM2OgFMs9LlnxuUjI9Ku2gt7aMeY4z6VY/teFAFiVQfWnYauyS30QJEAyggCrNtolsw3OcYPIBrOk1W4fK7hg+lEV3OxIH45NLlLszdXQdNClllA780xtP06P+MGqMUkjAAnBx61J5YLEHjFHsykX7OLTlcAyd+9b2m22nyE+VIhP1rlRbo3BPcd+1W4rQwsWjLAr79qpU0No7BtNRwCJKWPS1JGSPyrn7O71CAfJIXBPAbtWh/bN/tx5KA+tVyMjlZvxafFt2jFRT6UWOFIAFc62s6iz5LYA/uin/ANrX4G/zPzpcgcpsPYtGCCn44qJ0eJcAc/SqVvr90v8ArVDCtCDWrWUYkUA1DiDjYiS6ZB8yH3zQNRCuA44NPnWC4f8Acyg57ZrHvra5hJZhx270rC2N1rxSOMY9qpXkqupT171z39ovFJjt6dKsi9SUAqcfXvScQUjH8SWZCmZRyPSsfT0j87zVADnqa6u8CSxEMMgiuSx5F60XI54rKSNlLQ6O1dyPvHNadrKyIdxzWHZORjNX2lwuQazBkWs3BWF2JwADXyj8Rbr7X4pupOwbAr6P8V3pi024ctjCHFfLWtTG41SeX+85ruw0epxYiRT60jGn0xq6jkGZIPFa2mzAoOayDU9nJtkwTVwdmZVYcyOhWTJwKlyKo28mSKtKwJrqizzZqx6xqEHzyHGK5HXYj9tgA4yCQa7/AFKHLPiuI8URmO5s3TqCwP0pYSWhtmMdbmcxZAVYkkVg3bsHfPXPSte5k3zrukVFPBZjwKx9UO1yeCD0Irsm9DzKEfeOW1Lct4WBwT6U6HV7+FdqzsR70aqTvBI696oV41SKctT6ahJ8qNZPEF+OGfNbPhy5NyxlfqTXIYrpfBzgMVPrWMopLQ2uzt4wODWxp7cBe9ZEPKitKwfa4z0rCRpE6OzfgCte17ViW56EfhWvYP2NYSOiJu6eSuDS6s+IzjPSm2BBWi/BcfKMjPNOI5bGc7FYSM8mshlJZmbqTmuge2JjJwT7YrIvYHGcD8K1TMbFMSKhyxxUc2reVwvFUNSleKMu+eBXJX+sfv8AG7Aq0CR2jasH5ZyTUkV+rsrZPUCuBh1VWYYPOfzrStbyeSX9zE7Z9BVJGqZ38V8iyiNj/F1qzHqkKIzZw2ciuQY6q5Ux2Um7HcVNFpmvXDELZsC3q2KpRZokdiutRIu6NwxPY05NfWRPmG0qeoNc1b+E9f2B5GRFz03ZNaNr4S1HdtknAB60WZcadzoo9Zjd3ONuce4rWj1WEoMsDkDJrmIPB93vXy7vaFGGBOQavP4V1FbcmKfke1VZmqoHSW+s2CuN8/APY1ovq2k3CBYpf3h9q4O38J6vNGXZlkUehwaryaBrFvKpgtXQ54Jbg07vsV9WT6neNJDywBP4VC1zGDgMv0xXOppniBYRujJP1rNvRrNq5320mR7VLb7GboNHaJOjsACD9OlEhUn5WA+hrzy48QXMChJY3jHfIxU1l4sh6FgB3JbrUXM5QaO4S8kt5NyufqK0rXWEk+S5bKkfjXCf29HIm9CPqDVG41d1bercZ55pGTVzudcgQp5sCg9xWRHM0Zzzzz9Kraf4gjkhCykkY65pXu0lbcmGGetSzFqxswS+YAysCCORWTq0S/bUdRyaS0kKz8EhT29KsX8fmNG+e9RJFxdi3aIfKBI5oumOzaKuW8JW35rOvMhj8wArG2pozi/iNOLfw/PzgkYr50lGZGOc5Ne3fGC8EelmINnca8Sx3r0KCtE87ES94YRTGqQ0w1uc5G1MU4bPpUhphFBRrWUgKA1o25G08ZzWFYSY+U1r279K6KbOCtGzPoHU4sO4xXB+Loj5luQdvzFc16RqseJTxXEeM7cPp7Opw6SA1ng5HRj4XRyF9pSm0L+cobPLMeKwdS3GFECglRyR3rqCwe3aNzkbcYrnrtPkKL+denNXR4lGXvanI6pnI9qo1oaoCC2exrPwa8ip8R9HQ+FBmtzwk+Lsr61iYrQ8PyeXqC4PWsnsbo9ItScD3rQh4wazbEhlU+1aURDLgVySNYm7aPmNa0rSXDDnmsSzcquDWjA/IINZtG8WdbpzhlFaIj3gN7jisHTLjlRXR2rBkBFSinsPMIxiqN1ZA5ygrYiwwp80KmPjmrJOM1DRIp42VlzntXM3/gi2dt6x8ivR/KYSMDkioLqL92SKuMrCsjziHwjbwEN5S5B7nNdDo1rb2pwY0z/u1auY5AxwCcmoFVjJgZBHFbxZpFGjLOhcsoAA4FS2t6ERnLd8CsiVJFbjkD3qmZnCAOxGWq+Y2jY7Kw1FZZFTeNq8mtKGVZsMMbc5PvXn9teeWXKNjcK2dK1baFye9FzS56DocUElwizYAJ5+ldDbJaCaSOIAxnP3vSvPLLWQs4O7g8da1l11VdyrDp61rGSRLcuh2sNvZxqYUY8j73anT6XbThG8xcKOO1cdFraoE/efMeTzU8niNN4bPAFVzIi8zrBZw/ZwcAgVn3emQTfPgE96xofEalcK/H8qmTXEO4I2altFJzINQ0HS5AfOtkkB9RXJ638PtAu0eS3ElrN/sN8v5V1l1fbowOpNUXnDAnPQ1jKw35nl2q+F9V0m3aWFvtUSnkKOcfSuNvtcIm+znerg8gjFe95LZHUGqsPhPR7u9N3c2cTP/uDms5IwloeTaJdT3CfKrY9xW3Y3ckc/kur8mvUZfD9iCBDboiDsBVWXw7aecHWIEj1FZtGLMLToSUD5yD2NacMIZlQg9c1pjT1iXGwj0p0VsFcHGQKm40iWRQkGPQVzWqyhc81v6lIVhPPFcfq06gsSalLUqT0PI/jFel50tga82YHFdN8QLxrvX5ecqpwBXNGvRpq0TyqrvIZ2ptPNMNaGVxjd6Yw4qRhTGqS0xqMUYEVrWsmVGDWOavac/wDDWkGZVY3R9W6vGA+cVxnimLdp9yMfw5rv9Yj5zXI6/BvtZwB1Q1jhZWZ04yN4nmNwViVSucnrWXdAtuOMD+ddDNp+597NlfQVg6uSJjGCMLxXs3vE+aStKxyetqNxwOKyiK29aj/d571jYzXlVl7x9Bhn7hGalsn8u7jf0NIUNRnIb8axsdKZ6ZosweFe9bEDDdjvXI+GLndbpzzXUWzjcDXLNWNoM14H7Veifb3rMhbP1qyHI61kbI37G4+ZSDXUaVc7hyeK4Wzm5FdFpFzyeeKm1jS9zq7eXk4PFXY5AVxWLayjPsauo/pRcCzOABuAFULzJjyOlWt+5SKqzNwRTAyrkDqPxqqUBYHFX7xPl3CqjcxgelWmIRVUAg96glt4X4K04sQaa8nPFUpDUrFO701f+WTYOOlVfss8TAjPHer8zvj7xFV2nkXvWimaKoPiluV6569KupcS7SuWyT3NUPt4QcrmojqgDcqfyp8yLU0b0UkjY5zmpy3O3OPWsG31WNx3x7VK+pxDoCafMivaI2Q7qvyk/SrdlO8bhmfgds1zp1dGIAUgCrMOpK2MITS5kDqI6lLiWZ8pkk9ParMVvI2N7fWsay1ByAqqFrYtJ2ZMlsmk5oxlMvxWqYG6tK0VVAUCs2By5ArW05CXyelZuVzJtstrDnnFSC3wvI61MjgdBSSNkewqbisZd5GoY54qnOyqp4FWb5stknArC1K88tG+YdO9JlGdr11g7c1xfiS9EFhPOxxhTWpf3TTSsxavPPivqn2XRvs6thpTVQV2Z1JWR5fqFwbi/llJzuYmoWBIqCF881ZjORnFeitjyZvUgPHakPSrDrmoMYzTITIz+tRtnFSsPSo2pM0TIjU1kxWUHPeojRE22QH3oW45bH2lq0eQeK5jUogwYHoRiux1JAVNcvqKYzxXLQlZnbXjeJ5ffIYJHQ5YBiK5TWFBnZhxmu38RRMJ5lReS571x+rRGLKsQTjIr3oO8D5erHlqnL6ipdGUYz7nFYoFbt8vyMSetYI+8RXn1tz1sM/dHY9ajkSpl6UOMrWJ1Jmn4WudkpiY/Su0tJOnNecWchgulfPeu40y4EkStntXPVRtCR0ttIeMGrobd1rItZMgYNaKN8vPWuZnRFllHKN1rYsLghgQa55pTnFX7CU5HtSLudtYXG9MZrVglDRjBrlLGf0NbOnzZyM0rFJmykmOtRSHJzUQl9acfmHFAyNwGBFVJIiCR2q4ykGjAJwRTuIzmtyecZqM2zE1rCEUv2bjOKAsYzWoI5HNQS2We3Wt422B05pBb8jPrRcLHPLpgPXIFOOmp12ZBroHgDcACnrb8DC0cwWOc/stFXIX9KUaZgZ29a6X7MMdKPs5xytHMFjno9LyORU8WmlDwK3lt+OFNWba1DdVouGplWVqegH1rdtLcqoVRk1JDaBTnAxWhbpxngGi4WFtbYooyK1LchVqCEcDPSnsdpoCxcWRcUyabjAqn5nfpVee4wp7elAEGpzhQWzXF65ffMVBFbWu3gSI85PpXC3MxlmJPTNAMe7Ark14v8VtSN3q/wBnRgUh4616p4l1FNO0iWZm2kKcV4Hqkz3V1LO5yXYnNdFGN9TlrTtoRWzcVegbC4NZkBw+31rRhHFdkTz6hPioZF5JFShxnFIwBqjG5VYH0qNhU7jFRMKRpFkB9Kb0Ip7DFRt0pGp9x3ozGfpXMakuCwHrXTz8ofpXOaoMOa8+m7M9OrHQ4bxHEEud4BIcZ/GuH8Txgxh1HIOK9C8SKxhDAcq3X61wmsRlkkVjgEGvew8rwsfL42PLUucPf5wQQa59j85+tdFfjAZc5OMVz0ylZG+tc1bc7sNsOU0/rUa1IOlYHSNYcVv+Hbv5fKY8isKnW8zQTLIvbrUyjdFRlZnotjJjvWpA+QBmuX0m7EsSkMCCK6C1lyBxXFJWZ1xdy1Iu5SQeRVjTpeAKrs2wg1HBL5cuexNKxZ1dlJgDmti0lxg+tc1YzAqDW1ayZQe1SWmbySAqOeatQtjmsWGX36VftZsikWaJxnNNGC1N3bhigHBoAlUVYQcYNQwk59qnGQpagCUQblGOtPFoCue9PtWLRhuhq9CoYc0DMaWJ0b7mRVmztmcBjwD7VtRW8cgIcd+OKsQ20ajGKdgZjCywSQDgUNZscfK1dB5C7ehwRT1gXAAJosK5gR2h9OasRWZHbFbDwp9KjcbDggUrAZ/kbOtOjU7hVlyNpzUI4Gc8+lICYHGMUySXHWmNKVX3qCaQFc96aASaTOcfzqndTYTIPJpZJOvNY+qXHlhmLYOKYmYviO6ydgbnpWIxEUZdvTNPupmuLliTnBrI8Q3ggtXUNlsdqaRDdjhPiZromnGnRnIAy2DXAyAEYrU8UoxvvtRJO881n7QyZruppJHn1H71ymw2uK0bZsr161RmHtViybK471rExnqi1sOc0p4px6UCrOYicDGagbirTAH3qFx7UGkWV5APSoWFTuCBUJqTZH29KTtIrB1gHJNb7qSDWTqsWVNeWtGexJXRxOvKWtZeT0zXn+qBixwc16bqMG9WU9CMVw1/Cqkjb8w4PFe1g5aHz2Yw6nnuqBRMdo69a5q6UrOwPrXXeIIjFc9ODyDiuVvRi5b3oxC1DCPQrinr0pDSrXMdjHZ4prGnUxsUAi/pF6YJQjH5e1drpt0HUAGvOe9bmi3zR4DEkVjUhc3pytod+km9c5prHDVnWV0HQcjFXd4bBrnasdFzX02bkc8elbltNXJW0uxsetbdhPkCpaKizordznr1rRs2AzWJbSVpWsmR1qTRG7E2cVKcGs23lIHJ4q7HIDg5pDJlcqcZq2jgqFPIxVFyGGAaElKAZNAG1b42ACrkEgThj1rLtJQVB3ZBq2rBuKEx3NSCZc8GraOCOWOTWJFL5bYqdbrsWp3E9TbWRGGw/hUqsuBmsVbgDDVKbpTna3Wi4WNVyuR1qOYhh9KorcnaAGBpXuOnFJtALKwOdvFQplTyabJOAcdTUby8ZqLgSPJjOapzSHGO1Bl3NyeKguZVHPbtVICvcSFcnNcz4hvGCkbuvGK3L2dREx71xuqTebPyxOKtENlSWcRwsx+8ay5bN7u1lmdcnBC1Lcu083lp69q37K0Asdh6gf0p2IPHtZ0h71zbRY8zJ2g9z6VyEKSRSNBKpV0JBB7V6n4htms9Q85MrtbcD6VnfEvw7vt4fE9ghMcigXIUdDj71ddGV9Dirqx5zcIRk02zbEm096uTpuTI9KoD5Jhn1roOe90a4XK7hzTSop8H+rAoYHOa0WxzvRkZXFMkXjNS9aYwyKLDTKso4qBgO9W5F4qtIOM1DRtFn3M8XXis7ULclDxW+8fFVriDKnivMtY9jmODv7YgniuI8RWmyeRkxzzXqep24BbiuJ8S2uXDY6jFd2FnZnn4ympRPHvE8Lbg7E46Vx+ooN4YHkmvRvGNqfszkkkjvXnmoKcBfeuuvrqefhdNCkaFpccUAVyncxaaRT8e9NIoAZU9i2GxUJFLAdsoNJopHRWV00RAJ4+tbdpeBhjIrmoPmTFTwyvE4HasHE3TOtjkBAatGxnII54zXN2V2GUAmtO0n5AJrNo1UkdhaTggc1r2sg29a5K0uMEc8Vt2U+QOeKyaLTN+KTBXHIq7HIuc5rGglBUc9DVrzhjg0jS5sq4PIoz24rOhuCE69KlWcsuc80rDNazlEYIPSryP8wYGsCKbOcnrVq3uTyM8CgDc8xT8xppcZyKz4LncwUn8KlEnakwLZkbOM8URyPvzuqibj5gCfpT45ijc96kZrJKFIy1OafIxWY1x82RyakScYweKkC4G+bNLJJxzVJrgA8GmG43EgmgCaSUDkGq08hwc4qJ5dpOTWde3WAecVSEyvrN0qRnaefrXLXsmFyDy1Xb+4DyFs8Cs3BmmwRnPQVujFstaPa7nEhFdXBAvkdskVn6XAEiXcMED0rZtYsgD2ouUkcH4zsBtLgDNWvA7Q3ukyaZeRiSFwY2U91Nb/iWxWWM/KDng1x2hTNYawYwSNx4+taUpWkc+IhdHnvjvwxP4b1qaxdSYD89u/wDeQ9PxrjLxNsuRX0p8U9HPiDwn9phjD3dkvmJgclcfMK+dtQhOCcV3nnLQnsmHlLU7DIzVPTTmEDNXuCK0jsYT3IDTO9SyDFMNDEhkgBXrVWVcdKtkVDKKlm0WfeZWoZE+UirDCo3715jPZMDVo+tcX4ih/dZI6Gu+1NMqTXH6/Hugk+ma1pOzMa0bxPKfFkQNtIG9D2ryu+T7wzyDXsHiqPKke1eUaxH5d1Kue9elN3jc8en7s2jJ2jHSm45qbHFROMGuU7ExKQ9afikIoGMPSmngg+lOI9Kaw4oKTNWwbIU1fZAy5ArJ0xuduelbUI+XBrCWjNk7ogjZ0b5SRWlZ3RyMnmqcsZHIFRru7HBpbjudVZ3fTnNbtjdg9+tcNbzsBg9R71qWV2wxz096mUS4yO7tLgbvvVeScGuQs73puNa9vdBgPmrJxsbKRuxynHWporg5wTWRFcg8EjNPabioKubKz7SeafHcNuOT1rHiueMk08XQJ64oHc6K2uQGwT05FXpLgMowcVykdzzjfz61Mt+y8Mc4osFzoRJk96Vrg7cE8CsO11BWU5OKc15wcsMUrD5jdhuRt55NPNwM9a5kX/zcMRUsd9uUZbkVPKO5uyXGO9N+08ZJrI+0FhndxUbXfOAePejlFzGvPcjGQaxNSuicqDwahubwkMofrWdJLvc85Aq4xsRKQ6Vw3ermkWrSzh/yqlChkcACuq0S127TiqbElcv29uAg+Xp3q7Zrg5IqZIRswKeIjEmM5apNSjqEIlQkj5QK818SRG2vhOnGDmvWriHFpsPBxzXnvjC0zuIFVHczqK6NzwdfpdwGObBR0xj1zXhvxJ0J9E8SXdmV/cu3mQn1U16H8Pr4pLNaMfmic457Vq/FnQBrvhkX1umbuyBYYHLJ3FejTldHk1I2Z89aedsrIenUVogjFZpUx3nXHatJRlK2gc1REUjdsUwnipHU1A1UShRimSgUEnOaa7ZOalmiP//Z";
const bossFaceTexture = new THREE.TextureLoader().load(BOSS_FACE_DATA_URI);
bossFaceTexture.wrapS = THREE.ClampToEdgeWrapping;
bossFaceTexture.wrapT = THREE.ClampToEdgeWrapping;

/* Final boss (wave 15) face photo */
const FINALBOSS_FACE_DATA_URI = "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAUDBAQEAwUEBAQFBQUGBwwIBwcHBw8LCwkMEQ8SEhEPERETFhwXExQaFRERGCEYGh0dHx8fExciJCIeJBweHx7/2wBDAQUFBQcGBw4ICA4eFBEUHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eHh7/wAARCAGAAYADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwDtxQ33aBQ33a5wuR0UUUFJhS4NIKcTikwbCmtQWpM5GaQDl6VHL1qRelRydeaAHJjbTcLuzmo2kRO9U7u+jjH3hVJFGlKUCZzUQliCk7hXNajrSCIhX6Vz8niURuVaT9aqxLZ1mramlupYHvWdF4jgJ2syiuU1XWYp7Vv3gz9a4bUdXdLg7JD+dCiK57G2u2wkzvWlutbjaEkEHivEJNemIx5h/Ortv4kcxBGfoKpRC52N/wCIFS7wcdau3HiJDZR4I/OvKtW1JpJN6moYtZkMewscCnyjueiT+IF39qWPxGgA6V5nJqbFvvUn9ovjrRyjueqr4ijK9R+dVJPEEayZyK84XUXH8VNlvXboxo5Queow+K40nj5GPrWjd+IYWAlDDivFvtcmCdxyOlW7TVZjFtkY0uUOh7HZ+Lo5GRMjg112na9DPHsLDketfOtnqBjlDb+9b1n4kkikG2Q8e9JxJufQdnIjDcrA1biwX3N1rynwr4yQyKksn612suv25ZSsgwR60rDex0cyjqKjEg+4KqWmoQz2+4ODUAu083Iak0Bqq2KbK+RTIHWRcinEDdipsMYPu4oxTv48U/bxTAj7Ypr049cU16kCFutKtI3WlWhDJ4u1Tp1qCLtU6daoTH0UUUEsMUhWnZpCaSAYRikpzU2qQxelIx4xQTSE0jIQ0lLSUFIKU80lAoKRHJkdKWE5TninsBUZ45oGK0u04qtNcoz+XkDPeoL2cICc1x3iDWja7pFflTQBu63eG0UkNuFcnqWvCRDtb5vTNVLvxDHe2RDv8xHrXnWs6lLBdMUckZq0gbOovNdYMysefTNc3qeqs7EhsfjWLNeyTEyFjk1TmlJPLVViWaj6vMymME49aoTTsx3E5NVC+Oc00yE00gRI8zZzSC4YdqiJzTMmrSAsm5J6imeZ6CocmjNMCQNzmnh+OlRA0oNA7jy5JpRKw7ZqKigLku85zSvLuGAMVCTSZNILkyOy/wAVWIJWQ8nNUgTmpBkVNibmtaXDxSiVZCCO2a6e08RTNbgu2COOtcIJCO9SJO/TccUrFHsHh7xfIYxEyjHrmt6HWVMykPnPvXh9pfSQkYc1tWmtSAq285HvSsM+g9E1KORMMwFa3mI5yrZrwPTvFU0OPnNdf4f8X7yN7/rU2GeoJ97mpGJC9KxtN1NLqFJgw+atZX3rxzSsBGSc5xSEk9qkZTjJpjdKloCFsUsfJqOQ9afB0pIaLCcGpkNQjrUq0xD93tSjmmHtT0oJYtJj3paKSAaR70mKcaSqQxlNJooosRYBRSig0hiUHA6mkY8U1irJRcdwkYgZHT1rOvrxI1OJBVm7mEVqwrzjxTqrW7uik4qkFzV1PUxlsSCvO/Feoli43ZFVrvX2O4bv1rmNT1Bpiyk8GqUQuMm1GYNhWOKz57hpZfn5FMlk4xUDPzVpWFcfM5DlVPFRZLd6aW5oBpiHlMDOaacUMeKbTSGmKTiikpRTsVcMUEU6lNAMYM04UUUEiUlFIaBXHcetGPeo6dSDceBzT91R0oNFgsPzTh93PemCgmlYpC5Ympo5WXpmoQacpwc07DL8dzlck4q1ZalJE3ysax2bNSwkClyjueo+GPFbR28UTy4x6mvS/D+uQ3CL+/Un6183wTFGDc11fhXXvJuUUsRz61m0B9GGUSW+V5qLcDxmsfw9q0U9iuXHT1q8kqM+5TWbAmkX14pYRzUbSB2waliIBwKVxomHWpVqKpFoEONPSmjrSjrQSx1JkUpqNutVYVxxIozTF70tAXGUUGkzSAWkJpwAxzUTmpYC9ajkdIxyaC4AyTWHrd8I1JVqcQG69qcUcZG6vMfGN6jlmU9qs+KNWclvnrgtW1SWTMZYFa0QGXdXOZGwe9UJZSSaJnG8kGoGkJNaJAEjE1Hk0pOaTFMkQnmlBpCBnNHFADgaWmZx0oDGmguPpRTATTxTGmOpTRiigYlFFFA7DTSGpNopNooJIqdTtgpdooENoBp+0Um0UAANIxOadgUhUZoGANBbjNNIxR14PSgLj1bNSo2KgGB0p280BctJIcUQ3DxThlJyDUCyfLilDgHNQ0aI9C8MeKZYSsbuQuK9M8J67FdkAvmvneK5kyApxXWeD9dms7lAzjGec1m0B9FhUbDA0sZ+c1iaDqsF3YowcF8VrxMNu7vUWGXVqVagiZTHu71YTmMN3osIcOtKOtM3HNOUmixLHmo2608mmnrVEDV70tA70UAMNIKU0nelYoeB8pqGTABp7E4+WqN1I6ISaVgKOq3qwxv83OK888Sa0dh+b9a0/FWpBC434rzHxBqAcHa+acVYClrmpvKW+auclmZskmpZ5CzHJqtIRnArRARHJOaQj5qcKad2/pxVgFFO2n0o2t6UCsMPWipAhx0o20CIyKAKeVpMUDACnL1pBQpG6gaRLTeacOelKqnuKCrDMGjBqXYfSkK4607hYbRRSE4ouKwtFICCOKWi6HYKKQkDrQDRcLC0h60ZHrSE0XQmhDTacaaOtFxC80c0vHrRj3oCwmDRg06kzTLQKxQ5q5AX4dCaqptLYY4FT28u3gdKzaA77wX4hltsRyOcD3r2nw7ex3lmjBgSRXzLZTOsoI4Fen/DLXy03kPJ04HNQ0M9hRSAatxHMYFU7NjJFu65q1CCCQaQh5605ab3p6AmglimkPWnGmnrQQIO9FA70UANNNPWnGmnrSRRFPJ5ak1z2sakERlLVraxIY4vwry/xTqhR3UGqRRkeLb9XMvPavOdQuc1sa3qJkLjPWuXuHyaaQmhCSeaj+tPQjbTScnirSFewlKv3hSUdaXULkhYUm6lWPNTLbkiqkzSzZByelL5ZNXYrJzyBxU32JwOlZ8w/ZszPLIHFNMbVotbOD0pVtmpe0sP2LKCQMamjtwT0rThtGx0q7baaWIOOtT7VGkaDMqK046U57bAHFdLHpTbelNm03YuSKn2pr7FpHMtHgVXkTJravLbaTiqf2fNNVDJ0iksSntSvAMdK0oLBjViTTm20OoCpmB5YUECmBeelas1kUPNQi1OaFMHTM9lpyLgVdktj1qExHFaKRDgVtoLU/ysjIFPSP5quxQjyMnrSvqZuJkSKRTOc1oTQjdTY7UE0cxPKUgKeMVce021XkiKnFXGQ7WIyKQin4wKQiqQXIzxT42xSEcU3GDVMdy9BLjFbXhPUDZX+/pk1zaMcVftnA2sOoqGCPpTwTqwvbZQWzxXUxsfNINeGfDnxD5EyQlq9psLgXEKyDuKykgZe71LGcVEnSnGpWhLHnrTT1pTSHrVECDvRQO9FADJ3UH5RVe5nEcRbPNPIOM1g+I7vyYWwccUyjO8Rao5UjzBXlHim73SOd3NbPiPVSHI3V5/rN8ZJG5plGZqExL9aotyeadOxZwaRqtAxVAxihgoOBTAad1NNsjcQ9anhj3Y45pEiyRWlZ2/zjNZSlY2hTuNt7YkZxV62tcnleK0LO1yOlaVvZgHpXPKsd9PDlWzss7Rt4q++mp5efL5rUsbUALxWm9t+66Vzuudaw2hwtxYHdgLU9rpm7G5M1vzWw83OK0bG1UqPlqHWuHsUYMGlL/zzq7b6eqkAJXQx2yjtUyW6g5xUuoaRooyY7FQn3Kq3tqoT5l4rpzEoTpWXqUYKYpe1LdFWOG1SFQxAWqEduSeldJfWheTgU+z07OMrVKqYOiVdKsC6fOmTWmumIyHdHmtixtAigbavfZwE6U3VBUTgb7TC0hwnAqi2nFeqV6E1krEkrVO404EHC041SZUTgp7QBT8tZc8G0dK7i+09ucLWFfWEgBO01uqhhKic/FDlq0ILc+XgimrE0bHIrRsl3x9Kr2hl7Iy5rQbuFqzZWKl1ytahtw3UVds7YDBxS9oWqBj3FgmD8lYl/a7CcLiu7lt9wPFYep2fzfdq41DKdGxx0i4yO9RAGtK+tmErYHFUjGRnitoyOZ07MgYGkx61IwOaaeK2UibWEHFSxEjGD1qEmn79oFJsSZfsL2eyu0eKTbzXvPw18SrexLbyyhmAr57VfNx7V1XgLUJNO1qIlyFZgOtJoGfT8RKyKW+4afkG4H9z0qnZ3SXemwSIcnaM1dVQYge9ZS0JY84ppFSY4FNIpkDDxSZpXpKAILlxHGSa4Pxfc7kfaa67XbgRQHntXlvibUwd43Uy7HE+I7n99jJrkrt8yGtrXbgPPkVgTNkmqQxpIpjUmeacR2rRJD3RGAe1TQLk4PWhY81ZtovmAqJ2SCMbssW0DtjArYsbdi6jHNNsIMgVuWVsAynFcVSoelRpE9hbkDBFakFsewotIRnpWrbxCuKcz04QsPsrbCgkVfaJfLximwLgDFWNvFYNm1jHuLRmb5cVdsoNigNipTHlqmhjIovYOVD1jGOKAuDUqik4zRcLWIpcbSKyr+NsVryYIqrcIMDimDZhmDLcirlrBjGBVpIQW6VoWsC46U0ZtIIbfkYFWXt8r0qWOPGKmK8VRJntb9sCj7OpGCKvbOtN2cVN7Cvcxbq0jJxtFZt7psTqdq10c8WWqOSFSMYq4zYSppnneqaUyEkKKzoFEDbHHNeh6hYq6niuZ1XSyrGRVrVTMfZ6lOALIBtq/EqqmD1rNsFdZdpFahGFo5h2sSxoGWqGoQBuAK04BlaZPFuNNTZDhfc4+/svnPFZNxZsM8V3F1ZAgnFZN1ZcHitoVGc1SijiLiPacY5qu6mt7UrTZlsVlyx4FdkJXOGcbGe2aco45qwYxTCuDit1FGOw6BwlWba4aK6jkPQGqqjmrFugZjntSYH0P8AC/W4b2wSDLFwO9d7DuD7DXhfwe1DbfrFnvXu3Ta47ismriJvamtxTlpr9KRJG5zSUGigRyvi+Ui2bB7V4t4kun8x+a9d8bki2OD2rw3xI7ee/wAx60I0MG6mMjk5qmwyasNg5qF6tARsORUijJpnWpI1JNXew0WIUGKu2kWSDiiwhyBlc1r20AAHyiuSrUOyjSuWdPiOBxW7aR8isu3QgjtXQaYoyuRmvPnUPXpUrFu1jxWjAlRwoM9KtIuBxXPKZ2RgSpxxUqmo16CpYxUXLsOjUFqmVMUkeA1SihszY0jFROKsjHcVGV5ppksq4NO8oN1FT7PanRLyc07ksjigQHpVyKNVFIiipkHtVIi4uABSZqUgY6UxqdwsIOhqPvUi0hApMm2pFKvFViDmrRppAPahMtFSWPK9Kzb2JChQjk1sSiqk8YZskVaYnFHNpp4EhYCpXs+M46VsGIZ4FKsWTjFFxOJlQ22BTzb81qGEdhimmL2ouS4mRcW4C9Ky7q3G08V080Q2dKyryLg4FXGRnOKscXqluCp4rnr6HbXcXkIOcrWBqVsCTha7qUjzq0DlWGDSFRWhc2+DwMVXZMDGK64yOJoqgc1LE23PvTWXHSljHzc02yTtfhczR6whz3r6QtG821jPtXzX8OQf7Xjx6ivpHTDizjHtUgWlpH6U5aa/SpMyI0UjUlAjjvHCn7MfpXhPiZf9If619AeNoS1oxHpXg3idCLlx70I0OYA61DIKsP8AKTxUL81aCxFVu0UMwqvtJ4q3YrtYZ5pTZpTWpvadCMDite3gz2qjpmCoGK3LRRjJrzqzPYw8ULFb4xxWvYoFwarxqDir1umBXBJs9OEbF2HrVlemKpxZBqyh4rFs2SJ16Cpo6gQ1PGaEDJl608Gowcc05WqjFkgNOA4pi1MvSmmRcAlOVMHpT1I9KevNO5LGhaeBS4oFUmRYWkNJn2pQfaquUJTTTi3tTSaA3IzTetOOaTGKkVmMcVEVqc1G6k85qkNXIGUZpVUZFKyn1pBwaobHFRTSop/WmtmgmxHMg2VlXkfBrYdhsxis28UkGqizKVznL1MAmsO9XJNdBqAwprEuiCeldtJnHVRg3aYJ4rNkQZNbd4meay5UIJrrTPOmigyc9KWOPOfapWXJqSCPG4n0qrkHV/DCHdqqH3r6GshiFF9q8I+FUX/ExD54zXvFrjYp9qGxFsU1+lLnFNc1FzIiakpWpKYjJ8VxCSybA7V4H4uh2XT5HevonUovNs3z6V4Z8Qbby7iQ7aDRHndwBuquw5qec/Oc1Ax5qkUgVeas2ww4qup5FWoRhhxUTNIbm/pjcCt60OVzXO6e2BW9p5zF1rgrHtYVGtAavwngVnQmr9v2rhkelHYtp1qePpUCdanj6Vgy0yZKnjqBKniqkJslp6rTV61MgptGTYqqcVMq8U1elTKOKaRkwUVIoxQopx6U7BcSiiinYQmKMUuKMGqSJYmKTbzUqDrQR7U7DTINtIVqcr7U0j2ppBcg2801l5qwVpNmRTsFyk61GFO6rrpULJwaaQXIwKawqQCmvSaC5C3SqlyuVNXHqCUfLTSM2zm9UTCE1z11w3NddqMW6MjFcxqEOHPFdVN2OWqjLuACKzpkGScVpzrxVSWPiuyLuedNGY6jNOQfK2BUkic0sSfe+laGTO2+FSn7YPrXuFtxGteM/ClB9rHHevao1wi/SkyWiY9KY9PPSmtUIzZGaSlNJVITFlG+IivLPiTp+Y3baK9TJwMVxXxCgLWTsB2plo+dr+Dy7hh71UKc1q6yjJeOCO9ZrE5qkUh0aYqzAKrK1WoSKiZtSWpp2I5rdsfuisKybmt2x5UVwVj2sOjatugq9D1FUbb7oq/BywFcMjvWxZjPNWo+RUEanNWY1OKyZSZIhqeOo1XgVPGvFNIUiSPk1MlRouDUyCrsZMkWpl6ColFSjpVJGTFpDS0h6U7DFFKKb2pwqkiWKRQtKRSqOaaRI9RxxTse1CYAOaVmFUkTcQEelD49KaZFFRtcJVKIXHgUELmofPX1pGmU96dguSlFNMeIYJpnnKO9BnTHWmkFyGVBioCBmp5ZUPeoGZCetJoLkbjkmoJBzVo4xUEmKVgKk8e5MYrA1a1JBwK6RzxVG9i3qeKuLMKiOFuISrGqUq8kV0OpQFWPFYk6YJrrpO559RGdIKYOtTSjmokH7xRXQYs9N+Fsf7xTtr11fuLXmfwwhxGrYr0xOoFJktEh+7TG6U9ulMbpUIzaI2ptOam1SJYD5znpisDxXELizkQjGBW/GKo6pB5sEgx2plux82+MbcRXzEdjXNZDE54r0P4i2Oy8JA9a87cEOwpoVx0ZBzU0LHNVYzgmrNsNz0pm9J6mvYDIzW/p4wgzWPYRnArbtFworzq1z3MO9DWtTkCr9ucSCqFrwKtq4HeuNq52p6GnG65q1GwxWMJ1H8VSLeqvRqnkJUjdQrip0KgdawY79eOasR3645NWoCcjZDipUYVhNqCheDUY1Mg9atRRk5M6YMO1PVwawbfUwepq5DdBuc9aLE3NIuBRvBFUWlyOtEUvPWkF2Xw1OBqokvvUqyZoTAsbqN+O1RluKaWqrksmaUkZxioWmJPNRyvgdar+Zz1q0SST3JQEY4rPuL4IDtOaW8k+RvpWOcsOTVITNBNTYnBWntfkdBWWE96lRCw602JFttQfsKRrtyhIPNRpb5qYW4204jIDcymmm8kXtmpzBUMluc02hXLVtflowrLzVjcrjOawpEkjc4zipoLhlODUMTZoy5A6cVCX3fKVqWOQOmKikGDxUxYnqjJ1W2U5INcxeQBWY5rtZ08ziuX1qLYXrrpM5KsEc9KuT1qKOP8AfIM9TUrcsaW3GbmMe9da2OKWjPY/hzEIbVCDniu9h5Oa4zwDH/oafSuzjGMVLEyQ1G1SkcVGwosZDMZpNtPFIaBAcL3qCYZhfPpTpxlhRN/qCPahiPHviVbHzmPlnvXkNyu2dt3HNe/fEGAyIDjoK8N12323b5HemmNGV/EeauaeCXGBVURVp6VGcilNnRSWpu6evAzWijbTgdKp2owKsFq4ah7NHYuJcYHWkkvDjANUScmnKueKx5TfmLkUsj9zVqON3HU1DZxdK1raLiiwuYgjt2x1p/kOB1NakUK7RmpTbqRSE5GJsfPel2nucVqm3XPA5qndRYpiTIASvQ1btLtgQCcYqkAAaRSATzU2KR0CXKkffFTRSgn7wrnUkAPWrtvMCetSx2N2N896sI/vWXBJwKtxNmobsNRNDdnvSE1FGaex4qou5LiMmIx1qruHc1JcGqh5atCbDbnLcetUXi296vsDiq1yjbSaomxXVfep4E44NUTIVbBq1aSgJyaYkX404p5yB7VHDKpHWpWddpJxijUbsIrA0pAPaq7zRjoaatz6GhsixJLErduaqNBhulXI5NxzmnP8wpXuJlZAU5FS8EU4J60FRQkUloV2HPSsDxIg8skDmulwKxdfiyjNitoPUwqo4hV+Y54qS1U/a0wOM0k5HmlasWA/0iMD1rti9Dz5rU9q8BJ/oKHHauqPXiud8DDbp6fSuiXh80GTJuwqNqkQ96jlNMzGmm0tFADJBmmyf6sinucVFIx2nFTYnQ5bxhb77UnHavBvE8W27f619E68nnWrK3pXhPji18m5coD1oWhcDj1HzgetbelRDIrJgUs2WHSug0lMgHvUVGdlGJeC7RTXfmpWBJx2qKaPniuSZ6tPRCocmrMIywqrCpzVuP5cE1KKuaVsQBVyKcLxWMLoLSfbgOc07XDY6WO6XI5q0lwpHWuQXUEDctU39roo4YUezZLkjqTMuaz72cc1kJrCjksKryan5z7QQaORkc1i80/NME3Jqo+/buApVDYB7moasaxdy15p3Vcs5CWNUEjyM96sWpZZCO1ZSdkdEYtm9asSorRg7VlWTHAzWvagECsW7mnLYtxjpT3HFIh5FPPIq4kNFWVahCfNVmfjGO9Rr1rdMxkiN48KTWfcO2CMVshQy81lzpmcrjgVaIZgai7xgvjFZY1ny8gmurvLBLm1fI5A4xXlutxXMF46sCMHirjZsyqOy0OrTxAo/i/WrUGvJI4Rn4PWvOUlkJ6nNaem2s88qgkhT1xWnKjJSZ6At5E/3XzSvcbRkGuSP2myfCbiB61p6feSXA2yDFRKKNFI6K0uCyA1oRvmsi2QqoIrSt91Y2sOxdx8lMcGpI846U7ZkcijmRa0KbZqlqMRlgb6VpyrjpVWUN5bDFXB6mNRXPOb6Jlu2HvVjSRm+RT61a1uER3BZRz3pmhRK+oIzetdkJaHn1Iu57f4RXbp8f0rdk4XNc74euFjs41yMYrYS9R22ORirujJwZcjPFMkNIk0ZcBTT5lUDIoUkzLkZGKWnMFCjb+NNqiHoQu1MflaCDQw+WpuNxM+/XdCw9q8i+IFn8zttr2SdM8Eda8+8f2LtE5CVLkOEWeMou2XHvXQ6Snyisi4gZLnBXHNbmlAqo3CsZyPSw8S2yfNTZY+an2lj8ozViKEsnI5rmlI9SENDOjjI7Ur9MVp/ZiB92q81uT0Wo5h+zMe5bAOKoNK2eDWzcWUjdFqqLAg/MuKuMjKUWZr+YRuBNZ9xNMjdTXVR2O5cbeKjm0hX/hrXmM+VnLrdTMu3JzWpoIkkuBuz1rSh0Mb+ErX07SDEwISk5DUGbFvZRvbLkdqqy2e1jxWrZROqhWGKsTwqV4FZSkbQgYkUHFP8racirbRlT0xTMZNc83odkIktrxitizzgVlwqcjArWssBfm4rNFtF1OtP7VGhGetSZGK0Ri0RTDOKjxUzYqM9atOxm0KnpUMkHzlqlUjIqRiDVKRDiQWgUFkbvWF4g0CC5kaQKMkVvMhDAqKdOhcDjmrjOxnKF0eY3PhlkclV4zV3S9NkgYEr0ruXtgy/c5qOOz5wYwK0VQy9mYq6bFcJl1GabFoyo/7sV0cdkvfipvIWMZT5jUuZSgZMNmUQKRyKtRQYq8qFhuZcGgqBUtlpECJg1Lt4pRjtS5qAaK0qVCUBU1Zl5NV0b5mzVR0M2jkvEVviQkCs/RIm+2DHY10GvxlskDiqPh2LN62RXVCRzOCbOxsbp44lXPaibUZY5M7jTIEGVFNvIMvwKtyK9kmjQ0vWWMo3N3rr7K6W5hGCM15nsMZ+TrXT+FrtwQJTinFnPOlY6sAjilpqPvGRTsVumcFSNmVXfbVSa8VB1qXUGKRk1x2s6g0ZPzVk2a0o87OkbUIy4yeawPFsqTWzAHtXOtrJEwy1Le3/nQEZ7VjJnfHD6HD6nbr9pJx3q1ZR/JzS6iyGU885p9scJWM5G9OHKy5apnpWhboo61RsWGa1IUDDNc0pHpU1oK4XbUPlqT0qyYxTkiAGazcjVRKpt1I6VBLaKe1aqIpp/kKaI1CZU0YaWxBwOlTC1PFa6Wq7s1MIFHatPaGfs0ZUFoQ2a0ba3wKs+SAoxUkaYFJ1BOCQ0RADmo5eKnbNVLl8A1DmVGJVmOTUSL81Dv81S243E1HNc6ErImtxWhCOBVa3j6VowximiGx6g1JUipQyCtEZNkDU01K4waYaZFyPpzShs0pBpAuOtMCaIZqQpk5qOI4qXdQ3ZBYbspdhHNLuo3UJkSQmKMUZozTbJQp6VE4qSmkUXCxCBzSkU8ikI4poGivJ1qqThzVySq0yYOauxlJGZqylkqnoCbbxq1L9f3VZ+j4+3HFbwOZrU6WFPmU1JMuXxT0GAppCcyVbNEylLb4JNX9GO2UA0wAOCKlsl2ziqiKex11ocRCpd1VrVswipc1ujyqq1KOsnERx6V554gGS1eg6xzGa4XW48k1k2aUFqcTebhcKRnFMlvWX5M8Vfvowp5FY93GMlqyep6kdhlyyu6sKsW7cgdqz/MAO3vVq2Y7hWclYa3Nq1CgcCtO3+5WVadBWpbfcrjqHfSehYUA1KqjGKjWpVrBs3HIijtU6qvpUS1MvSmmgZIgAGKkwpqEdaeDxVXJsOOO1KDTBycU8KT2oYrDHJNULkNzWkyVVuUHNQUkZO07qt2i4Y1GVAap4SFOapIb2NOzRSBkVoJH/drKtZwCOa2LaVWAq1EwlInROOlEigDpUoK4pkrLitFEzuVZF5qNlxUkjqDTSQ1VymbepXOQwFSBc9aVl5zT05pNAgVB6UrLipkUU505qWi0ysRSVMy4qNhSQMbRS49qMe1USxMntQMnrSgU4LTEJjNMYVMFprjimiWys4FQTjirTLzVa45yK0iZtlO42tGQay7Jdl8SvFaMueRUEUf74HFbxM2dDF80AJ60i9c02E4iAqQDAqgQyP5W4qaFv3ox1qAgg0sLHzRVRHNaHVaexaKrhA25qjpf+qq+33a1ueTWWpn6mu9OK5DV4GJPArtbtcofpXM6tHyaynobYd3ZxmoWhZCSOlc7exbVau0vU+Qj1rn7y1yG4rFS1PVUdDk1QGU569qv2sbbgTimXduYpM4xUlu5yKJ6kpamvZ4A5rSgYbcVkWb5NakXauKojrplyPnpUyg1FD0qdelc7OtCqOamXpUS1MvSkA4dakUZ6UwDmpoxTEIsbBsnpUyqaVVzUqrirIbsyMpVG8GM5rTIrL1A4zQgUjO2ln4p8yNHGGJ4pYyOtVtUlPkAA9K1igb0GLexpJgtWzpt2JFAVq4C6nkWYkHvWpo1+6kDNaJGEj0BZzt61BcXaqMk1n21wSoy1JeK0kR21okZj11GBnxv5FaNq4kAKkYrz/VRdW9wpUHB61s+HdRlJCuTTJ6nXtgKc1HGcU1pAyZFNiOTUsaL0TA1MMGq8VTr0rOWxSGOuajKHNTGm1KQmyPbSYqUimkVViRmw9RS4xTu1IadguA9KRhQOtDHiqSM2yBioPNUZMh2J6Grcp5qnMetUjOTKs20nimwqd4pW+9T4Bl61izO5oQ5KirG4bfeooF+WpOOau5ohrsp5FR2x3TgCmFuoqfTkzOD71UQm9Dq9Lhfyc9qtOwAwajsSUhx7U5xk1qeTWepDOcpXP6sODXRSkEdKxdVj+UnFFTVFUJcrOVuuprKkAaUitudQwbisl0/ek1wS0Z71K0omPrNqoUnFYwTA4rq7uLcjbueK5q9XZJxwKpSJkrMfaMQ1bNocpmsKBsGtW0c7RzWVRGtNmvB0qwvSqUTH1qzGTiuVnZF6Ey1MvSol6VNF1qEhNEqDip4hUYFTRiqSIbJoly2Km20y3Hz81Y4p2M2V3FZOtDYm6tl8VmamhkQjGapIDBgkJyBUd6rSLgVVvEmhlJUlRTrSR5SVZjxWiKtoZs9kzMTim21u8bjGa6SC3DDkZqQ6eDyFFaJGUmV7GR2AANbVohKfNWbFbmNxgYroNO2GMAjNaJEIyb63hl+8vP0rOithDNlRXWT28b8hBWbcWnzcCholrUZBP8AKFJq7atkiqcdsQc1dtU5FS4jSL8fSpU6VGg+WngECoegxTSLyaYSc05TUkskIppFJk+tOFUiWIF4pClOzikJpk3GMMComPFSv92q0jc9aaZMiKU81SmPJq1KeM1Ul5qjGWpAetSwcGoT1qSEEt1rSJCNOE/IKGbmoU3BOtNL4PWtLGt7CfxfjWtpEQLg1lR/O/FdLosQCgla0iY1KmhsRrhFp22lboMUmTWyR5dWV2VXyDzVXUI90BPtV+cbjkcVXnIMZQjmia0Kpy1OKvUKOw9aypTtY102s2bK4fIxXN3RG4rjmvNq6M93DVFYjZgyH6VzWrrtkOK32cIpyM1g6v8AvGLDgVEGb1UZ6Mc1pWbkKKykbDc1ftpASOKuexFOWptwNwKuwngVm2xyKvwtgCuOSO2LLi9Kmi+9UCMCKmiPNSU2W1FTRioFPtViLpVIhk8PDVLniok608sMUmSxrnmq5KkkEVLI/PSoWK44HNO4luZ9/axOTwKzHsfLOUHWtqQZakwrduRVJmiKNpAwxmtOGPjmohgGpEkxVqRnKIksIzkCpLU7TimecvcU6NgTWikZ8pfL4GPWoJOTSowIp4UGqTJsRKM1LGm00oTvmpAp9abYtiRDxT8fLmogCKkRxtxis2K4x+KaDzTnqLdg0khEoNOBqIOKeGqrE3HZpCaM0hp2IGyHC1UkPNWJT8tVJOtCRMmRzNVSQ5qxLnFVnFaWM2R96tWg+c5qsg5q3aj5uKuJnctbflqs45q7sO2oxAzGtUEpkmk2xaQZFdXZxBEFZ2lWpTGcVsgYGKuKOSc7hRTiOlJitkckiN6ryjNTtUTinuhRdjN1KDzI84ri9UhKSnivQ2QNG1cpr9sASQK4q0D0cNVszlpOUbPpWFqPQ1vXHy7h0rC1PgZrnUbM9Vy5kZOcPV2zYcVnk/PVm2fBFVLYyi9ToLZhtq9EwwKybZ/lq/buSwrmkjtgzRiPFWIjzVWI8VYi5NZll6P7oqVWxVLzCDipUfNMC2ZMDg0okzUC81KopNCY4nNRvTyaryNyeaaQuoyVhULyY6GmzORVSSXHcVSRpfQsmU560qyn1qgZvenLL71aiC1L++pI5Md6zGuDQtyRVqIOKNpJiBxUizmsiG645qZbtatIlxNVZ+QKso4PesUXSnjNWYZj602jCaNXINGcHFVY5cjrUitkVm0YkxOaifuacDTJPumkgYitUgNV1PrUimqRJLnmlJ4qPPNBPFUSNkPy1WkPNTOciq79aEiWRynioHqWU8VCx4q7GVyMcGrNo2H5qKNcmrtrBufGDVxMpM0bYBlHFX7a3U4OKhs7chRWpaRH0rZIwnIt2luFA4qaQAGnRNhcVFK3zVrFHM5Dj0FJSDpS1ZDGMKherDDioXFQ0SiBzgVTuYBMhG0GtBlBU561X5QnPSoaNoSscB4hsmjm3AYAOa5vUlDISMV6jqdnHcxuMckV5x4o065tAdiEisJxOylWsjkbgMJSO1S242gAGo3kbcRIuDSxHA65rOSOqnK5qWzYPWtmzcYFc7DJg1q2UuWFYSR6FORvQsKn3DFUIH561aDcVg0b3LAYbaFfnrVctSxk5pCNG3bmrYYbaoW+c1OzYWqBhK+W61DJhDuJpCcmqGqXJVcDtTANQuFK4BxWduLY5NV3leTnNS2qEnmqRSJwhYVJHAx9asW8eQM1oW8IxyKtIoymhNLHCc9K13tx6UxIOelaJElIQEjpTJbdlGea10ip7QqVwRVoDmZGZG71Ol/tXbmtC5sVbJrNksCGzSMJIv6bqK7wjHrWySOCp4PNcebWZJd6A8V0ejyPJZ5k+8DioZjY0QeOtITSA8UZ5qRMWiiigkcKdkUwUE8U0Sxs5+T8arPUrtkYqJ6tGTIWqOTpUjdajkqmYzJLEEyCul06MHPyjpWDpqfvBXVacu0En0raCOabJokA7VajOB2qLIozWyOaTLiEU2SmxNxSseatEgKKKKtEsRjUTGnE0xjSYMjcZIOajmwVxT5DzUcnSoYkVWJQ5647VHd2lvf2zebEAcelSuMsPenMdg29qykrmsbo8h8Y6OLe5byhgZrmTug+U8mvYvFdjFJatLtGa8m1ZP8ASWA6Cs3E7aU7DLeQt2xWrZtyD6ViwkgVpWcnSsJI9CnO5v2r55xV1GzxWXZyVoRNzXNJHbF3JiecVJCMmoSeakiNRY0saEHDVMRlaqRPip0kGO9BJBK5jPAzWVeo1yxz8tbEoDGqzKuaoZkx2oTvmrEKc+lWJAPSoZG2DNUiiyjhAOM1oWcwYcjFc9Jc4OKdFqBjPerTFzHVkIe9RsAvfNYKawpx1qT+1FPrWiYuY20lABBFI0oPtWIdSXPenJeBzVXFzGv8pBO6oZEDrjpVeOTOKtKc1LZm2Pt4Ywu0gNnvUscSwgqvQ802PipCalsyY4GlHrTQaUnikSxwNKDUYNOBoJHU1jQTTGNNEMaw75qNjT2ao2NWjKTImqOQ4xT2qGU81olcwmamkjLA101qflxXN6ODxXQQnAreKOabLRbFG/2qHdmnVZzSZbR8Y4qQNu7VXU1KhqkybkpPSkzSUVSZLZ//2Q==";
const finalBossFaceTexture = new THREE.TextureLoader().load(FINALBOSS_FACE_DATA_URI);
finalBossFaceTexture.wrapS = THREE.ClampToEdgeWrapping;
finalBossFaceTexture.wrapT = THREE.ClampToEdgeWrapping;


/* ============================================================
   SETUP
   ============================================================ */
const wrap = document.getElementById('canvas-wrap');
const scene = new THREE.Scene();
scene.background = new THREE.Color(0x0a0d08);
scene.fog = new THREE.Fog(0x0a0d08, 8, 70);

const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 500);
const BASE_FOV = 75;
camera.position.set(0, 1.7, 0);

const renderer = new THREE.WebGLRenderer({ antialias:true });
renderer.setSize(window.innerWidth, window.innerHeight);
renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));
renderer.shadowMap.enabled = true;
wrap.appendChild(renderer.domElement);

window.addEventListener('resize', ()=>{
  camera.aspect = window.innerWidth/window.innerHeight;
  camera.updateProjectionMatrix();
  renderer.setSize(window.innerWidth, window.innerHeight);
});

/* Lighting */
const ambient = new THREE.AmbientLight(0x3a4030, 0.9);
scene.add(ambient);
const moon = new THREE.DirectionalLight(0x8fa0c0, 0.8);
moon.position.set(30,50,10);
moon.castShadow = true;
moon.shadow.mapSize.set(1024,1024);
moon.shadow.camera.left=-60; moon.shadow.camera.right=60;
moon.shadow.camera.top=60; moon.shadow.camera.bottom=-60;
scene.add(moon);
const fill = new THREE.PointLight(0x5a2a1a, 0.6, 40);
fill.position.set(0,5,0);
scene.add(fill);

/* ---------- SKY DOME ---------- */
function buildSky(){
  const canvas = document.createElement('canvas');
  canvas.width = 2; canvas.height = 256;
  const ctx = canvas.getContext('2d');
  const grad = ctx.createLinearGradient(0,0,0,256);
  grad.addColorStop(0,   '#04050a'); // dark night at the zenith
  grad.addColorStop(0.4, '#0d1420');
  grad.addColorStop(0.72,'#241c1e'); // dusky haze near the horizon
  grad.addColorStop(1,   '#2e211c'); // faint dying-ember warmth at the horizon line
  ctx.fillStyle = grad;
  ctx.fillRect(0,0,2,256);
  const tex = new THREE.CanvasTexture(canvas);
  tex.wrapS = THREE.ClampToEdgeWrapping;
  tex.wrapT = THREE.ClampToEdgeWrapping;
  const geo = new THREE.SphereGeometry(400, 24, 16);
  const mat = new THREE.MeshBasicMaterial({ map:tex, side:THREE.BackSide, fog:false, depthWrite:false });
  scene.add(new THREE.Mesh(geo, mat));
}
buildSky();

/* ---------- CLOUDS ---------- */
function makeCloudTexture(){
  const size = 128;
  const canvas = document.createElement('canvas');
  canvas.width = size; canvas.height = size;
  const ctx = canvas.getContext('2d');
  const grad = ctx.createRadialGradient(size/2,size/2,0, size/2,size/2,size/2);
  grad.addColorStop(0,   'rgba(255,255,255,0.85)');
  grad.addColorStop(0.45,'rgba(255,255,255,0.4)');
  grad.addColorStop(1,   'rgba(255,255,255,0)');
  ctx.fillStyle = grad;
  ctx.fillRect(0,0,size,size);
  return new THREE.CanvasTexture(canvas);
}
const cloudTexture = makeCloudTexture();
const cloudGroup = new THREE.Group();
scene.add(cloudGroup);
const clouds = [];
const CLOUD_COUNT = 20;
for(let i=0; i<CLOUD_COUNT; i++){
  const cluster = new THREE.Group();
  const puffCount = 3 + Math.floor(Math.random()*3);
  for(let j=0; j<puffCount; j++){
    const mat = new THREE.SpriteMaterial({
      map: cloudTexture, color:0x6b7280, transparent:true,
      opacity:0.5 + Math.random()*0.15, depthWrite:false, fog:false
    });
    const puff = new THREE.Sprite(mat);
    const s = 16 + Math.random()*14;
    puff.scale.set(s, s*0.5, 1);
    puff.position.set((Math.random()-0.5)*22, (Math.random()-0.5)*4, (Math.random()-0.5)*12);
    cluster.add(puff);
  }
  const ang = Math.random()*Math.PI*2;
  const dist = 70 + Math.random()*100;
  cluster.position.set(Math.cos(ang)*dist, 30+Math.random()*20, Math.sin(ang)*dist);
  cloudGroup.add(cluster);
  const driftAng = Math.random()*Math.PI*2;
  clouds.push({
    cluster,
    speed: 0.15 + Math.random()*0.3,
    dir: new THREE.Vector3(Math.cos(driftAng), 0, Math.sin(driftAng))
  });
}
function updateClouds(dt){
  for(const c of clouds){
    c.cluster.position.x += c.dir.x*c.speed*dt;
    c.cluster.position.z += c.dir.z*c.speed*dt;
    if(Math.hypot(c.cluster.position.x, c.cluster.position.z) > 200){
      const ang = Math.random()*Math.PI*2;
      c.cluster.position.set(Math.cos(ang)*75, c.cluster.position.y, Math.sin(ang)*75);
    }
  }
}

/* Ground */
const groundGeo = new THREE.PlaneGeometry(300,300);
const groundMat = new THREE.MeshStandardMaterial({color:0x1c2016, roughness:1});
const ground = new THREE.Mesh(groundGeo, groundMat);
ground.rotation.x = -Math.PI/2;
ground.receiveShadow = true;
scene.add(ground);

/* Scattered ground detail (patches) */
for(let i=0;i<60;i++){
  const p = new THREE.Mesh(new THREE.CircleGeometry(1+Math.random()*2,8), new THREE.MeshStandardMaterial({color: Math.random()>0.5?0x2a1810:0x141a10, roughness:1}));
  p.rotation.x=-Math.PI/2;
  p.position.set((Math.random()-0.5)*180,0.01,(Math.random()-0.5)*180);
  scene.add(p);
}

/* Obstacles / scenery (crates, ruined walls, cars) used for collision + cover */
const obstacles = []; // {mesh, radius} circular collision
function addBoxObstacle(x,z,w,h,d,color){
  const m = new THREE.Mesh(new THREE.BoxGeometry(w,h,d), new THREE.MeshStandardMaterial({color, roughness:0.9}));
  m.position.set(x,h/2,z);
  m.castShadow = true; m.receiveShadow = true;
  scene.add(m);
  obstacles.push({x,z, radius: Math.max(w,d)/2 + 0.4});
  return m;
}
// perimeter fence-ish walls
for(let i=0;i<10;i++){
  const ang = (i/10)*Math.PI*2;
  addBoxObstacle(Math.cos(ang)*55, Math.sin(ang)*55, 6,3,1.2, 0x2b2620);
}
// random crates / rubble / cars
const colors=[0x3a3226,0x2f2a22,0x44392c,0x555049];
for(let i=0;i<26;i++){
  const x=(Math.random()-0.5)*90, z=(Math.random()-0.5)*90;
  if(Math.hypot(x,z)<6) continue;
  const type = Math.random();
  if(type<0.5) addBoxObstacle(x,z, 1.4+Math.random(),1.2+Math.random(),1.4+Math.random(), colors[Math.floor(Math.random()*colors.length)]);
  else addBoxObstacle(x,z, 4.2,1.5,2, 0x1f2b33);
}
// a few dead trees (thin, no collision needed but adds atmosphere)
for(let i=0;i<20;i++){
  const trunk = new THREE.Mesh(new THREE.CylinderGeometry(0.15,0.25,4,6), new THREE.MeshStandardMaterial({color:0x1a1410}));
  trunk.position.set((Math.random()-0.5)*140,2,(Math.random()-0.5)*140);
  trunk.castShadow=true;
  scene.add(trunk);
}

/* World bound */
const WORLD_LIMIT = 70;

/* ============================================================
   PLAYER / CONTROLS
   ============================================================ */
const player = {
  height:1.7, speed:5.2, sprintMult:1.6,
  health:100, maxHealth:100,
  velocityY:0,
  yaw:0, pitch:0,
  alive:true
};

let pitchObject = new THREE.Object3D();
pitchObject.add(camera);
let yawObject = new THREE.Object3D();
yawObject.position.set(0, player.height, 8);
yawObject.add(pitchObject);
scene.add(yawObject);

const keys = {};
document.addEventListener('keydown', e=>{ keys[e.code]=true; handleWeaponKey(e.code); if(e.code==='KeyR') reload(); });
document.addEventListener('keyup', e=>{ keys[e.code]=false; });

const isTouchDevice = ('ontouchstart' in window) || navigator.maxTouchPoints > 0;

let pointerLocked = false;
const domEl = renderer.domElement;

function requestLock(){
  if(isTouchDevice) return;
  const p = domEl.requestPointerLock();
  // requestPointerLock() can return a Promise (modern browsers) that rejects silently
  // if the environment blocks it (e.g. inside a sandboxed iframe). We don't depend on
  // it succeeding for gameplay to work — see the mousemove/mousedown fallbacks below.
  if(p && typeof p.catch === 'function') p.catch(()=>{});
}
document.addEventListener('pointerlockchange', ()=>{
  pointerLocked = (document.pointerLockElement === domEl);
});
document.addEventListener('pointerlockerror', ()=>{ pointerLocked = false; });

function applyLookDelta(dx,dy,sens){
  yawObject.rotation.y -= dx*sens;
  pitchObject.rotation.x -= dy*sens;
  pitchObject.rotation.x = Math.max(-Math.PI/2+0.05, Math.min(Math.PI/2-0.05, pitchObject.rotation.x));
}

// NOTE: we intentionally do NOT require pointerLocked here. Pointer Lock can be blocked
// silently in some embedded/iframe contexts; movementX/Y are still populated on regular
// mousemove events, so aiming keeps working (just without the cursor being hidden/clamped).
document.addEventListener('mousemove', e=>{
  if(!running || !player.alive || isTouchDevice) return;
  applyLookDelta(e.movementX, e.movementY, 0.0022);
});

/* ---------- TOUCH CONTROLS ---------- */
let moveTouchId = null, lookTouchId = null;
let touchMoveVec = {x:0,y:0};
let joystickCenter = {x:0,y:0};
const JOY_RADIUS = 48;
let lastLookPos = {x:0,y:0};

const joyBase = document.getElementById('joy-base');
const joyKnob = document.getElementById('joy-knob');
const touchControlsEl = document.getElementById('touch-controls');

function isOnTouchUI(target){
  return !!(target && target.closest && target.closest('.touch-btn, .weapon-btn, #weapon-btns'));
}

window.addEventListener('touchstart', e=>{
  if(!running || !player.alive) return;
  for(const t of e.changedTouches){
    if(isOnTouchUI(t.target)) continue; // let button handlers deal with it
    if(t.clientX < window.innerWidth*0.5 && moveTouchId===null){
      moveTouchId = t.identifier;
      joystickCenter = {x:t.clientX, y:t.clientY};
      joyBase.style.left = t.clientX+'px';
      joyBase.style.top = t.clientY+'px';
      joyBase.style.display = 'block';
      joyKnob.style.transform = 'translate(-50%,-50%)';
    } else if(lookTouchId===null){
      lookTouchId = t.identifier;
      lastLookPos = {x:t.clientX, y:t.clientY};
    }
  }
}, {passive:true});

window.addEventListener('touchmove', e=>{
  for(const t of e.changedTouches){
    if(t.identifier === moveTouchId){
      let dx = t.clientX - joystickCenter.x;
      let dy = t.clientY - joystickCenter.y;
      const dist = Math.hypot(dx,dy);
      if(dist > JOY_RADIUS){ dx = dx/dist*JOY_RADIUS; dy = dy/dist*JOY_RADIUS; }
      joyKnob.style.transform = `translate(${dx-22}px, ${dy-22}px)`;
      touchMoveVec = {x: dx/JOY_RADIUS, y: dy/JOY_RADIUS};
    } else if(t.identifier === lookTouchId){
      const dx = t.clientX - lastLookPos.x;
      const dy = t.clientY - lastLookPos.y;
      if(player.alive) applyLookDelta(dx, dy, 0.0032);
      lastLookPos = {x:t.clientX, y:t.clientY};
    }
  }
}, {passive:true});

function endTouch(e){
  for(const t of e.changedTouches){
    if(t.identifier === moveTouchId){
      moveTouchId = null;
      touchMoveVec = {x:0,y:0};
      joyBase.style.display = 'none';
    }
    if(t.identifier === lookTouchId){
      lookTouchId = null;
    }
  }
}
window.addEventListener('touchend', endTouch, {passive:true});
window.addEventListener('touchcancel', endTouch, {passive:true});

/* ---------- GAMEPAD (controle) ---------- */
let gamepadIndex = null;
let gameOverActive = false; // true once game-over or victory screen is showing (Start button restarts)
let gamepadMoveVec = {x:0, y:0};
let gamepadShootHeld = false;
let gamepadAiming = false;
let gamepadSprint = false;
let prevGamepadPressed = [];

window.addEventListener('gamepadconnected', e=>{
  gamepadIndex = e.gamepad.index;
  addFeedMessage('🎮 controle conectado: '+e.gamepad.id, '#8fd0ff');
});
window.addEventListener('gamepaddisconnected', e=>{
  if(gamepadIndex === e.gamepad.index){
    gamepadIndex = null;
    gamepadMoveVec = {x:0,y:0};
    gamepadShootHeld = false;
    if(gamepadAiming){ toggleAim(false); gamepadAiming = false; }
    addFeedMessage('🎮 controle desconectado', '#8fd0ff');
  }
});

function applyDeadzone(v, dz){ return Math.abs(v) < dz ? 0 : v; }

function updateGamepad(dt){
  if(gamepadIndex === null) return;
  const pads = navigator.getGamepads ? navigator.getGamepads() : [];
  const gp = pads[gamepadIndex];
  if(!gp) return;

  // Left stick: movement (same analog blend used by the touch joystick)
  const lx = applyDeadzone(gp.axes[0]||0, 0.18);
  const ly = applyDeadzone(gp.axes[1]||0, 0.18);
  gamepadMoveVec = { x: lx, y: ly };

  // Right stick: look
  const rx = applyDeadzone(gp.axes[2]||0, 0.15);
  const ry = applyDeadzone(gp.axes[3]||0, 0.15);
  if((rx!==0 || ry!==0) && running && player.alive){
    const lookSpeed = 2.6; // radians/sec at full stick deflection
    yawObject.rotation.y -= rx*lookSpeed*dt;
    pitchObject.rotation.x -= ry*lookSpeed*dt;
    pitchObject.rotation.x = Math.max(-Math.PI/2+0.05, Math.min(Math.PI/2-0.05, pitchObject.rotation.x));
  }

  const btn = gp.buttons;
  const pressed = i => !!(btn[i] && (btn[i].pressed || btn[i].value > 0.5));
  const justPressed = i => pressed(i) && !prevGamepadPressed[i];

  // Right trigger (RT/R2, index 7) = shoot. Left trigger (LT/L2, index 6) = aim/scope.
  gamepadShootHeld = pressed(7);
  const aimNow = pressed(6);
  if(aimNow !== gamepadAiming){ toggleAim(aimNow); gamepadAiming = aimNow; }

  // A (index 0) held = sprint
  gamepadSprint = pressed(0);

  // X (index 2) = pistol, Y (index 3) = escopeta, B (index 1) = fuzil de precisão
  if(justPressed(2)) switchWeapon('pistol');
  if(justPressed(3)) switchWeapon('shotgun');
  if(justPressed(1)) switchWeapon('sniper');
  // LB (index 4) = recarregar
  if(justPressed(4)) reload();

  // Start/Menu (index 9): launches the game from the main menu, or restarts after death/victory
  if(justPressed(9)){
    if(onStartScreen) document.getElementById('playBtn').click();
    else if(gameOverActive) location.reload();
  }

  if(running && player.alive && gamepadShootHeld) tryShoot();

  for(let i=0;i<btn.length;i++) prevGamepadPressed[i] = pressed(i);
}

function tryMove(dx,dz){
  const nx = yawObject.position.x + dx;
  const nz = yawObject.position.z + dz;
  // collision vs obstacles
  for(const o of obstacles){
    if(Math.hypot(nx-o.x, nz-o.z) < o.radius) return;
  }
  if(Math.hypot(nx,nz) > WORLD_LIMIT) return;
  yawObject.position.x = nx;
  yawObject.position.z = nz;
}

function updatePlayer(dt){
  if(!player.alive) return;
  const forward = new THREE.Vector3(Math.sin(yawObject.rotation.y), 0, Math.cos(yawObject.rotation.y)).multiplyScalar(-1);
  const right = new THREE.Vector3(forward.z, 0, -forward.x);
  let mx=0, mz=0;
  if(keys['KeyW']){ mx+=forward.x; mz+=forward.z; }
  if(keys['KeyS']){ mx-=forward.x; mz-=forward.z; }
  if(keys['KeyA']){ mx-=right.x; mz-=right.z; }
  if(keys['KeyD']){ mx+=right.x; mz+=right.z; }

  let analogMag = 0;
  if(Math.abs(touchMoveVec.x) > 0.06 || Math.abs(touchMoveVec.y) > 0.06){
    const fwdAmt = -touchMoveVec.y;
    const strafeAmt = touchMoveVec.x;
    mx += forward.x*fwdAmt + right.x*strafeAmt;
    mz += forward.z*fwdAmt + right.z*strafeAmt;
    analogMag = Math.max(analogMag, Math.min(1, Math.hypot(touchMoveVec.x, touchMoveVec.y)));
  }
  if(Math.abs(gamepadMoveVec.x) > 0.001 || Math.abs(gamepadMoveVec.y) > 0.001){
    const fwdAmt = -gamepadMoveVec.y;
    const strafeAmt = gamepadMoveVec.x;
    mx += forward.x*fwdAmt + right.x*strafeAmt;
    mz += forward.z*fwdAmt + right.z*strafeAmt;
    analogMag = Math.max(analogMag, Math.min(1, Math.hypot(gamepadMoveVec.x, gamepadMoveVec.y)));
  }

  const len = Math.hypot(mx,mz);
  let spd = player.speed * (keys['ShiftLeft']||keys['ShiftRight']||gamepadSprint ? player.sprintMult : 1);
  if(isAiming) spd *= 0.4;
  if(len>0){
    mx/=len; mz/=len;
    const magFactor = analogMag>0 ? analogMag : 1;
    tryMove(mx*spd*magFactor*dt, mz*spd*magFactor*dt);
  }
  // subtle head bob
  const moving = len>0;
  bobTime += moving ? dt*(spd/player.speed)*9 : 0;
  const bobY = moving ? Math.sin(bobTime)*0.045 : 0;
  camera.position.y = bobY;
}
let bobTime=0;

/* ============================================================
   WEAPONS
   ============================================================ */
const weapons = {
  pistol: {
    id:'pistol', name:'PISTOLA',
    dmgHead:9999, dmgChestNear:34, dmgChestFar:22, dmgLeg:16,
    range:60, falloffStart:14, fireRate:0.28, reload:1.1,
    mag:12, magSize:12, reserve:48, pellets:1, spread:0.006, scoped:false,
    knockdownChance:0.15
  },
  shotgun: {
    id:'shotgun', name:'ESCOPETA',
    dmgHead:9999, dmgChestNear:22, dmgChestFar:5, dmgLeg:14,
    range:16, falloffStart:5, fireRate:0.85, reload:1.9,
    mag:6, magSize:6, reserve:24, pellets:8, spread:0.09, scoped:false,
    knockdownChance:0.45
  },
  sniper: {
    id:'sniper', name:'FUZIL DE PRECISÃO',
    dmgHead:9999, dmgChestNear:95, dmgChestFar:80, dmgLeg:60,
    range:120, falloffStart:100, fireRate:1.35, reload:2.4,
    mag:5, magSize:5, reserve:15, pellets:1, spread:0.0008, scoped:true,
    knockdownChance:0.7
  },
  scytheMelee: {
    id:'scytheMelee', name:'FOICE DO BOSS', melee:true,
    dmgHead:9999, dmgChestNear:60, dmgChestFar:60, dmgLeg:40,
    range:2.4, falloffStart:2.4, fireRate:0.55, reload:0,
    mag:1, magSize:1, reserve:0, pellets:1, spread:0.02, scoped:false,
    knockdownChance:0.5
  },
  signMelee: {
    id:'signMelee', name:'PLACA DO BOSS', melee:true,
    dmgHead:9999, dmgChestNear:50, dmgChestFar:50, dmgLeg:35,
    range:2.2, falloffStart:2.2, fireRate:0.7, reload:0,
    mag:1, magSize:1, reserve:0, pellets:1, spread:0.03, scoped:false,
    knockdownChance:0.6
  }
};
let currentWeaponId = 'pistol';
let meleeWeaponId = null; // vira 'scytheMelee' ou 'signMelee' ao coletar a arma do boss da onda 1
let currentAmmo = { pistol:12, shotgun:6, sniper:5, scytheMelee:1, signMelee:1 };
let reserveAmmo = { pistol:48, shotgun:24, sniper:15, scytheMelee:0, signMelee:0 };
let lastShot = 0;
let shotCounter = 0;
let reloading = false;
let isAiming = false;

function currentWeapon(){ return weapons[currentWeaponId]; }

/* ---------- VIEWMODEL (arma visível na mão) ---------- */
function buildViewmodelPistol(){
  const g = new THREE.Group();
  const bodyMat = new THREE.MeshStandardMaterial({color:0x2b2b2e, roughness:0.4, metalness:0.6});
  const gripMat = new THREE.MeshStandardMaterial({color:0x161616, roughness:0.7});
  const body = new THREE.Mesh(new THREE.BoxGeometry(0.09,0.14,0.32), bodyMat);
  g.add(body);
  const barrel = new THREE.Mesh(new THREE.CylinderGeometry(0.02,0.02,0.18,8), bodyMat);
  barrel.rotation.x = Math.PI/2;
  barrel.position.set(0,0.02,-0.25);
  g.add(barrel);
  const grip = new THREE.Mesh(new THREE.BoxGeometry(0.07,0.18,0.08), gripMat);
  grip.position.set(0,-0.14,0.09);
  grip.rotation.x = 0.35;
  g.add(grip);
  const sight = new THREE.Mesh(new THREE.BoxGeometry(0.02,0.02,0.02), bodyMat);
  sight.position.set(0,0.08,-0.14);
  g.add(sight);
  return g;
}
function buildViewmodelShotgun(){
  const g = new THREE.Group();
  const woodMat = new THREE.MeshStandardMaterial({color:0x4a2f1a, roughness:0.8});
  const metalMat = new THREE.MeshStandardMaterial({color:0x1e1e1e, roughness:0.4, metalness:0.7});
  const barrel = new THREE.Mesh(new THREE.CylinderGeometry(0.035,0.035,0.78,8), metalMat);
  barrel.rotation.x = Math.PI/2;
  barrel.position.set(0,0.03,-0.35);
  g.add(barrel);
  const pump = new THREE.Mesh(new THREE.BoxGeometry(0.085,0.08,0.22), woodMat);
  pump.position.set(0,-0.01,-0.25);
  g.add(pump);
  const receiver = new THREE.Mesh(new THREE.BoxGeometry(0.09,0.11,0.2), metalMat);
  receiver.position.set(0,0.0,0.02);
  g.add(receiver);
  const stock = new THREE.Mesh(new THREE.BoxGeometry(0.09,0.13,0.4), woodMat);
  stock.position.set(0,-0.04,0.28);
  g.add(stock);
  return g;
}
function buildViewmodelSniper(){
  const g = new THREE.Group();
  const metalMat = new THREE.MeshStandardMaterial({color:0x24261f, roughness:0.35, metalness:0.7});
  const darkMat = new THREE.MeshStandardMaterial({color:0x141414, roughness:0.4, metalness:0.6});
  const barrel = new THREE.Mesh(new THREE.CylinderGeometry(0.025,0.03,0.95,8), metalMat);
  barrel.rotation.x = Math.PI/2;
  barrel.position.set(0,0.01,-0.42);
  g.add(barrel);
  const body = new THREE.Mesh(new THREE.BoxGeometry(0.08,0.12,0.5), metalMat);
  body.position.set(0,-0.02,0.08);
  g.add(body);
  const scope = new THREE.Mesh(new THREE.CylinderGeometry(0.035,0.035,0.3,10), darkMat);
  scope.rotation.x = Math.PI/2;
  scope.position.set(0,0.1,-0.05);
  g.add(scope);
  const scopeLensF = new THREE.Mesh(new THREE.CylinderGeometry(0.037,0.037,0.01,10), new THREE.MeshStandardMaterial({color:0x3fa9c9, emissive:0x104050}));
  scopeLensF.rotation.x = Math.PI/2;
  scopeLensF.position.set(0,0.1,-0.2);
  g.add(scopeLensF);
  const stock = new THREE.Mesh(new THREE.BoxGeometry(0.08,0.11,0.38), metalMat);
  stock.position.set(0,-0.03,0.38);
  g.add(stock);
  return g;
}

function buildViewmodelScythe(){
  const g = new THREE.Group();
  const handleMat = new THREE.MeshStandardMaterial({color:0x4a2f1a, roughness:0.7});
  const bladeMat = new THREE.MeshStandardMaterial({color:0xb8bcc4, metalness:0.8, roughness:0.25});
  const handle = new THREE.Mesh(new THREE.CylinderGeometry(0.025,0.025,0.9,8), handleMat);
  handle.rotation.z = Math.PI/2;
  handle.position.set(0,-0.06,-0.1);
  g.add(handle);
  const blade = new THREE.Mesh(new THREE.TorusGeometry(0.22,0.028,6,16,2.0), bladeMat);
  blade.position.set(0.32,0.04,-0.1);
  g.add(blade);
  return g;
}
function buildViewmodelSign(){
  const g = new THREE.Group();
  const pole = new THREE.Mesh(new THREE.CylinderGeometry(0.02,0.02,0.55,8),
    new THREE.MeshStandardMaterial({color:0x777777, metalness:0.5, roughness:0.6}));
  pole.position.y = -0.24;
  g.add(pole);
  const oct = new THREE.Mesh(new THREE.CylinderGeometry(0.2,0.2,0.03,8),
    new THREE.MeshStandardMaterial({color:0xc4161c, roughness:0.6}));
  oct.rotation.x = Math.PI/2; oct.rotation.z = Math.PI/8;
  oct.position.y = 0.05;
  g.add(oct);
  const cv = document.createElement('canvas'); cv.width = cv.height = 128;
  const cx = cv.getContext('2d');
  cx.fillStyle = '#fff'; cx.font = 'bold 38px Arial';
  cx.textAlign = 'center'; cx.textBaseline = 'middle';
  cx.fillText('PARE',64,68);
  const txt = new THREE.Mesh(new THREE.PlaneGeometry(0.36,0.36),
    new THREE.MeshBasicMaterial({map:new THREE.CanvasTexture(cv), transparent:true, side:THREE.DoubleSide}));
  txt.position.set(0,0.05,0.02);
  g.add(txt);
  return g;
}

const viewmodelAnchor = new THREE.Group();
viewmodelAnchor.position.set(0.22,-0.22,-0.5);
camera.add(viewmodelAnchor);

const viewmodels = {
  pistol: buildViewmodelPistol(),
  shotgun: buildViewmodelShotgun(),
  sniper: buildViewmodelSniper(),
  scytheMelee: buildViewmodelScythe(),
  signMelee: buildViewmodelSign()
};
Object.values(viewmodels).forEach(vm=>{ vm.visible = false; vm.castShadow = false; viewmodelAnchor.add(vm); });
viewmodels[currentWeaponId].visible = true;

const muzzleTip = new THREE.Object3D();
muzzleTip.position.set(0, 0.03, -0.75); // roughly where the barrel ends, in front of the visible weapon
viewmodelAnchor.add(muzzleTip);

let recoilAmount = 0;
function updateViewmodel(dt){
  recoilAmount = Math.max(0, recoilAmount - dt*7);
  const vm = viewmodels[currentWeaponId];
  if(!vm) return;
  vm.position.z = recoilAmount*0.12;
  vm.rotation.x = -recoilAmount*0.25;
  const moving = (keys['KeyW']||keys['KeyA']||keys['KeyS']||keys['KeyD']||Math.abs(touchMoveVec.x)>0.06||Math.abs(touchMoveVec.y)>0.06||Math.abs(gamepadMoveVec.x)>0.001||Math.abs(gamepadMoveVec.y)>0.001) && player.alive && !isAiming;
  const bx = moving ? Math.sin(bobTime*2)*0.015 : 0;
  const by = moving ? Math.abs(Math.sin(bobTime*2))*0.012 : 0;
  vm.position.x = bx;
  vm.position.y = -by - recoilAmount*0.02;
}

function handleWeaponKey(code){
  if(code==='Digit1') switchWeapon('pistol');
  if(code==='Digit2') switchWeapon('shotgun');
  if(code==='Digit3') switchWeapon('sniper');
  if(code==='Digit4' && meleeWeaponId) switchWeapon(meleeWeaponId);
}
function switchWeapon(id){
  if(reloading) return;
  currentWeaponId = id;
  isAiming = false;
  document.getElementById('scope-overlay').style.display='none';
  camera.fov = BASE_FOV; camera.updateProjectionMatrix();
  Object.keys(viewmodels).forEach(k=>{ viewmodels[k].visible = (k===id); });
  document.querySelectorAll('.weapon-btn').forEach(b=>{ b.classList.toggle('active', b.dataset.w===id); });
  updateHUD();
}

function reload(){
  const w = currentWeapon();
  if(w.melee) return;
  if(reloading) return;
  if(currentAmmo[w.id] >= w.magSize) return;
  if(reserveAmmo[w.id] <= 0) return;
  reloading = true;
  document.getElementById('reload-msg').style.display='block';
  setTimeout(()=>{
    const need = w.magSize - currentAmmo[w.id];
    const take = Math.min(need, reserveAmmo[w.id]);
    currentAmmo[w.id] += take;
    reserveAmmo[w.id] -= take;
    reloading = false;
    document.getElementById('reload-msg').style.display='none';
    updateHUD();
  }, w.reload*1000);
}

/* mouse buttons */
domEl.addEventListener('mousedown', e=>{
  if(isTouchDevice || !running || !player.alive) return;
  if(e.button===0){ shootHeld=true; tryShoot(); }
  if(e.button===2){ toggleAim(true); }
});
window.addEventListener('mouseup', e=>{
  if(e.button===0) shootHeld=false;
  if(e.button===2) toggleAim(false);
});
domEl.addEventListener('contextmenu', e=>e.preventDefault());
let shootHeld=false;

function toggleAim(state){
  const w = currentWeapon();
  if(!w.scoped) return;
  isAiming = state && !reloading;
  document.getElementById('scope-overlay').style.display = isAiming ? 'block' : 'none';
  camera.fov = isAiming ? 18 : BASE_FOV;
  camera.updateProjectionMatrix();
  viewmodels[w.id].visible = !isAiming;
}

/* ---------- TOUCH UI BUTTONS ---------- */
const btnFire = document.getElementById('btn-fire');
const btnAim = document.getElementById('btn-aim');
const btnReload = document.getElementById('btn-reload');

btnFire.addEventListener('touchstart', e=>{ e.preventDefault(); e.stopPropagation(); shootHeld=true; tryShoot(); }, {passive:false});
btnFire.addEventListener('touchend', e=>{ e.preventDefault(); e.stopPropagation(); shootHeld=false; }, {passive:false});
btnFire.addEventListener('touchcancel', e=>{ shootHeld=false; });

btnAim.addEventListener('touchstart', e=>{ e.preventDefault(); e.stopPropagation(); toggleAim(true); }, {passive:false});
btnAim.addEventListener('touchend', e=>{ e.preventDefault(); e.stopPropagation(); toggleAim(false); }, {passive:false});
btnAim.addEventListener('touchcancel', e=>{ toggleAim(false); });

btnReload.addEventListener('touchstart', e=>{ e.preventDefault(); e.stopPropagation(); reload(); }, {passive:false});

const btnFullscreen = document.getElementById('btn-fullscreen');
function toggleFullscreen(){
  const el = document.documentElement;
  const request = el.requestFullscreen || el.webkitRequestFullscreen || el.msRequestFullscreen;
  const exit = document.exitFullscreen || document.webkitExitFullscreen || document.msExitFullscreen;
  try{
    const isFull = document.fullscreenElement || document.webkitFullscreenElement;
    if(!isFull && request){
      const p = request.call(el);
      if(p && p.catch) p.catch(()=>{});
    } else if(isFull && exit){
      const p = exit.call(document);
      if(p && p.catch) p.catch(()=>{});
    }
  }catch(err){ /* fullscreen can be blocked inside an embedded preview — fail silently */ }
}
btnFullscreen.addEventListener('touchstart', e=>{ e.preventDefault(); e.stopPropagation(); toggleFullscreen(); }, {passive:false});
btnFullscreen.addEventListener('click', toggleFullscreen);

document.querySelectorAll('.weapon-btn').forEach(btn=>{
  btn.addEventListener('touchstart', e=>{
    e.preventDefault(); e.stopPropagation();
    switchWeapon(btn.dataset.w);
  }, {passive:false});
});

function tryShoot(){
  if(!player.alive) return;
  const w = currentWeapon();
  const now = performance.now()/1000;
  if(reloading) return;
  if(now - lastShot < w.fireRate) return;
  if(!w.melee && currentAmmo[w.id] <= 0){ reload(); return; }
  lastShot = now;
  if(!w.melee){
    currentAmmo[w.id]--;
    updateHUD();
  }
  fireRaycast(w);
  muzzleFlash();
  if(!w.melee && currentAmmo[w.id]<=0) reload();
}

/* auto-fire loop for held mouse (pistol/shotgun feel ok, sniper limited by fireRate) */
setInterval(()=>{ if(shootHeld) tryShoot(); }, 16);

function muzzleFlash(){
  document.getElementById('crosshair').style.filter = 'brightness(2.4)';
  setTimeout(()=>{ document.getElementById('crosshair').style.filter=''; }, 60);
  recoilAmount = 1;
}

const raycaster = new THREE.Raycaster();
const TRACER_STYLE = {
  pistol:  { color:0xfff4c2, thickness:0.014 },
  shotgun: { color:0xffb347, thickness:0.011 },
  sniper:  { color:0xbfe8ff, thickness:0.022 },
  scytheMelee: { color:0xd8dde2, thickness:0.024 },
  signMelee:   { color:0xffffff, thickness:0.024 }
};

function spawnTracer(start, end, color, thickness){
  const diff = new THREE.Vector3().subVectors(end, start);
  const length = diff.length();
  if(length < 0.05) return;
  const geo = new THREE.CylinderGeometry(thickness, thickness, length, 6, 1, true);
  geo.translate(0, length/2, 0); // so the cylinder grows from its base (start point) upward
  const mat = new THREE.MeshBasicMaterial({ color, transparent:true, opacity:0.95, depthWrite:false });
  const mesh = new THREE.Mesh(geo, mat);
  mesh.position.copy(start);
  const up = new THREE.Vector3(0,1,0);
  mesh.quaternion.setFromUnitVectors(up, diff.clone().normalize());
  scene.add(mesh);

  const born = performance.now();
  const life = 90; // ms — appears and vanishes fast, no bullets litter the map
  (function fade(){
    const t = (performance.now()-born)/life;
    if(t >= 1){
      scene.remove(mesh);
      geo.dispose(); mat.dispose();
      return;
    }
    mat.opacity = 0.95*(1-t);
    requestAnimationFrame(fade);
  })();
}

function fireRaycast(w){
  shotCounter++;
  const camPos = new THREE.Vector3();
  camera.getWorldPosition(camPos);
  const camDir = new THREE.Vector3();
  camera.getWorldDirection(camDir);
  const muzzlePos = new THREE.Vector3();
  muzzleTip.getWorldPosition(muzzlePos);
  const style = TRACER_STYLE[w.id] || TRACER_STYLE.pistol;

  let anyHit = false, headHit = false;

  for(let p=0; p<w.pellets; p++){
    const dir = camDir.clone();
    dir.x += (Math.random()-0.5)*w.spread;
    dir.y += (Math.random()-0.5)*w.spread;
    dir.z += (Math.random()-0.5)*w.spread;
    dir.normalize();
    raycaster.set(camPos, dir);
    raycaster.far = w.range;
    const hits = raycaster.intersectObjects(hittableMeshes, false);
    const travelDist = hits.length>0 ? hits[0].distance : w.range;
    const endPoint = camPos.clone().addScaledVector(dir, travelDist);
    spawnTracer(muzzlePos, endPoint, style.color, style.thickness);

    if(hits.length>0){
      const hit = hits[0];
      const dist = hit.distance;
      const zone = hit.object.userData.zone;
      const zombie = hit.object.userData.zombie;
      if(zombie && zombie.alive){
        anyHit = true;
        if(zone==='head') headHit = true;
        applyDamage(zombie, zone, dist, w);
      }
    }
  }
  if(anyHit) showHitmarker(headHit);
}

function showHitmarker(headshot){
  const hm = document.getElementById('hitmarker');
  hm.className = headshot ? 'headshot show' : 'show';
  clearTimeout(hm._t);
  hm._t = setTimeout(()=>{ hm.className=''; }, 180);
}

/* ============================================================
   ZOMBIES
   ============================================================ */
const hittableMeshes = []; // flat list of zombie body-part meshes used for shot raycasting.
// IMPORTANT: these meshes stay attached to their own zombie's group (so they move/rotate
// correctly with the zombie); we just keep a separate flat array of references for raycasting.

const zombies = [];
let score = 0;
const MAX_WAVE = 15;
let wave = 1;
let zombiesToSpawn = wave*10;      // wave 1 = 10, wave 2 = 20, ... wave 15 = 150
let zombiesAliveTarget = Math.min(6+wave, 18); // concurrent zombies on screen at once (kept playable)
let spawnTimer = 0;
let gameWon = false;

const ZOMBIE_TYPES = {
  walker: { color:0x4c6b3a, speed:1.7, health:100, scale:1.0, attack:9, label:'Andarilho' },
  runner: { color:0x8a2a20, speed:5.8, health:65, scale:0.95, attack:13, label:'Corredor' },
  crawler:{ color:0x5c5738, speed:0.8, health:55, scale:0.9, attack:7, label:'Rastejante' },
  boss: { color:0x000000, speed:5.8, health:9999, scale:2, attack:85, reach:2.6, label:'BOSS' },
  finalboss: { color:0x000000, speed:5.8, health:9999, scale:2, attack:60, reach:2.6, label:'BOSS FINAL' },
  owl: { color:0x0d0d0d, speed:1.7, health:10, scale:1, attack:6, reach:2.0, label:'Coruja' }
};

function buildZombie(type){
  const def = ZOMBIE_TYPES[type];
  const group = new THREE.Group();
  const mat = new THREE.MeshStandardMaterial({color:def.color, roughness:0.85});
  const matDark = new THREE.MeshStandardMaterial({color: new THREE.Color(def.color).multiplyScalar(0.6), roughness:0.9});

  // body (chest)
  const chest = new THREE.Mesh(new THREE.BoxGeometry(0.7,0.9,0.4), mat);
  chest.position.y = 1.15;
  chest.castShadow = true;
  group.add(chest);

  // head
  const head = new THREE.Mesh(new THREE.SphereGeometry(0.27,10,10), matDark);
  head.position.y = 1.75;
  head.castShadow = true;
  group.add(head);

  // legs (two, used for "leg" hit zone as one unit each side, tag both same zone)
  const legL = new THREE.Mesh(new THREE.BoxGeometry(0.28,0.85,0.32), matDark);
  legL.position.set(-0.19, 0.42, 0);
  const legR = legL.clone();
  legR.position.x = 0.19;
  group.add(legL, legR);

  // arms (cosmetic, tag as chest zone so they don't create dead zones)
  const armGeo = new THREE.BoxGeometry(0.2,0.7,0.2);
  const armL = new THREE.Mesh(armGeo, mat);
  armL.position.set(-0.48,1.2,0);
  armL.rotation.z = 0.3;
  const armR = armL.clone();
  armR.position.x = 0.48; armR.rotation.z=-0.3;
  group.add(armL, armR);

  // Base pose per zombie type
  if(type === 'walker'){
    // classic zombie stance: arms held out straight ahead
    armL.rotation.set(-1.15, 0, 0.08);
    armR.rotation.set(-1.15, 0, -0.08);
    armL.position.z = 0.22;
    armR.position.z = 0.22;
  } else if(type === 'crawler'){
    // low, prone stance dragging itself along the ground
    chest.position.set(0, 0.42, 0.02);
    chest.rotation.x = -1.2;
    head.position.set(0, 0.46, 0.42);
    legL.position.set(-0.19, 0.15, -0.38);
    legR.position.set(0.19, 0.15, -0.38);
    legL.rotation.x = -0.3;
    legR.rotation.x = -0.3;
    armL.position.set(-0.32, 0.28, 0.42);
    armR.position.set(0.32, 0.28, 0.42);
    armL.rotation.set(-1.0, 0, 0);
    armR.rotation.set(-1.0, 0, 0);
  }

  // Runner zombies get the uploaded face texture on the front of the head
  let face = null;
  if(type === 'runner' || type === 'boss' || type === 'finalboss'){
    const faceMat = new THREE.MeshBasicMaterial({
      map: type === 'finalboss' ? finalBossFaceTexture : (type === 'boss' ? bossFaceTexture : runnerFaceTexture),
      transparent:true, side:THREE.DoubleSide, depthWrite:false
    });
    face = new THREE.Mesh(new THREE.PlaneGeometry(0.5,0.5), faceMat);
    face.position.set(0, 1.75, 0.33); // pushed clear of the head sphere's surface (radius 0.27) so it isn't clipped inside it
    group.add(face);
  }

  let sign = null, bossWeapon = null;
  if(type === 'boss'){
    bossWeapon = Math.random() < 0.5 ? 'scythe' : 'sign';
    armL.rotation.set(-0.5,0,0.3);
    armR.rotation.set(-1.2,0,-0.1); armR.position.z = 0.2;
    sign = new THREE.Group();
    const pole = new THREE.Mesh(new THREE.CylinderGeometry(0.04,0.04, bossWeapon==='scythe' ? 2.0 : 1.6, 8),
      new THREE.MeshStandardMaterial({color: bossWeapon==='scythe' ? 0x4a2f1a : 0x777777, metalness:0.4, roughness:0.6}));
    pole.position.y = -0.8;
    sign.add(pole);
    if(bossWeapon === 'scythe'){
      const blade = new THREE.Mesh(new THREE.TorusGeometry(0.6,0.06,6,20,2.0),
        new THREE.MeshStandardMaterial({color:0xb8bcc4, metalness:0.8, roughness:0.3}));
      blade.rotation.x = Math.PI/2;
      blade.position.set(-0.6, 0.2, 0);
      sign.add(blade);
    } else {
      const holder = new THREE.Group(); holder.rotation.x = Math.PI/2;
      const oct = new THREE.Mesh(new THREE.CylinderGeometry(0.47,0.47,0.05,8),
        new THREE.MeshStandardMaterial({color:0xc4161c, roughness:0.6}));
      oct.rotation.y = Math.PI/8;
      holder.add(oct);
      const cv = document.createElement('canvas'); cv.width = cv.height = 256;
      const cx = cv.getContext('2d');
      cx.strokeStyle = '#fff'; cx.lineWidth = 10; cx.beginPath();
      for(let i=0;i<8;i++){
        const a = Math.PI/4*i + Math.PI/8;
        const px = 128+Math.cos(a)*112, py = 128+Math.sin(a)*112;
        i ? cx.lineTo(px,py) : cx.moveTo(px,py);
      }
      cx.closePath(); cx.stroke();
      cx.fillStyle = '#fff'; cx.font = 'bold 74px Arial';
      cx.textAlign = 'center'; cx.textBaseline = 'middle';
      cx.fillText('PARE',128,132);
      const txt = new THREE.Mesh(new THREE.PlaneGeometry(0.9,0.9),
        new THREE.MeshBasicMaterial({map:new THREE.CanvasTexture(cv), transparent:true, side:THREE.DoubleSide}));
      txt.position.z = 0.04;
      sign.add(holder, txt);
    }
    sign.position.set(0.62, 2.25, 0.6);
    group.add(sign);
  }

  let finalBossVariant = null, chestImmune = false, finalAttackDamage = null;
  let appliedScale = def.scale;
  if(type === 'finalboss'){
    finalBossVariant = Math.random() < 0.4 ? 'greatsword' : 'katana';
    armL.rotation.set(-0.55,0,0.25);
    armR.rotation.set(-1.25,0,-0.15); armR.position.z = 0.2;
    sign = new THREE.Group();
    if(finalBossVariant === 'greatsword'){
      // Cabo enfaixado de branco
      const grip = new THREE.Mesh(new THREE.CylinderGeometry(0.045,0.045,0.5,8),
        new THREE.MeshStandardMaterial({color:0xe8e4da, roughness:0.75}));
      grip.position.y = -0.28;
      sign.add(grip);
      const pommel = new THREE.Mesh(new THREE.SphereGeometry(0.06,8,8),
        new THREE.MeshStandardMaterial({color:0xc9ccd1, metalness:0.8, roughness:0.3}));
      pommel.position.y = -0.55;
      sign.add(pommel);
      // Guarda circular prateada
      const guard = new THREE.Mesh(new THREE.CylinderGeometry(0.14,0.14,0.06,16),
        new THREE.MeshStandardMaterial({color:0xb8bcc4, metalness:0.85, roughness:0.25}));
      sign.add(guard);
      // Lâmina larga: base cinza clara com tarja preta central (feito de duas caixas finas)
      const bladeEdge = new THREE.Mesh(new THREE.BoxGeometry(0.36,2.1,0.05),
        new THREE.MeshStandardMaterial({color:0xc9ccd1, metalness:0.7, roughness:0.3}));
      bladeEdge.position.y = 1.12;
      sign.add(bladeEdge);
      const bladeCenter = new THREE.Mesh(new THREE.BoxGeometry(0.24,2.1,0.052),
        new THREE.MeshStandardMaterial({color:0x1c1c1c, metalness:0.3, roughness:0.6}));
      bladeCenter.position.y = 1.12;
      sign.add(bladeCenter);
      const tip = new THREE.Mesh(new THREE.ConeGeometry(0.18,0.28,4),
        new THREE.MeshStandardMaterial({color:0xc9ccd1, metalness:0.7, roughness:0.3}));
      tip.rotation.y = Math.PI/4;
      tip.position.y = 2.28;
      sign.add(tip);
      sign.position.set(0.68, 1.55, 0.55);
      sign.rotation.z = 0.28;
      chestImmune = true;
      finalAttackDamage = 100;
      appliedScale = def.scale * 1.3; // maior que o boss da onda 10
    } else {
      // Katana: lâmina fina e curva, cabo escuro
      const handle = new THREE.Mesh(new THREE.CylinderGeometry(0.035,0.035,0.35,8),
        new THREE.MeshStandardMaterial({color:0x1a1410, roughness:0.8}));
      handle.position.y = -0.17;
      sign.add(handle);
      const tsuba = new THREE.Mesh(new THREE.CylinderGeometry(0.08,0.08,0.02,12),
        new THREE.MeshStandardMaterial({color:0x2a2620, metalness:0.6, roughness:0.4}));
      sign.add(tsuba);
      const blade = new THREE.Mesh(new THREE.BoxGeometry(0.045,1.15,0.012),
        new THREE.MeshStandardMaterial({color:0xd8dde2, metalness:0.85, roughness:0.15}));
      blade.position.y = 0.6;
      blade.rotation.z = -0.08;
      sign.add(blade);
      const spine = new THREE.Mesh(new THREE.BoxGeometry(0.014,1.15,0.014),
        new THREE.MeshStandardMaterial({color:0x2a2a2a, metalness:0.4, roughness:0.5}));
      spine.position.set(0.012,0.6,0);
      spine.rotation.z = -0.08;
      sign.add(spine);
      sign.position.set(0.62, 2.0, 0.55);
      sign.rotation.z = 0.15;
      chestImmune = false;
      finalAttackDamage = 60;
      appliedScale = def.scale; // igual à altura do boss da onda 10
    }
    group.add(sign);
  }

  group.scale.setScalar(appliedScale);

  const parts = { head, chest, legL, legR, armL, armR };
  if(face) parts.face = face;

  const zombie = {
    type, def, group,
    health: def.health, maxHealth: def.health,
    baseSpeed: def.speed, speed: def.speed,
    alive:true, state: type==='crawler' ? 'crawling' : 'walking',
    slowTimer:0, fallTimer:0, headHits:0, legHits:0, lastHeadShot:-1, sign, bossWeapon,
    finalBossVariant, chestImmune, chestHits:0,
    headHitsByWeapon:{pistol:0, shotgun:0, sniper:0},
    attackDamage: bossWeapon==='scythe' ? 45 : (bossWeapon==='sign' ? 85 : finalAttackDamage),
    parts,
    attackCooldown:0
  };

  const taggable = [ [head,'head'], [chest,'chest'], [armL,'chest'], [armR,'chest'], [legL,'leg'], [legR,'leg'] ];
  if(face) taggable.push([face,'head']); // shooting the face counts as a headshot
  taggable.forEach(([mesh,zone])=>{
      mesh.userData.zone = zone;
      mesh.userData.zombie = zombie;
      hittableMeshes.push(mesh); // mesh stays a child of `group`; we just track it for raycasting
    });

  return zombie;
}


/* ---------- CORUJAS (invocação do boss final) ---------- */
function buildOwl(){
  const def = ZOMBIE_TYPES.owl;
  const group = new THREE.Group();
  const bodyMat = new THREE.MeshStandardMaterial({color:0x0d0d0d, roughness:0.9});
  const bellyMat = new THREE.MeshStandardMaterial({color:0x2a1a1a, roughness:0.9});
  const eyeMat = new THREE.MeshStandardMaterial({color:0xff2020, emissive:0x8a0000, emissiveIntensity:1.1});
  const beakMat = new THREE.MeshStandardMaterial({color:0x1a1a1a, roughness:0.5, metalness:0.25});
  const wingMat = new THREE.MeshStandardMaterial({color:0x050505, roughness:0.95});

  const body = new THREE.Mesh(new THREE.SphereGeometry(0.32,10,10), bodyMat);
  body.scale.set(1,1.25,0.9);
  body.castShadow = true;
  group.add(body);

  const belly = new THREE.Mesh(new THREE.SphereGeometry(0.2,8,8), bellyMat);
  belly.position.set(0,-0.05,0.2);
  group.add(belly);

  const eyeL = new THREE.Mesh(new THREE.SphereGeometry(0.08,8,8), eyeMat);
  eyeL.position.set(-0.13,0.14,0.27);
  const eyeR = eyeL.clone(); eyeR.position.x = 0.13;
  group.add(eyeL, eyeR);

  const beak = new THREE.Mesh(new THREE.ConeGeometry(0.06,0.16,6), beakMat);
  beak.rotation.x = Math.PI/2;
  beak.position.set(0,0.0,0.37);
  group.add(beak);

  // asas rasgadas, em formato de lâmina (estilo morcego), achatadas
  const wingGeo = new THREE.ConeGeometry(0.24, 0.68, 4, 1, false, Math.PI/4);
  const wingL = new THREE.Mesh(wingGeo, wingMat);
  wingL.scale.set(1,1,0.16);
  wingL.rotation.z = Math.PI/2 + 0.3;
  wingL.position.set(-0.36, 0.04, 0);
  const wingR = wingL.clone();
  wingR.rotation.z = -(Math.PI/2 + 0.3);
  wingR.position.x = 0.36;
  group.add(wingL, wingR);

  // tufos em espinho, mais longos e ameaçadores
  const earL = new THREE.Mesh(new THREE.ConeGeometry(0.045,0.24,5), bodyMat);
  earL.position.set(-0.13,0.44,0.05); earL.rotation.z = -0.3;
  const earR = earL.clone(); earR.position.x = 0.13; earR.rotation.z = 0.3;
  group.add(earL, earR);

  const parts = { body, wingL, wingR };
  const zombie = {
    type:'owl', def, group,
    health: def.health, maxHealth: def.health,
    baseSpeed: def.speed, speed: def.speed,
    alive:true, state:'flying',
    slowTimer:0, fallTimer:0,
    owlHits:0,
    parts,
    attackDamage: def.attack,
    reach: def.reach,
    attackCooldown:0,
    flyPhase: Math.random()*Math.PI*2,
    hoverHeight: 3.0 + Math.random()*1.0
  };

  [[body,'owl'],[wingL,'owl'],[wingR,'owl']].forEach(([mesh,zone])=>{
    mesh.userData.zone = zone;
    mesh.userData.zombie = zombie;
    hittableMeshes.push(mesh);
  });

  return zombie;
}

function spawnOwls(bossZombie){
  for(let i=0;i<2;i++){
    const owl = buildOwl();
    const ang = (i===0 ? -1 : 1)*0.9;
    const bx = bossZombie.group.position.x + Math.cos(ang)*2.2;
    const bz = bossZombie.group.position.z + Math.sin(ang)*2.2;
    owl.group.position.set(bx, owl.hoverHeight, bz);
    scene.add(owl.group);
    zombies.push(owl);
  }
  addFeedMessage('🦉 O boss invocou duas corujas!', '#ffd23f');
}

function updateOwl(z, dt, playerPos){
  z.flyPhase += dt*2.4;
  const dx = playerPos.x - z.group.position.x;
  const dz = playerPos.z - z.group.position.z;
  const distXZ = Math.hypot(dx,dz) || 0.0001;
  const dirX = dx/distXZ, dirZ = dz/distXZ;
  z.group.rotation.y = Math.atan2(dirX, dirZ);

  const targetY = z.hoverHeight + Math.sin(z.flyPhase*0.6)*0.4;
  z.group.position.y += (targetY - z.group.position.y)*Math.min(1, dt*2);

  const reach = z.reach || 2.0;
  if(distXZ > reach){
    z.group.position.x += dirX*z.speed*dt;
    z.group.position.z += dirZ*z.speed*dt;
  } else {
    z.attackCooldown -= dt;
    if(z.attackCooldown <= 0){
      z.attackCooldown = 1.4;
      damagePlayer(z.attackDamage);
    }
  }

  const flap = Math.sin(z.flyPhase*8);
  z.parts.wingL.rotation.z = 0.15 + flap*0.5;
  z.parts.wingR.rotation.z = -0.15 - flap*0.5;
}

// On these waves, the FIRST N zombies spawned that wave are forced to be runners
// (the rest of that wave, and every other wave, uses the normal mix).
const RUNNER_WAVE_OVERRIDE = { 5:25, 10:50, 15:140 };
let spawnedInWave = 0; // how many zombies have been spawned so far in the current wave

function pickZombieType(){
  if(wave === 3 && spawnedInWave === wave*10 - 1) return 'boss';
  if(wave === MAX_WAVE && spawnedInWave === wave*10 - 1) return 'finalboss';
  const forcedCount = RUNNER_WAVE_OVERRIDE[wave];
  if(forcedCount !== undefined && spawnedInWave < forcedCount){
    return 'runner';
  }
  const roll = Math.random();
  if(roll < 0.28) return 'runner';
  if(roll < 0.52) return 'crawler';
  return 'walker';
}

function spawnZombie(){
  const type = pickZombieType();
  spawnedInWave++;
  const z = buildZombie(type);
  if(type === 'boss') addFeedMessage('⚠ O BOSS CHEGOU ('+(z.bossWeapon==='scythe'?'foice':'placa de PARE')+')', '#c92a2a');
  if(type === 'finalboss'){
    addFeedMessage('☠ O BOSS FINAL CHEGOU ('+(z.finalBossVariant==='greatsword'?'espada gigante':'katana')+')', '#ff2a2a');
    spawnOwls(z);
  }

  const ang = Math.random()*Math.PI*2;
  const dist = 30 + Math.random()*20;
  z.group.position.set(Math.cos(ang)*dist, 0, Math.sin(ang)*dist);
  z.group.rotation.y = ang + Math.PI;
  scene.add(z.group);
  zombies.push(z);
}

function applyDamage(zombie, zone, dist, w){
  if(!zombie.alive) return;
  if(zombie.type === 'owl'){
    flashHitColor(zombie);
    if(w.id === 'pistol'){
      zombie.owlHits++;
      if(zombie.owlHits >= 10) killZombie(zombie, false);
    }
    return;
  }
  if(zombie.type === 'finalboss'){
    if(zone === 'head'){
      if(zombie.lastHeadShot !== shotCounter){
        zombie.lastHeadShot = shotCounter;
        const wid = (w.id === 'pistol' || w.id === 'shotgun') ? w.id : 'shotgun'; // sniper usa o mesmo limiar da escopeta
        zombie.headHitsByWeapon[wid]++;
        flashHitColor(zombie);
        const threshold = wid === 'pistol' ? 20 : 15;
        if(zombie.headHitsByWeapon[wid] >= threshold) killZombie(zombie, true);
      }
    } else if(zone === 'chest' && !zombie.chestImmune){
      zombie.chestHits++;
      flashHitColor(zombie);
      if(zombie.chestHits >= 100) killZombie(zombie, false);
    }
    return;
  }
  if(zombie.type === 'boss'){
    if(zone === 'head'){
      if(zombie.lastHeadShot !== shotCounter){
        zombie.lastHeadShot = shotCounter;
        zombie.headHits += (w.id === 'pistol') ? 0.5 : 1;
        flashHitColor(zombie);
        if(zombie.headHits >= 10) killZombie(zombie, true);
      }
    } else if(zone === 'leg' && w.id === 'pistol'){
      zombie.legHits++;
      flashHitColor(zombie);
      if(zombie.legHits >= 5){
        zombie.legHits = 0;
        if(zombie.state !== 'fallen'){
          zombie.state = 'fallen';
          zombie.fallTimer = 4.5;
          zombie.group.rotation.x = -Math.PI/2.6;
        }
      }
    }
    return;
  }
  if(zone === 'head'){
    killZombie(zombie, true);
    return;
  }
  if(zone === 'chest'){
    const near = dist <= w.falloffStart;
    let dmg = near ? w.dmgChestNear : w.dmgChestFar;
    if(!near && w.dmgChestNear!==w.dmgChestFar){
      const t = Math.min(1, (dist-w.falloffStart)/(w.range-w.falloffStart));
      dmg = w.dmgChestNear + (w.dmgChestFar-w.dmgChestNear)*t;
    }
    zombie.health -= dmg;
    flashHitColor(zombie);
    if(zombie.health <= 0) killZombie(zombie, false);
    return;
  }
  if(zone === 'leg'){
    zombie.health -= w.dmgLeg*0.4; // legs do a little damage too
    flashHitColor(zombie);
    // slow effect always
    zombie.slowTimer = 3.5;
    // chance to knock down (crawling state) based on weapon
    if(Math.random() < w.knockdownChance && zombie.state!=='fallen'){
      zombie.state = 'fallen';
      zombie.fallTimer = 4.5;
      zombie.group.rotation.x = -Math.PI/2.6;
    }
    if(zombie.health <= 0) killZombie(zombie, false);
    return;
  }
}

function flashHitColor(zombie){
  Object.values(zombie.parts).forEach(m=>{
    if(!m.material._orig) m.material._orig = m.material.color.getHex();
    m.material.color.setHex(0xff3020);
  });
  setTimeout(()=>{
    Object.values(zombie.parts).forEach(m=>{
      if(m.material._orig!=null) m.material.color.setHex(m.material._orig);
    });
  }, 90);
}

function killZombie(zombie, headshot){
  if(!zombie.alive) return;
  zombie.alive = false;
  zombie.health = 0;
  score += headshot ? 15 : 10;
  addKillFeed(zombie.def.label, headshot);
  updateHUD();

  // drop ammo pickup on the ground where it died
  if(zombie.type !== 'crawler' && zombie.type !== 'owl' && Math.random() < AMMO_DROP_CHANCE){
    spawnAmmoPickup(zombie.group.position.x, zombie.group.position.z);
  }
  // runners also have a chance to drop a health pack
  if(zombie.type === 'runner' && Math.random() < HEALTH_DROP_CHANCE){
    spawnHealthPickup(zombie.group.position.x + 0.4, zombie.group.position.z + 0.4);
  }
  // the wave-1 boss has a 50% chance to drop the weapon he was carrying (placa/foice)
  if(zombie.type === 'boss' && Math.random() < 0.7){
    spawnBossWeaponPickup(zombie.group.position.x - 0.4, zombie.group.position.z - 0.4, zombie.bossWeapon);
  }

  // Remove this zombie's parts from the raycast target list RIGHT AWAY so its corpse
  // can no longer block shots meant for zombies standing behind/near it while it collapses.
  Object.values(zombie.parts).forEach(m=>{
    const hi = hittableMeshes.indexOf(m);
    if(hi >= 0) hittableMeshes.splice(hi,1);
  });

  // simple death animation: collapse
  const g = zombie.group;
  let t = 0;
  const startY = g.position.y;
  function collapse(){
    t += 0.06;
    g.rotation.z = Math.min(Math.PI/2, t*3);
    const dropAmount = (zombie.type === 'owl') ? t*4.5 : t*0.6;
    g.position.y = Math.max(-0.3, startY - dropAmount);
    if(t < 1) requestAnimationFrame(collapse);
    else {
      setTimeout(()=>{
        scene.remove(g);
        const idx = zombies.indexOf(zombie);
        if(idx>=0) zombies.splice(idx,1);
      }, 2500);
    }
  }
  collapse();
}

function addFeedMessage(text, borderColor){
  const el = document.createElement('div');
  el.className = 'kill-msg';
  if(borderColor) el.style.borderLeftColor = borderColor;
  el.textContent = text;
  document.getElementById('kill-feed').appendChild(el);
  setTimeout(()=> el.remove(), 2600);
}

function addKillFeed(label, headshot){
  addFeedMessage(headshot ? (label+' — tiro na cabeça') : (label+' abatido'));
}

/* ============================================================
   AMMO DROPS
   ============================================================ */
const ammoPickups = []; // {group, life}
const AMMO_PICKUP_RADIUS = 1.3;
const AMMO_PICKUP_AMOUNT = 6;
const AMMO_DROP_CHANCE = 0.4; // 40% chance any given zombie drops ammo on death

function spawnAmmoPickup(x,z){
  const group = new THREE.Group();
  const boxMat = new THREE.MeshStandardMaterial({color:0xffd23f, emissive:0x5a3d00, emissiveIntensity:0.7, roughness:0.35, metalness:0.4});
  const box = new THREE.Mesh(new THREE.BoxGeometry(0.28,0.16,0.42), boxMat);
  group.add(box);
  const capMat = new THREE.MeshStandardMaterial({color:0x8a6a1f, roughness:0.5, metalness:0.3});
  const cap1 = new THREE.Mesh(new THREE.CylinderGeometry(0.05,0.05,0.03,10), capMat);
  cap1.rotation.x = Math.PI/2;
  cap1.position.set(0.09,0.1,0);
  const cap2 = cap1.clone(); cap2.position.x = -0.09;
  group.add(cap1, cap2);
  const light = new THREE.PointLight(0xffd23f, 0.7, 3.2);
  light.position.set(0,0.25,0);
  group.add(light);
  group.position.set(x, 0.28, z);
  group.rotation.y = Math.random()*Math.PI*2;
  scene.add(group);
  ammoPickups.push({ group, life: 10 });
}

function collectAmmoPickup(pickup){
  scene.remove(pickup.group);
  const w = currentWeapon();
  reserveAmmo[w.id] += AMMO_PICKUP_AMOUNT;
  updateHUD();
  addFeedMessage('+'+AMMO_PICKUP_AMOUNT+' munição ('+w.name+')', '#ffd23f');
}

function updateAmmoPickups(dt){
  const playerPos = yawObject.position;
  for(let i = ammoPickups.length-1; i >= 0; i--){
    const p = ammoPickups[i];
    p.group.rotation.y += dt*1.7;
    p.group.position.y = 0.28 + Math.sin(performance.now()/280 + i)*0.06;
    p.life -= dt;
    if(p.life < 4) p.group.visible = Math.floor(p.life*6)%2===0; // blink before it expires

    const dx = playerPos.x - p.group.position.x;
    const dz = playerPos.z - p.group.position.z;
    if(Math.hypot(dx,dz) < AMMO_PICKUP_RADIUS){
      collectAmmoPickup(p);
      ammoPickups.splice(i,1);
      continue;
    }
    if(p.life <= 0){
      scene.remove(p.group);
      ammoPickups.splice(i,1);
    }
  }
}

/* ============================================================
   HEALTH DROPS (runner zombies only)
   ============================================================ */
const healthPickups = []; // {group, life}
const HEALTH_PICKUP_RADIUS = 1.3;
const HEALTH_PICKUP_PERCENT = 10; // % of max health restored, overridden on boss waves below
const HEALTH_DROP_CHANCE = 0.4;   // runners have a 40% chance to drop a health pack

function spawnHealthPickup(x,z){
  const group = new THREE.Group();
  const caseMat = new THREE.MeshStandardMaterial({color:0xe6e6e0, roughness:0.4, metalness:0.1});
  const crossMat = new THREE.MeshStandardMaterial({color:0xc92a2a, emissive:0x5a0f0f, emissiveIntensity:0.6, roughness:0.4});
  const box = new THREE.Mesh(new THREE.BoxGeometry(0.32,0.2,0.32), caseMat);
  group.add(box);
  const crossV = new THREE.Mesh(new THREE.BoxGeometry(0.07,0.03,0.2), crossMat);
  crossV.position.y = 0.105;
  const crossH = new THREE.Mesh(new THREE.BoxGeometry(0.2,0.03,0.07), crossMat);
  crossH.position.y = 0.105;
  group.add(crossV, crossH);
  const light = new THREE.PointLight(0xff5050, 0.7, 3.2);
  light.position.set(0,0.3,0);
  group.add(light);
  group.position.set(x, 0.28, z);
  group.rotation.y = Math.random()*Math.PI*2;
  scene.add(group);
  healthPickups.push({ group, life: 10 });
}

const HEALTH_HARD_WAVES = [5, 10, 15]; // reduced healing on these tougher waves

function collectHealthPickup(pickup){
  scene.remove(pickup.group);
  const healPercent = HEALTH_HARD_WAVES.includes(wave) ? 5 : HEALTH_PICKUP_PERCENT;
  const healAmount = Math.round(player.maxHealth * (healPercent/100));
  player.health = Math.min(player.maxHealth, player.health + healAmount);
  updateHUD();
  addFeedMessage('+'+healPercent+'% de vida', '#ff5050');
}

function updateHealthPickups(dt){
  const playerPos = yawObject.position;
  for(let i = healthPickups.length-1; i >= 0; i--){
    const p = healthPickups[i];
    p.group.rotation.y += dt*1.4;
    p.group.position.y = 0.28 + Math.sin(performance.now()/260 + i)*0.06;
    p.life -= dt;
    if(p.life < 4) p.group.visible = Math.floor(p.life*6)%2===0;

    const dx = playerPos.x - p.group.position.x;
    const dz = playerPos.z - p.group.position.z;
    if(Math.hypot(dx,dz) < HEALTH_PICKUP_RADIUS){
      collectHealthPickup(p);
      healthPickups.splice(i,1);
      continue;
    }
    if(p.life <= 0){
      scene.remove(p.group);
      healthPickups.splice(i,1);
    }
  }
}


/* ============================================================
   BOSS WEAPON DROPS (placa / foice do boss da onda 1)
   ============================================================ */
const bossWeaponPickups = []; // {group, life, weaponType}
const BOSS_WEAPON_PICKUP_RADIUS = 1.4;
const BOSS_WEAPON_SCORE_BONUS = 50;

function spawnBossWeaponPickup(x,z,weaponType){
  const group = new THREE.Group();
  if(weaponType === 'scythe'){
    const handleMat = new THREE.MeshStandardMaterial({color:0x4a2f1a, roughness:0.7});
    const bladeMat = new THREE.MeshStandardMaterial({color:0xb8bcc4, metalness:0.8, roughness:0.25, emissive:0x2a2c30, emissiveIntensity:0.4});
    const handle = new THREE.Mesh(new THREE.CylinderGeometry(0.03,0.03,0.7,8), handleMat);
    handle.rotation.z = Math.PI/2;
    group.add(handle);
    const blade = new THREE.Mesh(new THREE.TorusGeometry(0.28,0.035,6,16,2.0), bladeMat);
    blade.position.set(0.3,0.12,0);
    group.add(blade);
  } else {
    const holderMat = new THREE.MeshStandardMaterial({color:0xc4161c, roughness:0.6, emissive:0x4a0000, emissiveIntensity:0.3});
    const oct = new THREE.Mesh(new THREE.CylinderGeometry(0.28,0.28,0.04,8), holderMat);
    oct.rotation.x = Math.PI/2; oct.rotation.z = Math.PI/8;
    group.add(oct);
    const cv = document.createElement('canvas'); cv.width = cv.height = 128;
    const cx = cv.getContext('2d');
    cx.fillStyle = '#fff'; cx.font = 'bold 40px Arial';
    cx.textAlign = 'center'; cx.textBaseline = 'middle';
    cx.fillText('PARE',64,68);
    const txt = new THREE.Mesh(new THREE.PlaneGeometry(0.5,0.5),
      new THREE.MeshBasicMaterial({map:new THREE.CanvasTexture(cv), transparent:true, side:THREE.DoubleSide}));
    txt.position.z = 0.03;
    group.add(txt);
  }
  const light = new THREE.PointLight(weaponType==='scythe' ? 0xbfe0ff : 0xff5050, 0.7, 3.2);
  light.position.set(0,0.3,0);
  group.add(light);
  group.position.set(x, 0.55, z);
  group.rotation.y = Math.random()*Math.PI*2;
  scene.add(group);
  bossWeaponPickups.push({ group, life: 14, weaponType });
}

function ensureMeleeButton(weaponType){
  const wid = weaponType === 'scythe' ? 'scytheMelee' : 'signMelee';
  let btn = document.getElementById('btn-melee-weapon');
  if(!btn){
    btn = document.createElement('div');
    btn.id = 'btn-melee-weapon';
    btn.className = 'weapon-btn';
    document.getElementById('weapon-btns').appendChild(btn);
    btn.addEventListener('touchstart', e=>{
      e.preventDefault(); e.stopPropagation();
      if(meleeWeaponId) switchWeapon(meleeWeaponId);
    }, {passive:false});
  }
  btn.dataset.w = wid;
  btn.textContent = weaponType === 'scythe' ? '🗡' : '🛑';
  meleeWeaponId = wid;
}

function collectBossWeaponPickup(pickup){
  scene.remove(pickup.group);
  score += BOSS_WEAPON_SCORE_BONUS;
  const label = pickup.weaponType === 'scythe' ? 'a Foice do Boss' : 'a Placa do Boss';
  ensureMeleeButton(pickup.weaponType);
  switchWeapon(meleeWeaponId); // ativa o corpo a corpo assim que a arma é coletada
  addFeedMessage('Você pegou '+label+'! Corpo a corpo ativado (tecla 4)', '#ffd23f');
  updateHUD();
}

function updateBossWeaponPickups(dt){
  const playerPos = yawObject.position;
  for(let i = bossWeaponPickups.length-1; i >= 0; i--){
    const p = bossWeaponPickups[i];
    p.group.rotation.y += dt*1.1;
    p.group.position.y = 0.55 + Math.sin(performance.now()/300 + i)*0.08;
    p.life -= dt;
    if(p.life < 4) p.group.visible = Math.floor(p.life*6)%2===0;

    const dx = playerPos.x - p.group.position.x;
    const dz = playerPos.z - p.group.position.z;
    if(Math.hypot(dx,dz) < BOSS_WEAPON_PICKUP_RADIUS){
      collectBossWeaponPickup(p);
      bossWeaponPickups.splice(i,1);
      continue;
    }
    if(p.life <= 0){
      scene.remove(p.group);
      bossWeaponPickups.splice(i,1);
    }
  }
}

function updateZombies(dt){
  const playerPos = yawObject.position;
  for(const z of zombies){
    if(!z.alive) continue;
    if(z.type === 'owl'){ updateOwl(z, dt, playerPos); continue; }

    if(z.fallTimer > 0){
      z.fallTimer -= dt;
      if(z.fallTimer <= 0){
        z.state = (z.type==='crawler') ? 'crawling' : 'walking';
        z.group.rotation.x = 0;
      }
      continue; // fallen, can't move
    }
    if(z.slowTimer > 0){
      z.slowTimer -= dt;
      z.speed = z.baseSpeed * 0.35;
    } else {
      z.speed = z.baseSpeed;
    }

    const dx = playerPos.x - z.group.position.x;
    const dz = playerPos.z - z.group.position.z;
    const dist = Math.hypot(dx,dz);
    const dirX = dx/dist, dirZ = dz/dist;

    z.group.rotation.y = Math.atan2(dirX, dirZ);

    // crawling posture (lean forward, lower)
    if(z.type==='crawler' || z.state==='fallen'){
      z.group.position.y = 0;
    }

    const reach = z.reach || z.def.reach || 1.3;
    if(dist > reach){
      z.group.position.x += dirX*z.speed*dt;
      z.group.position.z += dirZ*z.speed*dt;
    } else {
      z.attackCooldown -= dt;
      if(z.attackCooldown <= 0){
        z.attackCooldown = 1.0;
        damagePlayer(z.attackDamage || z.def.attack);
      }
    }

    // per-type limb animation, speed-scaled so slowed/knocked zombies animate slower too
    const t = performance.now()/1000;
    const phase = t*(2 + z.speed*1.4) + z.group.id;
    const p = z.parts;
    if(z.type === 'walker'){
      const legSwing = Math.sin(phase*4)*0.5;
      p.legL.rotation.x = legSwing;
      p.legR.rotation.x = -legSwing;
      const armSway = Math.sin(phase*4)*0.12;
      p.armL.rotation.z = 0.08 + armSway;
      p.armR.rotation.z = -0.08 - armSway;
    } else if(z.type === 'runner' || z.type === 'boss' || z.type === 'finalboss'){
      const swing = Math.sin(phase*3.2)*0.95;
      p.armL.rotation.x = swing;
      p.armR.rotation.x = -swing;
      const legSwing = Math.sin(phase*3.2)*0.65;
      p.legL.rotation.x = legSwing;
      p.legR.rotation.x = -legSwing;
    } else if(z.type === 'crawler'){
      const drag = Math.sin(phase*2.4)*0.18;
      p.armL.rotation.x = -1.0 + drag;
      p.armR.rotation.x = -1.0 - drag;
      p.legL.rotation.x = -0.3 - drag*0.5;
      p.legR.rotation.x = -0.3 + drag*0.5;
    }

    if(z.type === 'boss'){
      p.armR.rotation.x = -1.2;
      if(z.sign) z.sign.rotation.z = Math.sin(phase*3.2)*0.06;
    }
    if(z.type === 'finalboss'){
      p.armR.rotation.x = -1.25;
      if(z.sign) z.sign.rotation.x = Math.sin(phase*3.2)*0.1;
    }

    // simple bob/shuffle animation
    const bob = Math.sin(performance.now()/150 + z.group.id)*0.05;
    if(z.type === 'crawler'){
      p.head.position.y = 0.46 + bob*0.2;
    } else {
      p.head.position.y = 1.75 + bob*0.3;
    }
  }
}

function damagePlayer(amount){
  if(!player.alive) return;
  player.health -= amount;
  flashDamageVignette();
  if(player.health <= 0){
    player.health = 0;
    endGame();
  }
  updateHUD();
}
function flashDamageVignette(){
  const v = document.getElementById('damage-vignette');
  v.style.boxShadow = 'inset 0 0 160px rgba(200,0,0,0.55)';
  setTimeout(()=>{ v.style.boxShadow='inset 0 0 0px rgba(180,0,0,0)'; }, 250);
}

/* Spawner / wave logic */
function updateSpawner(dt){
  if(gameWon) return;
  const bossWaiting = (zombiesToSpawn === 1 && zombies.some(z=>z.alive) && (wave === 3 || wave === MAX_WAVE));
  if(zombies.length < zombiesAliveTarget && zombiesToSpawn > 0 && !bossWaiting){
    spawnTimer -= dt;
    if(spawnTimer <= 0){
      // spawns get a little faster on later waves to keep bigger waves playable
      spawnTimer = Math.max(0.28, 0.85 - wave*0.03) + Math.random()*0.4;
      spawnZombie();
      zombiesToSpawn--;
      updateHUD();
    }
  }
  if(zombiesToSpawn <= 0 && zombies.length===0){
    if(wave >= MAX_WAVE){
      triggerVictory();
      return;
    }
    wave++;
    zombiesToSpawn = wave*10;
    zombiesAliveTarget = Math.min(6+wave, 18);
    spawnedInWave = 0;
    document.getElementById('wave-num').textContent = wave;
    updateHUD();
  }
}

/* ============================================================
   HUD
   ============================================================ */
function updateHUD(){
  document.getElementById('health-bar-inner').style.width = Math.max(0,player.health) + '%';
  document.getElementById('score-num').textContent = score;
  document.getElementById('wave-num').textContent = wave;
  const aliveCount = zombies.reduce((n,z)=> n + (z.alive ? 1 : 0), 0);
  document.getElementById('zombies-num').textContent = aliveCount + zombiesToSpawn;
  const w = currentWeapon();
  document.getElementById('weapon-name').textContent = w.name;
  document.getElementById('ammo-count').textContent = w.melee ? '∞' : currentAmmo[w.id];
  document.getElementById('ammo-reserve').textContent = w.melee ? 'corpo a corpo' : ('reserva: ' + reserveAmmo[w.id]);
}

/* ============================================================
   GAME FLOW
   ============================================================ */
let running = false;
let onStartScreen = true;

document.getElementById('playBtn').addEventListener('click', ()=>{
  onStartScreen = false;
  document.getElementById('start-screen').style.display='none';
  document.getElementById('hud').style.display='block';
  if(isTouchDevice){
    document.getElementById('touch-controls').style.display='block';
  } else {
    requestLock();
  }
  running = true;
  updateHUD();
});

document.getElementById('restartBtn').addEventListener('click', ()=>{
  location.reload();
});

function endGame(){
  running = false;
  player.alive = false;
  gameOverActive = true;
  document.exitPointerLock();
  document.getElementById('gameover-stats').innerHTML =
    'Ondas sobrevividas: <b style="color:#c92a2a">'+ (wave-1>0?wave-1:0) +'</b><br>Abates: <b style="color:#c92a2a">'+score+'</b>';
  document.getElementById('gameover-screen').style.display='flex';
  document.getElementById('hud').style.display='none';
  document.getElementById('scope-overlay').style.display='none';
  document.getElementById('touch-controls').style.display='none';
}

function triggerVictory(){
  if(gameWon) return;
  gameWon = true;
  running = false;
  gameOverActive = true;
  document.exitPointerLock();
  document.getElementById('victory-stats').innerHTML =
    'Ondas concluídas: <b style="color:#9fd0e0">'+MAX_WAVE+'</b> / '+MAX_WAVE+'<br>Abates: <b style="color:#9fd0e0">'+score+'</b>';
  document.getElementById('victory-screen').style.display='flex';
  document.getElementById('hud').style.display='none';
  document.getElementById('scope-overlay').style.display='none';
  document.getElementById('touch-controls').style.display='none';
}

document.getElementById('victoryRestartBtn').addEventListener('click', ()=>{
  location.reload();
});

/* ============================================================
   MAIN LOOP
   ============================================================ */
let lastTime = performance.now();
function animate(){
  requestAnimationFrame(animate);
  const now = performance.now();
  const dt = Math.min(0.05, (now-lastTime)/1000);
  lastTime = now;

  updateClouds(dt);
  updateGamepad(dt);

  if(running && player.alive){
    updatePlayer(dt);
    updateViewmodel(dt);
    updateZombies(dt);
    updateSpawner(dt);
    updateAmmoPickups(dt);
    updateHealthPickups(dt);
    updateBossWeaponPickups(dt);
  }

  renderer.render(scene, camera);
}
animate();

/* click canvas to relock if lost mid-game (desktop only) */
domEl.addEventListener('click', ()=>{
  if(!isTouchDevice && running && player.alive && !pointerLocked) requestLock();
});

/* Adapt the start-screen copy for touch devices (no mouse/keyboard hints) */
if(isTouchDevice){
  const brief = document.querySelector('#start-screen .brief');
  if(brief){
    brief.innerHTML =
      'Use o <b>manche esquerdo</b> para andar e arraste no lado direito da tela para olhar ao redor.<br><br>' +
      '<b>🔫</b> atira · <b>🎯</b> mira de precisão (fuzil) · <b>⟳</b> recarrega · botões <b>1 2 3</b> trocam de arma<br><br>' +
      'Tiro na <b>cabeça</b> mata na hora. Tiro no <b>peito</b> causa dano pesado. Tiro na <b>perna</b> derruba ou deixa lento.';
  }
  const hint = document.querySelector('#start-screen .hint');
  if(hint) hint.textContent = 'toque no botão para começar';
}

})();
</script>
</body>
</html>
