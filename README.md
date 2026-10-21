<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Happy Birthday, Nanaluu 🐘</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,400;0,600;1,400&family=Caveat:wght@500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --sky:#dfe9f8; --cream:#fbf4ee; --navy:#2b3a5c; --blue:#8fb0e0;
    --rose:#d9778f; --gold:#b98f45; --muted:#5d6b8a;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  body{
    font-family:'Fraunces',Georgia,serif; color:var(--navy); line-height:1.7;
    background:linear-gradient(180deg,var(--sky),var(--cream)) fixed; min-height:100vh; overflow-x:hidden;
  }
  #pattern{position:fixed;inset:0;z-index:0;pointer-events:none}
  #float{position:fixed;inset:0;pointer-events:none;overflow:hidden;z-index:1}
  .fl{position:absolute;bottom:-40px;animation:rise linear forwards;opacity:.85}
  @keyframes rise{to{transform:translateY(-115vh) rotate(18deg);opacity:0}}

  section{position:relative;z-index:2;max-width:600px;margin:0 auto;padding:0 24px}
  .screen{min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;gap:16px;padding-top:40px;padding-bottom:40px}
  .script{font-family:'Caveat',cursive;font-size:clamp(1.6rem,6vw,2.2rem);color:var(--gold)}
  h1{font-weight:600;font-size:clamp(2.2rem,8.5vw,3.6rem);line-height:1.12}
  .hint{color:var(--muted);font-style:italic;font-size:.95rem}
  .elephant{font-size:4.5rem;animation:sway 3s ease-in-out infinite}
  @keyframes sway{50%{transform:rotate(-6deg) translateY(-4px)}}

  .card{display:flex;flex-direction:column;align-items:center;gap:14px;width:100%;background:rgba(255,255,255,.72);border:1px solid rgba(143,176,224,.55);border-radius:32px;padding:30px 22px 28px;box-shadow:0 18px 50px rgba(43,58,92,.14);backdrop-filter:blur(4px)}
  .card h1{font-size:clamp(2rem,8vw,3rem)}
  /* Photo */
  .arch{width:min(280px,100%);aspect-ratio:3/4;border-radius:150px 150px 22px 22px;overflow:hidden;border:6px solid #fff;box-shadow:0 14px 40px rgba(43,58,92,.22)}
  .arch img{width:100%;height:100%;object-fit:cover;object-position:50% 15%;display:block}

  .cake{font-size:3.4rem;cursor:pointer;user-select:none;transition:transform .2s}
  .cake:hover{transform:scale(1.1)}
  button{font:inherit;font-weight:600;color:#fff;background:var(--navy);border:0;padding:14px 30px;border-radius:40px;cursor:pointer;transition:transform .15s;box-shadow:0 8px 22px rgba(43,58,92,.25)}
  button:hover{transform:translateY(-2px)}
  button:focus-visible,.cake:focus-visible{outline:3px solid var(--rose);outline-offset:3px}

  /* Letter */
  #letter{display:none;padding-top:70px;padding-bottom:120px}
  #letter.show{display:block}
  .stanza{margin-bottom:2.2rem;font-size:1.12rem;opacity:0;transform:translateY(14px);transition:opacity .9s ease,transform .9s ease}
  .stanza.in{opacity:1;transform:none}
  .stanza.big{font-style:italic;font-size:1.28rem;color:var(--rose)}
  .pet{font-family:'Caveat',cursive;font-size:1.9rem;color:var(--rose)}
  .sign{font-family:'Caveat',cursive;font-size:2.2rem;color:var(--gold);text-align:right}
  .pop{cursor:pointer;display:inline-block;transition:transform .2s}
  .pop:hover{transform:scale(1.3) rotate(-8deg)}
  .hidden{display:none!important}
  @media (prefers-reduced-motion:reduce){.fl,.elephant{animation:none}.stanza{transition:none;opacity:1;transform:none}}
</style>
</head>
<body>
<div id="pattern" aria-hidden="true"></div>
<div id="float" aria-hidden="true"></div>

<!-- 2. Opening -->
<section id="open" class="screen">
  <div class="card">
    <div class="script">Today is all about you</div>
    <h1>Happy Birthday,<br>Nanaluu 🐘</h1>
    <div class="arch"><img src="photo.jpg" alt="Us together"></div>
    <div class="cake" id="cake" role="button" tabindex="0" aria-label="Blow out the candle">🎂</div>
    <p class="hint" id="hint">Tap the cake and make a wish</p>
    <button id="btn" class="hidden">Read what I wrote for you</button>
  </div>
</section>

<!-- 3. Letter -->
<section id="letter">
  <p class="stanza">It's been three months since we met,<br>
  and the moment I first saw you, something felt different moment of Flying colours to me ❤️</p>

  <p class="stanza">Little did I know that your smile would become one of my favourite things,<br>
  your care would mean so much to me,<br>
  and your concern would make me feel special in ways I can't explain.</p>

  <p class="stanza">From those little smiles to our silly conversations,<br>
  from your care to those adorable names —<br>
  my <span class="pet">Dumbo</span>, my <span class="pet">Nanaluu</span> 😍</p>

  <p class="stanza">Somehow, in just three months,<br>
  you've become a beautiful part of my everyday thoughts.</p>

  <p class="stanza">I don't know what the future has written for us,<br>
  but if I could choose one beautiful possibility,<br>
  it would be to see you beside me <span class="pop">🙈</span><br>
  not just for a few moments,<br>
  but through all the little and big moments life has waiting for us.</p>

  <p class="stanza">Maybe some feelings are too precious to say directly 😊<br>
  So, for now, I'll just say this…</p>

  <p class="stanza big">I'm really glad our paths crossed. And if life ever gives me the choice,
  I'd love for our story to become something that lasts forever. ❤️✨</p>

</section>

<script>
  const $ = id => document.getElementById(id);

  /* Soft elephant pattern in the background (like her kurta) */
  const tile = "<svg xmlns='http://www.w3.org/2000/svg' width='140' height='140'><text x='22' y='52' font-size='30' opacity='.13'>🐘</text><text x='88' y='118' font-size='22' opacity='.1'>🐘</text></svg>";
  $('pattern').style.backgroundImage = "url(\"data:image/svg+xml," + encodeURIComponent(tile) + "\")";

  /* Floating elephants & hearts */
  const icons = ['🐘','🤍','💙','🐘','✨'];
  function spawn(){
    const e = document.createElement('span');
    e.className = 'fl';
    e.textContent = icons[Math.floor(Math.random()*icons.length)];
    e.style.left = Math.random()*100 + 'vw';
    e.style.fontSize = (14 + Math.random()*20) + 'px';
    e.style.animationDuration = (8 + Math.random()*7) + 's';
    $('float').appendChild(e);
    setTimeout(() => e.remove(), 16000);
  }
  setInterval(spawn, 900);

  /* Cake */
  function blow(){
    $('hint').textContent = 'Wish made 🌟 I hope it comes true';
    $('btn').classList.remove('hidden');
    for(let i=0;i<20;i++) setTimeout(spawn, i*60);
  }
  $('cake').addEventListener('click', blow);
  $('cake').addEventListener('keydown', e => { if(e.key==='Enter'||e.key===' '){e.preventDefault();blow();} });

  /* Letter */
  $('btn').addEventListener('click', () => {
    $('letter').classList.add('show');
    $('letter').scrollIntoView({behavior:'smooth'});
    const io = new IntersectionObserver(es => es.forEach(e => {
      if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); }
    }), {threshold:.3});
    document.querySelectorAll('.stanza').forEach(s => io.observe(s));
  });
  document.querySelectorAll('.pop').forEach(p => p.addEventListener('click', () => {
    for(let i=0;i<10;i++) setTimeout(spawn, i*50);
  }));
</script>
</body>
</html>
