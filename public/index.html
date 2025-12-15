<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Daniela y Steven</title>

<style>
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: #05030a;
  overflow: hidden;
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
}
canvas {
  display: block;
  width: 100vw;
  height: 100vh;
}

/* ✅ Texto abajo */
.love-text {
  position: fixed;
  left: 50%;
  bottom: 52px;
  transform: translateX(-50%);
  width: min(92vw, 900px);
  text-align: center;
  line-height: 1.25;
  padding: 14px 16px;
  border-radius: 14px;

  color: rgba(255,255,255,0.92);
  font-size: clamp(16px, 2.4vw, 28px);
  font-weight: 700;

  /* Glow */
  text-shadow:
    0 0 10px rgba(180,90,255,0.45),
    0 0 18px rgba(170,90,255,0.30);

  /* Fondo sutil */
  background: rgba(25, 10, 40, 0.22);
  backdrop-filter: blur(6px);

  opacity: 0;
  transition: opacity 600ms ease;
}

/* Cursor tipo máquina de escribir */
.love-text .cursor {
  display: inline-block;
  width: 10px;
  margin-left: 4px;
  border-right: 2px solid rgba(255,255,255,0.85);
  height: 1.1em;
  transform: translateY(2px);
  animation: blink 0.8s steps(2, start) infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}
</style>
</head>

<body>
<canvas id="canvas"></canvas>
<audio id="bgMusic" src="musica.mp3" preload="auto"></audio>

<!-- ✅ Texto abajo -->
<div id="loveText" class="love-text">
  <span id="typeTarget"></span>
</div>


<!-- ✅ Texto final -->
<div id="finalText" style="
  position: fixed;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  font-size: clamp(28px, 5vw, 60px);
  font-weight: 800;
  color: white;
  text-align: center;
  text-shadow:
    0 0 18px rgba(255,140,255,0.8),
    0 0 35px rgba(170,90,255,0.6);
  opacity: 0;
  transition: opacity 1200ms ease;
  pointer-events: none;
">
  
  <!-- Texto -->
  <span>¿Quieres ser mi novia?</span>

  <!-- Iconos abajo -->
  <div style="display:flex; gap:16px; margin-top:10px;">
    <img src="iconleon.png"
         alt="León"
         style="
           width: 60px;
           height: 60px;
           filter: drop-shadow(0 0 12px rgba(255,140,255,0.9));
         ">
    <img src="iconConeja.png"
         alt="Coneja"
         style="
           width: 60px;
           height: 60px;
           filter: drop-shadow(0 0 12px rgba(255,140,255,0.9));
         ">
  </div>

</div>


