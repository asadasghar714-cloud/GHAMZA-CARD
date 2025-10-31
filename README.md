
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Openable Card — For GUZIIIIIII</title>
  <style>
    :root{--bg:#ffae00;--card:#ff0000;--accent:#000000;--muted:#a6b0bd}
    *{box-sizing:border-box;font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, Arial}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#0048ff 0%, #000000 100%);color:#eef4fb}
    .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:28px}

    /* 3D flip card container */
    .scene{width:540px;height:340px;perspective:1200px}
    .card{width:100%;height:100%;position:relative;transform-style:preserve-3d;transition:transform .9s cubic-bezier(.2,.9,.2,1)}
    .card.open{transform:rotateY(-180deg)}
    .side{position:absolute;inset:0;border-radius:18px;padding:22px;backface-visibility:hidden;box-shadow:0 12px 40px rgba(2,6,23,0.6);display:flex;flex-direction:column}

    .front{background:linear-gradient(180deg, rgba(238, 4, 4, 0.02), rgba(255,255,255,0.01));align-items:center;justify-content:center}
    .back{background:linear-gradient(180deg, rgba(255, 0, 0, 0.02), rgba(255,255,255,0.00));transform:rotateY(180deg);gap:10px}

    h2{margin:0;font-size:22px;letter-spacing:1px}
    p.lead{color:var(--muted);margin-top:10px}

    .open-btn{margin-top:18px;padding:10px 16px;border-radius:12px;border:none;background:linear-gradient(90deg,var(--accent),#ff7aa0);color:#fff;font-weight:700;cursor:pointer}

    .messageBox{flex:1;display:flex;align-items:center;justify-content:center;padding:18px;border-radius:12px;border:1px dashed rgba(255,255,255,0.03);background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent)}
    .message{font-size:16px;line-height:1.45;text-align:center;white-space:pre-wrap}

    .small{font-size:13px;color:var(--muted)}

    /* decoration */
    .ribbon{position:absolute;left:-36px;top:18px;transform:rotate(-12deg);background:var(--accent);color:#fff;padding:8px 52px;border-radius:8px;box-shadow:0 8px 20px rgba(255,77,109,0.12);font-weight:700}

    @media (max-width:600px){.scene{width:92vw;height:340px}}
  </style>
</head>
<body>
  <div class="wrap">
    <div class="scene" role="region" aria-label="Openable greeting card">
      <div class="card" id="card">
        <div class="side front">
          <div class="ribbon">For MOTO</div>
          <div style="text-align:center;" aria-hidden="false">
            <h2>Tap to Open</h2>
            <p class="lead">A special message inside — click the button below to open the card.</p>
            <button class="open-btn" id="openBtn">Open Card ✨</button>
          </div>
        </div>

        <div class="side back">
          <div style="display:flex;justify-content:space-between;align-items:center">
            <div>
              <strong style="font-size:20px">ASAD KI GHAMZA</strong>
              <div class="small">Open ZANUUU</div>
            </div>
            <button class="open-btn" id="closeBtn">Close</button>
          </div>

          <div class="messageBox" aria-live="polite">
            <div class="message" id="messageContent">' GHAMZA MERIIIII SUNO SI MOTO I LIVE UH MORE THEN ANYING UMAHHHHHHHH MERI SARI DUNYA HA TUMMM. SHOLLY AP KO THOLA TANG KRNA KE LIE. MERAAAA GHAMZA NECK PR PAPI UMAHHHHH</div>
          </div>

          <div style="display:flex;justify-content:space-between;align-items:center;margin-top:10px">
            <div class="small">Made with LUBB — open KHOTA HEHE 😊</div>
            <div class="small" id="time"> </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script>
    const card = document.getElementById('card');
    const openBtn = document.getElementById('openBtn');
    const closeBtn = document.getElementById('closeBtn');
    const timeEl = document.getElementById('time');

    function updateTime(){const d=new Date();timeEl.textContent=d.toLocaleString();}
    updateTime(); setInterval(updateTime,60000);

    openBtn.addEventListener('click', ()=>{card.classList.add('open');
      // small confetti effect using DOM
      for(let i=0;i<16;i++){const el=document.createElement('div');el.textContent='✨';el.style.position='fixed';el.style.left=(20+Math.random()*60)+'%';el.style.top=(20+Math.random()*60)+'%';el.style.fontSize=(12+Math.random()*28)+'px';el.style.opacity=0.9;el.style.transition='transform 1.2s ease, opacity 1.2s linear';document.body.appendChild(el);requestAnimationFrame(()=>{el.style.transform='translateY(-120px) rotate('+ (Math.random()*90-45) +'deg)';el.style.opacity=0});setTimeout(()=>el.remove(),1400);}    
    });
    closeBtn.addEventListener('click', ()=>{card.classList.remove('open');});
  </script>
</body>
</html>