<script>
(() => {
  const canvas = document.getElementById("canvas");
  const ctx = canvas.getContext("2d");
const bgMusic = document.getElementById("bgMusic");

  /* ============================================================
     ⚙️ CONFIGURACIÓN DE RENDIMIENTO
     ============================================================ */
  const DPR_LIMIT = 1.5;
  const MAX_PARTICLES = 20;
  const PARTICLES_PER_POINT = 1;
  const LINE_SHADOW = 12;
  const PARTICLE_SHADOW = 8;
  const FADE_ALPHA = 0.28;
  const HEART_SPEED = 0.0010;

  const isMobile = /Android|iPhone|iPad/i.test(navigator.userAgent);

  /* ============================================================
     📐 RESIZE
     ============================================================ */
  function resize() {
    const dpr = Math.min(window.devicePixelRatio || 1, DPR_LIMIT);
    canvas.width = innerWidth * dpr;
    canvas.height = innerHeight * dpr;
    canvas.style.width = innerWidth + "px";
    canvas.style.height = innerHeight + "px";
    ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
  }
  window.addEventListener("resize", resize);
  resize();

  /* ============================================================
     ⭐ ESTRELLAS
     ============================================================ */
  const stars = [];
  function createStars(count = 350) {
    stars.length = 0;
    for (let i = 0; i < count; i++) {
      stars.push({
        x: Math.random() * innerWidth,
        y: Math.random() * innerHeight,
        r: Math.random() * 1.2,
        a: Math.random() * 0.8 + 0.1
      });
    }
  }
  createStars();



    /* ============================================================
     ☄️ ESTRELLAS FUGACES
     ============================================================ */
  const shootingStars = [];

  function spawnShootingStar() {
    if (shootingStars.length > 2) return;

    const startX = Math.random() * innerWidth * 0.8;
    const startY = Math.random() * innerHeight * 0.3;

    shootingStars.push({
      x: startX,
      y: startY,
      vx: Math.random() * 6 + 6,
      vy: Math.random() * 3 + 3,
      life: 60 + Math.random() * 40,
      alpha: 1
    });
  }

  function updateShootingStars() {
    for (let i = shootingStars.length - 1; i >= 0; i--) {
      const s = shootingStars[i];
      s.x += s.vx;
      s.y += s.vy;
      s.life--;
      s.alpha = s.life / 100;

      if (
        s.life <= 0 ||
        s.x > innerWidth + 100 ||
        s.y > innerHeight + 100
      ) {
        shootingStars.splice(i, 1);
      }
    }
  }

  function drawShootingStars() {
    ctx.save();
    ctx.globalCompositeOperation = "lighter";
    ctx.strokeStyle = "rgba(200,160,255,0.9)";
    ctx.shadowColor = "rgba(200,160,255,1)";
    ctx.shadowBlur = 12;
    ctx.lineWidth = 2;

    for (const s of shootingStars) {
      ctx.globalAlpha = s.alpha;
      ctx.beginPath();
      ctx.moveTo(s.x, s.y);
      ctx.lineTo(s.x - s.vx * 4, s.y - s.vy * 4);
      ctx.stroke();
    }

    ctx.restore();
    ctx.globalAlpha = 1;
  }


  function drawStars() {
    ctx.save();
    ctx.globalCompositeOperation = "source-over";
    ctx.fillStyle = "#bfa9ff";
    for (const s of stars) {
      ctx.globalAlpha = s.a;
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
      ctx.fill();
    }
    ctx.restore();
    ctx.globalAlpha = 1;
  }

  /* ============================================================
     💜 CORAZÓN PRECALCULADO
     ============================================================ */
  const heartPath = [];
  const STEPS = 600;

  for (let i = 0; i <= STEPS; i++) {
    const t = i / STEPS;
    const a = t * Math.PI * 2;
    const x = 16 * Math.pow(Math.sin(a), 3);
    const y = 13 * Math.cos(a)
            - 5 * Math.cos(2 * a)
            - 2 * Math.cos(3 * a)
            - Math.cos(4 * a);
    heartPath.push({ x: x / 18, y: -y / 20 });
  }

  /* ============================================================
     ✨ PARTÍCULAS
     ============================================================ */
  const particles = [];

  function spawnParticles(x, y) {
    const count = isMobile ? 2 : PARTICLES_PER_POINT;

    for (let i = 0; i < count; i++) {
      const ang = Math.random() * Math.PI * 2;
      const sp = Math.random() * 1.8 + 0.4;

      particles.push({
        x, y,
        vx: Math.cos(ang) * sp,
        vy: Math.sin(ang) * sp,
        life: Math.random() * 40 + 30,
        max: 0,
        r: Math.random() * 1.8 + 0.6,
        a: Math.random() * 0.6 + 0.4
      });

      particles[particles.length - 1].max =
        particles[particles.length - 1].life;
    }

    if (particles.length > MAX_PARTICLES) {
      particles.splice(0, particles.length - MAX_PARTICLES);
    }
  }

  function updateParticles() {
    for (let i = particles.length - 1; i >= 0; i--) {
      const p = particles[i];
      p.x += p.vx;
      p.y += p.vy;
      p.vx *= 0.985;
      p.vy *= 0.985;
      p.life--;

      if (p.life <= 0) particles.splice(i, 1);
    }
  }

  function drawParticles() {
    ctx.save();
    ctx.globalCompositeOperation = "lighter";
    ctx.shadowColor = "rgba(170,90,255,0.8)";
    ctx.shadowBlur = PARTICLE_SHADOW;

    for (const p of particles) {
      const k = p.life / p.max;
      ctx.globalAlpha = p.a * k;
      ctx.fillStyle = "rgba(160,90,255,1)";
      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fill();
    }

    ctx.restore();
    ctx.globalAlpha = 1;
  }

  /* ============================================================
     💖 TRAZO DEL CORAZÓN
     ============================================================ */
  let tProgress = 0;
  let drawnPoints = [];

  function drawHeart() {
    if (drawnPoints.length < 2) return;

    const cx = innerWidth * 0.5;
    const cy = innerHeight * 0.45;

    const grad = ctx.createLinearGradient(
      cx - 200, cy - 200,
      cx + 200, cy + 200
    );
    grad.addColorStop(0, "rgba(255,140,255,0.9)");
    grad.addColorStop(0.5, "rgba(170,90,255,0.9)");
    grad.addColorStop(1, "rgba(120,60,255,0.9)");

    ctx.save();
    ctx.globalCompositeOperation = "lighter";
    ctx.strokeStyle = grad;
    ctx.lineWidth = 3.5;
    ctx.lineCap = "round";
    ctx.lineJoin = "round";
    ctx.shadowColor = "rgba(180,90,255,0.9)";
    ctx.shadowBlur = LINE_SHADOW;

    ctx.beginPath();
    ctx.moveTo(drawnPoints[0].x, drawnPoints[0].y);
    for (let i = 1; i < drawnPoints.length; i++) {
      ctx.lineTo(drawnPoints[i].x, drawnPoints[i].y);
    }
    ctx.stroke();

    ctx.restore();
  }

  /* ============================================================
     💬 TEXTO TIPO "ESCRIBIENDO"
     ============================================================ */
  const loveBox = document.getElementById("loveText");
  const typeTarget = document.getElementById("typeTarget");

  const finalText = document.getElementById("finalText");

let showOnlyBackground = false;


  const message = "Mi amor quiero compartir el resto de mi vida contigo de verdad te amo mucho, eres la mejor persona que he conocido y me gustaria pedirte... ";
  let typingStarted = false;

  function startTyping() {
    typingStarted = true;
    loveBox.style.opacity = "1";

    let i = 0;
    const speedMs = 75; // velocidad de tipeo

    const timer = setInterval(() => {
      typeTarget.textContent += message[i] ?? "";
      i++;
      if (i >= message.length) {
  clearInterval(timer);
  setTimeout(showFinalQuestion, 4000);
}
    }, speedMs);
  }

  function showFinalQuestion() {
  showOnlyBackground = true;

  // Oculta texto inferior
  loveBox.style.opacity = "0";

  // Muestra texto final
  finalText.style.opacity = "1";
}


  /* ============================================================
     🔁 LOOP PRINCIPAL
     ============================================================ */
  function loop() {
    ctx.fillStyle = `rgba(5,3,10,${FADE_ALPHA})`;
    ctx.fillRect(0, 0, innerWidth, innerHeight);

    drawStars();
        // ☄️ Estrellas fugaces ocasionales
    if (Math.random() < 0.008) spawnShootingStar();

    updateShootingStars();
    drawShootingStars();

    if (showOnlyBackground) {
  requestAnimationFrame(loop);
  return;
}



    const centerX = innerWidth * 0.5;
    const centerY = innerHeight * 0.45;
    const scale = Math.min(innerWidth, innerHeight) * 0.22;

    tProgress += HEART_SPEED;

    // ✅ Cuando el corazón va por ~40% empezamos a escribir el texto
    if (!typingStarted && tProgress >= 1) startTyping();

    if (tProgress > 1) {
      tProgress = 0;
      drawnPoints = [];
      // Opcional: si querés que el texto se reinicie cada vez, descomenta:
      // typingStarted = false;
      // typeTarget.textContent = "";
      // loveBox.style.opacity = "0";
    }

    const idx = Math.floor(tProgress * STEPS);
    const p = heartPath[idx];

    const x = centerX + p.x * scale;
    const y = centerY + p.y * scale;

    drawnPoints.push({ x, y });
    spawnParticles(x, y);

    drawHeart();
    updateParticles();
    drawParticles();

    requestAnimationFrame(loop);
  }

  ctx.fillStyle = "#05030a";
  ctx.fillRect(0, 0, innerWidth, innerHeight);
  requestAnimationFrame(loop);
})();


let musicStarted = false;

function startMusic() {
  if (musicStarted) return;
  musicStarted = true;

  bgMusic.volume = 1;
  bgMusic.play().catch(() => {});
}

window.addEventListener("click", startMusic);
window.addEventListener("touchstart", startMusic);

</script>
</body>
</html>
