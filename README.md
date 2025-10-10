
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pregunta importante :)</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg-color-container: rgba(255, 250, 252, 0.96);
      --border-color: #ff6699;
      --bg-color-btn-si: #ff4da6;
      --bg-color-btn-si-hover: #ff80bf;
      --bg-color-btn-no: #5e3566;
      --bg-color-btn-no-hover: #7a4b8a;
    }

    body {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Segoe UI", "Open Sans", "Helvetica Neue", sans-serif;
      display: grid;
      place-content: center;
      height: 100dvh;
      width: 100%;
      overflow: hidden;
      position: relative;
      background: linear-gradient(135deg, #fff9fb, #f8f0ff, #fff0f8);
      color: #5a2a5e;
    }

    /* === ELEMENTOS DECORATIVOS EN FONDO CLARO === */
    .star {
      position: absolute;
      color: #ffb3d9;
      font-size: 12px;
      opacity: 0.7;
      z-index: -1;
      animation: twinkle var(--duration, 4s) infinite ease-in-out;
      pointer-events: none;
    }

    .spark {
      position: absolute;
      width: 6px;
      height: 6px;
      background: radial-gradient(circle, #ff99cc, transparent);
      border-radius: 50%;
      box-shadow: 0 0 8px 2px #ff99cc;
      z-index: -1;
      animation: floatSpark var(--duration, 12s) infinite ease-in-out;
      opacity: 0.8;
      pointer-events: none;
    }

    .floating-heart {
      position: absolute;
      font-size: 18px;
      color: #ff6699;
      opacity: 0;
      z-index: -1;
      pointer-events: none;
      animation: floatHeart var(--duration, 16s) infinite ease-in-out;
      text-shadow: 0 0 6px rgba(255, 153, 204, 0.6);
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 0.9; }
    }

    @keyframes floatSpark {
      0% {
        transform: translateY(100vh) translateX(0);
        opacity: 0;
      }
      10% { opacity: 0.8; }
      90% { opacity: 0.6; }
      100% {
        transform: translateY(-100px) translateX(var(--dx, 0));
        opacity: 0;
      }
    }

    @keyframes floatHeart {
      0% {
        transform: translateY(100vh) rotate(0deg);
        opacity: 0;
      }
      10% { opacity: 0.85; }
      90% { opacity: 0.7; }
      100% {
        transform: translateY(-100px) rotate(360deg);
        opacity: 0;
      }
    }

    /* Contenedor principal */
    .box {
      width: 80vw;
      max-width: 400px;
      background: var(--bg-color-container);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 2px solid var(--border-color);
      border-radius: 20px;
      box-shadow: 0 8px 25px rgba(255, 102, 153, 0.3),
                  inset 0 0 12px rgba(255, 230, 240, 0.8);
      backdrop-filter: blur(6px);
      padding: 20px;
      position: relative;
      z-index: 10;
    }

    .box h1 {
      font-family: 'Pacifico', cursive;
      font-size: 26px;
      font-weight: 400;
      margin-top: 24px;
      margin-bottom: 14px;
      text-align: center;
      color: #ff4da6;
      text-shadow: 0 2px 6px rgba(255, 102, 153, 0.4);
      letter-spacing: 1px;
    }

    .box .btn-container {
      margin: 14px 0;
    }

    .box .btn-container .btn-si,
    .box .btn-container .btn-no {
      font-family: 'Pacifico', cursive;
      color: white;
      width: 95px;
      height: 50px;
      border: 2px solid var(--border-color);
      border-radius: 50px;
      font-size: 20px;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    }

    .box .btn-container .btn-si {
      background: var(--bg-color-btn-si);
      margin-right: 10px;
    }

    .box .btn-container .btn-si:hover {
      background: var(--bg-color-btn-si-hover);
      transform: scale(1.08);
      box-shadow: 0 0 18px rgba(255, 102, 153, 0.6);
    }

    .box .btn-container .btn-no {
      background: var(--bg-color-btn-no);
      margin-left: 10px;
    }

    .box .btn-container .btn-no:hover {
      background: var(--bg-color-btn-no-hover);
      transform: scale(1.05);
    }

    .box img {
      width: 90%;
      margin: 16px 0;
      border-radius: 14px;
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.08);
      transition: transform 0.4s ease;
    }

    .box img:hover {
      transform: scale(1.03);
    }

    .hidden {
      display: none !important;
    }

    /* Mensaje final adornado */
    #mensajeFinal {
      font-family: 'Pacifico', cursive;
      font-size: 28px;
      color: #ff3366;
      text-align: center;
      margin: 10px 0;
      text-shadow: 0 0 10px rgba(255, 102, 153, 0.7),
                   0 0 20px rgba(255, 200, 220, 0.8);
      animation: pulse 2s infinite alternate;
      opacity: 0;
      transform: scale(0.8);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    @keyframes pulse {
      from { transform: scale(1); }
      to { transform: scale(1.03); }
    }

    .show-message {
      opacity: 1 !important;
      transform: scale(1) !important;
    }

    /* Créditos fuera del cuadro */
    .credits {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      font-family: 'Pacifico', cursive;
      font-size: 17px;
      color: #ff6699;
      text-align: center;
      text-shadow: 0 1px 3px rgba(255, 102, 153, 0.5);
      letter-spacing: 1.2px;
      z-index: 5;
    }

    /* Corazones de explosión (claros y brillantes) */
    .heart-particle {
      position: absolute;
      font-size: 22px;
      color: #ff4da6;
      pointer-events: none;
      z-index: 20;
      animation: explode 1.3s forwards;
      text-shadow: 0 0 6px white, 0 0 10px #ffd6e8;
    }

    @keyframes explode {
      0% {
        transform: translate(0, 0) scale(0.4);
        opacity: 1;
      }
      100% {
        transform: translate(var(--tx), var(--ty)) scale(1.3);
        opacity: 0;
      }
    }

    /* Estilos para la galaxia */
    #galaxy-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 100;
      display: none;
      background: #000;
    }

    .galaxy-credits {
      position: fixed;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
      color: #ff66aa;
      font-size: 16px;
      text-shadow: 0 0 10px #ff3366, 0 0 20px #ff66aa;
      z-index: 999;
      font-family: Georgia, serif;
      letter-spacing: 1px;
      font-weight: bold;
      text-align: center;
      width: 100%;
    }

    .galaxy-player {
      position: fixed;
      bottom: 70px;
      left: 50%;
      transform: translateX(-50%);
      width: 90%;
      max-width: 600px;
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 10px;
      border: 2px solid #ff66aa;
      border-radius: 999px;
      background: rgba(20, 5, 20, 0.7);
      box-shadow: 0 0 15px #ff66aa, 0 0 30px #ff3366;
      z-index: 1000;
      color: #fff;
      font-size: 14px;
      font-family: Georgia, serif;
    }

    .galaxy-player button {
      background: 0 0;
      border: none;
      color: #ff66aa;
      font-size: 22px;
      cursor: pointer;
      filter: drop-shadow(0 0 6px #ff3366);
      transition: transform .2s;
      font-family: Georgia, serif;
    }

    .galaxy-player button:hover {
      transform: scale(1.2);
      filter: drop-shadow(0 0 10px #ff0033);
    }

    .galaxy-progress {
      flex-grow: 1;
      height: 14px;
      background: rgba(255, 102, 170, .2);
      border-radius: 999px;
      overflow: hidden;
      cursor: pointer;
      position: relative;
    }

    .galaxy-progress-bar {
      height: 100%;
      width: 0%;
      background: linear-gradient(270deg, #ff66aa, #ff3366, #ff0033, #ff66aa);
      background-size: 400% 400%;
      border-radius: 999px;
      box-shadow: 0 0 10px #ff66aa;
      animation: flowing 6s ease infinite;
    }

    @keyframes flowing {
      0% { background-position: 0 50% }
      50% { background-position: 100% 50% }
      100% { background-position: 0 50% }
    }

    .galaxy-time {
      min-width: 74px;
      text-align: right;
      font-size: 12px;
      color: #ff66aa;
      text-shadow: 0 0 5px #ff3366;
      font-family: Georgia, serif;
    }

    .menu-btn {
      position: fixed;
      top: 15px;
      left: 15px;
      z-index: 2000;
      background: rgba(20, 5, 20, 0.7);
      color: #ff66aa;
      border: 1px solid #ff66aa;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      font-size: 20px;
      cursor: pointer;
      outline: none;
      font-family: Georgia, serif;
      box-shadow: 0 0 8px #ff66aa;
    }

    .menu {
      position: fixed;
      top: 0;
      left: 0;
      width: 280px;
      height: 100vh;
      background: rgba(15, 5, 15, 0.95);
      color: #ff66aa;
      padding: 20px;
      transform: translateX(-100%);
      transition: transform 0.3s ease;
      z-index: 1500;
      overflow-y: auto;
      font-family: Georgia, serif;
      border-right: 2px solid #ff66aa;
    }

    .menu.active {
      transform: translateX(0);
    }

    .menu h3 {
      margin-top: 0;
      color: #ff66aa;
      text-shadow: 0 0 8px rgba(255, 102, 170, 0.5);
    }

    .menu label {
      display: block;
      margin: 12px 0;
      color: #ff99cc;
    }

    .menu select, .menu button {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      background: rgba(30, 10, 30, 0.8);
      color: #ff99cc;
      border: 1px solid #ff66aa;
      font-family: Georgia, serif;
      border-radius: 4px;
    }

    .close-menu {
      position: absolute;
      top: 15px;
      right: 15px;
      background: transparent;
      border: none;
      color: #ff66aa;
      font-size: 24px;
      cursor: pointer;
      font-family: Georgia, serif;
      text-shadow: 0 0 8px rgba(255, 102, 170, 0.7);
    }

    /* Estilo para la cuenta regresiva */
    #countdown {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Pacifico', cursive;
      font-size: 120px;
      color: #ff3366;
      text-shadow: 0 0 20px rgba(255, 102, 153, 0.8),
                   0 0 40px rgba(255, 200, 220, 0.9);
      z-index: 50;
      opacity: 0;
      pointer-events: none;
    }

    .show-countdown {
      opacity: 1 !important;
      animation: pulseCountdown 1s ease-out;
    }

    @keyframes pulseCountdown {
      0% { transform: scale(0.5); opacity: 0; }
      50% { transform: scale(1.2); opacity: 1; }
      100% { transform: scale(1); opacity: 1; }
    }
  </style>
</head>
<body>
  <!-- Contenedor principal de la pregunta -->
  <div class="box" id="question-box">
    <h1 id="title">¿Quieres ser mi novia? 🥺</h1>
    <div class="btn-container" id="containerBtns">
      <button class="btn-si" id="btnSi">Si</button>
      <button class="btn-no" id="btnNo">No</button>
    </div>
    <div id="mensajeFinal">Sabía que aceptarías.. ᵖᵉʳᵒ ᵉˢᵖᵉʳᵃ ᵘⁿ ᵐᵒᵐᵉⁿᵗᵒ❤️</div>
    <img src="" alt="gato" id="img" />
  </div>
  
  <!-- Créditos fuera del cuadro -->
  <div class="credits">By AnthZz Berrocal BerMatMods</div>

  <!-- Contenedor de la galaxia -->
  <div id="galaxy-container">
    <canvas id="c"></canvas>
    
    <!-- Menú hamburguesa -->
    <button class="menu-btn" id="menuBtn">☰</button>
    <div class="menu" id="menu">
      <button class="close-menu" id="closeMenu">×</button>
      <h3>⚙️ Configuración</h3>
      
      <label>
        Color de palabras flotantes:
        <select id="wordColorSelector">
          <option value="#ff66ff">#ff66ff (Rosa)</option>
          <option value="#ff99cc">#ff99cc (Rosa claro)</option>
          <option value="#ff3366">#ff3366 (Rosa intenso)</option>
          <option value="#ff0033">#ff0033 (Rosa profundo)</option>
          <option value="#ffccdd">#ffccdd (Rosa pastel)</option>
          <option value="#ffa0f8">#ffa0f8 (Lavanda rosado)</option>
          <option value="#c6a7ff">#c6a7ff (Violeta rosado)</option>
          <option value="#ff4444">#ff4444 (Rojo rosado)</option>
        </select>
      </label>

      <label>
        Color del brillo central (glow):
        <select id="glowColorSelector">
          <option value="255,102,170|255,51,102">Rosa clásico</option>
          <option value="255,153,204|255,51,153">Rosa suave</option>
          <option value="255,0,102|255,0,51">Rosa intenso</option>
          <option value="255,102,204|255,51,153">Rosa brillante</option>
        </select>
      </label>

      <h3>👨‍💻Dominio</h3>
      <p>Este proyecto fue Desarrollado por <strong>AnthZz Berrocal</strong> (➪𝐁𝐞𝐫𝐌𝐚𝐭𝐌𝐨𝐝𝐬𖤍).</p>
      <p>Galaxia Rosada V1.5</p>
      <p>✨F.A.M.A.✨</p>
    </div>

    <!-- Reproductor -->
    <div class="galaxy-player">
      <button id="play">▶️</button>
      <div class="galaxy-progress" id="progress"><div class="galaxy-progress-bar" id="progress-bar"></div></div>
      <div class="galaxy-time" id="time">0:00 / 0:00</div>
    </div>

    <!-- Créditos en la base -->
    <div class="galaxy-credits">By: AnthZz Berrocal BerMatMods</div>
  </div>

  <!-- Contenedor para la cuenta regresiva -->
  <div id="countdown"></div>

  <script>
    // === CREAR FONDO DECORATIVO CLARO ===
    function createLightDecor() {
      const body = document.body;
      const width = window.innerWidth;
      const height = window.innerHeight;

      // Estrellas (emojis)
      const stars = ['✨', '🌟', '⭐'];
      for (let i = 0; i < 80; i++) {
        const el = document.createElement('div');
        el.className = 'star';
        el.textContent = stars[Math.floor(Math.random() * stars.length)];
        el.style.left = `${Math.random() * 100}%`;
        el.style.top = `${Math.random() * 100}%`;
        el.style.setProperty('--duration', `${3 + Math.random() * 5}s`);
        el.style.fontSize = `${10 + Math.random() * 8}px`;
        body.appendChild(el);
      }

      // Chispas
      for (let i = 0; i < 20; i++) {
        const spark = document.createElement('div');
        spark.className = 'spark';
        spark.style.left = `${Math.random() * 100}%`;
        spark.style.setProperty('--duration', `${10 + Math.random() * 8}s`);
        spark.style.setProperty('--dx', `${(Math.random() - 0.5) * 250}px`);
        body.appendChild(spark);
      }

      // Corazones flotantes
      const hearts = ['❤️', '💖', '💗', '💕'];
      for (let i = 0; i < 10; i++) {
        const heart = document.createElement('div');
        heart.className = 'floating-heart';
        heart.textContent = hearts[Math.floor(Math.random() * hearts.length)];
        heart.style.left = `${Math.random() * 100}%`;
        heart.style.setProperty('--duration', `${14 + Math.random() * 8}s`);
        heart.style.fontSize = `${16 + Math.random() * 10}px`;
        body.appendChild(heart);
      }
    }

    // === EXPLOSIÓN DE CORAZONES AL TOCAR ===
    function createHeartExplosion(x, y) {
      const particleCount = 20;
      const hearts = ['❤️', '💖', '💗', '💕', '💘'];
      for (let i = 0; i < particleCount; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart-particle';
        heart.textContent = hearts[Math.floor(Math.random() * hearts.length)];
        heart.style.left = `${x}px`;
        heart.style.top = `${y}px`;

        const angle = Math.random() * Math.PI * 2;
        const distance = 50 + Math.random() * 160;
        const tx = Math.cos(angle) * distance;
        const ty = Math.sin(angle) * distance;

        heart.style.setProperty('--tx', `${tx}px`);
        heart.style.setProperty('--ty', `${ty}px`);

        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 1300);
      }
    }

    // Evento de clic global
    document.addEventListener('click', (e) => {
      createHeartExplosion(e.clientX, e.clientY);
    });

    // Iniciar decoración
    createLightDecor();

    // === TU CÓDIGO ORIGINAL (AJUSTADO PARA MENSAJE FINAL ADORNADO) ===
    const FRASES = [
      "Andale 🤕",
      "Dí que sii 😖",
      "Porfa 🥺",
      "Di si preciosa 😩",
      "No seas asi 💔",
    ];

    const TIMAGENES = [
      "https://i.postimg.cc/dtsK38Jj/2288551b0e48859fc3cd8f53834b6928.jpg",
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRIoL2oztE91lPQYpt85X2paDV6uemyee-Lrg&s",
      "https://i.pinimg.com/originals/ff/53/93/ff53935e6607a7fa92c7dce5e8748c88.png",
      "https://i.postimg.cc/DyvK0q7C/ebc109d64ce38ac17c107e6f6d7c0803.jpg",
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQzKL3Vr7nvWQAvuhdI_oSyCYY0LktNWABTFShtrXpRk76GpLxVKoZMPQeIj0rfGg4I3F8&usqp=CAU",
    ];
    const imagenPrincipio = "https://st2.depositphotos.com/1031481/9719/i/450/depositphotos_97193380-stock-photo-cat-brought-roses-as-a.jpg";
    const imageneFinal = "https://stickerly.pstatic.net/sticker_pack/RoQKd7eh2a6EUxtCfRXefw/PTDFFC/16/1673169483582.png";

    const $ = (e) => document.getElementById(e);

    const btnSi = $("btnSi");
    const btnNo = $("btnNo");
    const title = $("title");
    const img = $("img");
    const btnContainer = $("containerBtns");
    const mensajeFinalEl = $("mensajeFinal");
    const questionBox = $("question-box");
    const galaxyContainer = $("galaxy-container");
    const countdownEl = $("countdown");
    let contador = 0;

    const preloadImages = (images) => {
      images.forEach((src) => {
        const img = new Image();
        img.src = src.trim();
      });
    };

    preloadImages([imagenPrincipio, imageneFinal, ...TIMAGENES]);
    img.src = imagenPrincipio;

    btnSi.addEventListener("click", () => {
      // Mostrar mensaje y imagen final
      title.classList.add("hidden");
      img.src = imageneFinal;
      btnContainer.classList.add("hidden");
      mensajeFinalEl.classList.add("show-message");
      
      // Esperar 2 segundos antes de mostrar la cuenta regresiva
      setTimeout(() => {
        // Aplicar transición de desvanecimiento
        questionBox.classList.add("fade-out");
        
        // Mostrar la cuenta regresiva después de la transición
        setTimeout(() => {
          questionBox.style.display = "none";
          countdownEl.classList.add("show-countdown");
          
          // Iniciar la cuenta regresiva
          let count = 5;
          countdownEl.textContent = count;
          
          const countdownInterval = setInterval(() => {
            count--;
            if (count >= 0) {
              countdownEl.textContent = count;
              countdownEl.style.animation = 'none';
              setTimeout(() => {
                countdownEl.style.animation = 'pulseCountdown 1s ease-out';
              }, 10);
            } else {
              clearInterval(countdownInterval);
              countdownEl.classList.remove("show-countdown");
              
              // Mostrar la galaxia
              galaxyContainer.style.display = "block";
              
              // Iniciar la galaxia
              initGalaxy();
            }
          }, 1000);
        }, 1000);
      }, 2000);
    });

    btnNo.addEventListener("click", () => {
      if (FRASES.length > contador) {
        title.textContent = FRASES[contador];
        img.src = TIMAGENES[contador].trim();
      } else {
        contador = 0;
        title.textContent = FRASES[contador];
        img.src = TIMAGENES[contador].trim();
      }
      contador++;
      sizeControl(btnSi, "mas");
      sizeControl(btnSi, "menos");
    });

    function sizeControl(btn, size) {
      const currentSize = parseInt(window.getComputedStyle(btn).fontSize) || 18;
      const currentHeight = parseInt(window.getComputedStyle(btn).height) || 50;
      const currentWidth = parseInt(window.getComputedStyle(btn).width) || 95;
      let newFontSize, newHeightSize, newWidthSize;

      if (size === "mas") {
        newFontSize = currentSize + 5;
        newHeightSize = currentHeight + 5;
        newWidthSize = currentWidth + 5;
        if (newFontSize <= 70) {
          btn.style.fontSize = newFontSize + "px";
          btn.style.height = newHeightSize + "px";
          btn.style.width = newWidthSize + "px";
        }
      } else if (size === "menos") {
        newFontSize = currentSize - 5;
        newHeightSize = currentHeight - 5;
        newWidthSize = currentWidth - 5;
        if (newFontSize >= 12) {
          btn.style.fontSize = newFontSize + "px";
          btn.style.height = newHeightSize + "px";
          btn.style.width = newWidthSize + "px";
        }
      }
    }

    // === FUNCIÓN PARA INICIAR LA GALAXIA ROSADA ===
    function initGalaxy() {
      // Audio setup
      const audio = new Audio();
      audio.src = "https://www.dropbox.com/scl/fi/qfv28rqu6b36jwusao4x4/Love.MP3?rlkey=ptjd053374f028aa4jfcfrfxn&st=1j0j51eo&raw=1";
      audio.loop = true;
      
      const playBtn = document.getElementById("play");
      const progress = document.getElementById("progress");
      const progressBar = document.getElementById("progress-bar");
      const timeDisplay = document.getElementById("time");
      const menuBtn = document.getElementById("menuBtn");
      const menu = document.getElementById("menu");
      const closeMenu = document.getElementById("closeMenu");

      let isPlaying = false;

      function formatTime(e) {
        if (!isFinite(e)) return "0:00";
        return Math.floor(e / 60) + ":" + Math.floor(e % 60).toString().padStart(2, "0");
      }

      // Reproducir automáticamente al iniciar la galaxia
      audio.play().then(() => {
        playBtn.textContent = "⏸️";
        isPlaying = true;
      }).catch(e => {
        console.log("Reproducción automática bloqueada, mostrando botón de play");
        playBtn.textContent = "▶️";
        isPlaying = false;
      });

      playBtn.addEventListener("click", async () => {
        if (isPlaying) {
          audio.pause();
          playBtn.textContent = "▶️";
        } else {
          await audio.play();
          playBtn.textContent = "⏸️";
        }
        isPlaying = !isPlaying;
      });

      audio.addEventListener("timeupdate", () => {
        const percent = (audio.currentTime / audio.duration) * 100;
        progressBar.style.width = (isFinite(percent) ? percent : 0) + "%";
        timeDisplay.textContent = formatTime(audio.currentTime) + " / " + formatTime(audio.duration);
      });

      progress.addEventListener("click", (e) => {
        const rect = progress.getBoundingClientRect();
        const clickX = e.clientX - rect.left;
        const ratio = clickX / rect.width;
        if (isFinite(audio.duration)) audio.currentTime = ratio * audio.duration;
      });

      menuBtn.addEventListener("click", () => menu.classList.add("active"));
      closeMenu.addEventListener("click", () => menu.classList.remove("active"));

      // THREE.JS
      const canvas = document.getElementById("c");
      const renderer = new THREE.WebGLRenderer({ canvas, antialias: true });
      renderer.setPixelRatio(Math.min(window.devicePixelRatio || 1, 2));
      renderer.setSize(window.innerWidth, window.innerHeight);

      const scene = new THREE.Scene();
      const camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 5000);

      // Fondo rosado
      const loader = new THREE.TextureLoader();
      const nebulaTex = loader.load("https://raw.githubusercontent.com/mrdoob/three.js/dev/examples/textures/cube/space/px.jpg");
      
      // Crear un fondo rosado personalizado
      const bgCanvas = document.createElement('canvas');
      bgCanvas.width = 1024;
      bgCanvas.height = 1024;
      const bgCtx = bgCanvas.getContext('2d');
      
      // Degradado radial rosado
      const gradient = bgCtx.createRadialGradient(
        bgCanvas.width/2, bgCanvas.height/2, 0,
        bgCanvas.width/2, bgCanvas.height/2, bgCanvas.width/2
      );
      gradient.addColorStop(0, 'rgba(255, 102, 170, 0.1)');
      gradient.addColorStop(0.5, 'rgba(255, 51, 102, 0.05)');
      gradient.addColorStop(1, 'rgba(20, 5, 20, 0.3)');
      
      bgCtx.fillStyle = gradient;
      bgCtx.fillRect(0, 0, bgCanvas.width, bgCanvas.height);
      
      // Añadir estrellas rosadas
      for (let i = 0; i < 2000; i++) {
        const x = Math.random() * bgCanvas.width;
        const y = Math.random() * bgCanvas.height;
        const size = Math.random() * 2;
        const opacity = Math.random() * 0.8 + 0.2;
        
        bgCtx.beginPath();
        bgCtx.arc(x, y, size, 0, Math.PI * 2);
        bgCtx.fillStyle = `rgba(255, ${100 + Math.random() * 100}, ${150 + Math.random() * 50}, ${opacity})`;
        bgCtx.fill();
      }
      
      const bgTexture = new THREE.CanvasTexture(bgCanvas);
      scene.background = bgTexture;

      // Estrellas rosadas
      (function(e = 2000, t = 3000) {
        const n = new THREE.BufferGeometry();
        const a = new Float32Array(3 * e);
        const colors = new Float32Array(3 * e);
        for (let i = 0; i < e; i++) {
          const radius = t * (0.3 + 0.7 * Math.random());
          const theta = Math.random() * Math.PI * 2;
          const phi = Math.acos(2 * Math.random() - 1);
          a[3 * i + 0] = radius * Math.sin(phi) * Math.cos(theta);
          a[3 * i + 1] = radius * Math.cos(phi);
          a[3 * i + 2] = radius * Math.sin(phi) * Math.sin(theta);
          
          // Colores rosados para las estrellas
          const r = 1.0;
          const g = 0.4 + Math.random() * 0.4;
          const b = 0.6 + Math.random() * 0.4;
          colors[3 * i + 0] = r;
          colors[3 * i + 1] = g;
          colors[3 * i + 2] = b;
        }
        n.setAttribute("position", new THREE.BufferAttribute(a, 3));
        n.setAttribute("color", new THREE.BufferAttribute(colors, 3));
        scene.add(new THREE.Points(n, new THREE.PointsMaterial({ 
          size: 1.5, 
          vertexColors: true,
          depthWrite: false 
        })));
      })();

      // Núcleo con tu foto
      const coreGeo = new THREE.SphereGeometry(40, 64, 64);
      const coreTexture = loader.load("https://i.postimg.cc/fbh8Ph2R/1756434414.png");
      coreTexture.colorSpace = THREE.SRGBColorSpace;
      const coreMat = new THREE.MeshBasicMaterial({ map: coreTexture });
      const core = new THREE.Mesh(coreGeo, coreMat);
      scene.add(core);

      // Sprite central "TE AMO ❤️"
      function makeCenterTextTexture(text) {
        const canvas = document.createElement("canvas");
        canvas.width = 512; canvas.height = 512;
        const ctx = canvas.getContext("2d");
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        ctx.font = "bold 80px Georgia";
        ctx.textAlign = "center";
        ctx.textBaseline = "middle";
        ctx.fillStyle = "#ff0033";
        ctx.shadowColor = "#ff66aa";
        ctx.shadowBlur = 50;
        ctx.fillText(text, canvas.width / 2, canvas.height / 2);
        return new THREE.CanvasTexture(canvas);
      }

      const centerTex = makeCenterTextTexture("TE AMO ❤️");
      const centerMat = new THREE.SpriteMaterial({ map: centerTex, transparent: true });
      const centerSprite = new THREE.Sprite(centerMat);
      centerSprite.scale.set(60, 60, 1);
      centerSprite.position.set(0, 0, 0);
      centerSprite.renderOrder = 999;
      scene.add(centerSprite);

      // Glow (brillo central rosado)
      let glowMaterial;
      function updateGlow(inner = "255,102,170", outer = "255,51,102") {
        const size = 768;
        const canvas = document.createElement("canvas");
        canvas.width = canvas.height = size;
        const ctx = canvas.getContext("2d");
        const grad = ctx.createRadialGradient(size/2, size/2, 0.05*size, size/2, size/2, 0.5*size);
        grad.addColorStop(0, `rgba(${inner},0.9)`);
        grad.addColorStop(0.5, `rgba(${outer},0.5)`);
        grad.addColorStop(1, "rgba(0,0,0,0)");
        ctx.fillStyle = grad;
        ctx.fillRect(0, 0, size, size);
        const tex = new THREE.CanvasTexture(canvas);
        if (glowMaterial) glowMaterial.map = tex;
        else glowMaterial = new THREE.SpriteMaterial({ map: tex, transparent: true, depthWrite: false });
      }
      updateGlow();

      const glow = new THREE.Sprite(glowMaterial);
      glow.scale.set(500, 500, 1);
      scene.add(glow);

      // Anillos rosados
      function ringTexture(size = 768) {
        const canvas = document.createElement("canvas");
        canvas.width = canvas.height = size;
        const ctx = canvas.getContext("2d");
        ctx.translate(size/2, size/2);
        const inner = 0.34 * size;
        const outer = 0.49 * size;
        const grad = ctx.createRadialGradient(0,0,0.3*inner, 0,0,outer);
        grad.addColorStop(0, "rgba(255,200,220,1)");
        grad.addColorStop(0.3, "rgba(255,102,170,0.9)");
        grad.addColorStop(0.65, "rgba(255,51,102,0.6)");
        grad.addColorStop(1, "rgba(0,0,0,0)");
        ctx.fillStyle = grad;
        ctx.beginPath();
        ctx.arc(0,0,outer,0,Math.PI*2);
        ctx.arc(0,0,inner,0,Math.PI*2,true);
        ctx.closePath();
        ctx.fill();
        return new THREE.CanvasTexture(canvas);
      }

      const ring1 = new THREE.Mesh(new THREE.RingGeometry(60, 80, 128), new THREE.MeshBasicMaterial({ map: ringTexture(), transparent: true, side: THREE.DoubleSide }));
      const ring2 = new THREE.Mesh(new THREE.RingGeometry(85, 100, 128), new THREE.MeshBasicMaterial({ map: ringTexture(), transparent: true, side: THREE.DoubleSide, opacity: 0.6 }));
      ring1.rotation.x = ring2.rotation.x = Math.PI / 2;
      scene.add(ring1, ring2);

      // Palabras flotantes
      const baseWords = [
        "💖 Mi amor","🌞 Mi sol","🌎 Mi mundo","✨ Brillas","❤️ Te amo","🌌 Universo","👑 Reina","🌠 Estrella",
        "💫 Mi cielo","🔥 Siempre tú","🎶 Tu risa","🦋 Libertad","💎 Eres todo","🙏 Gracias","💕 Cariño",
        "🌹 Amor eterno","🤗 Abrazos","🌸 Esperanza","🌈 Alegría","🌟 Contigo","🧸 Ternura","🎁 Mi razón",
        "🌙 Mi destino","💌 Recuerdos","🕊️ Mi paz","🪐 Mi universo","🌊 Mi calma","💡 Mi luz","🍒 Dulzura",
        "🥰 Mi vida","🎇 Felicidad","🌻 Alegría","🌺 Mi flor","💜 Eternidad","🌟 Sueños","✨ Magia","🎵 Canción",
        "🔥 Pasión","⭐ Mi estrella","🌴 Mi paraíso","🌄 Amanecer","🌃 Noche contigo","🎉 Mi fiesta","💫 Inspiración",
        "🌷 Siempre juntos","🎀 Mi ternura","🍀 Mi fortuna","🪞 Mi reflejo"
      ];
      let WORDS = [];
      for (let i = 0; i < 6; i++) WORDS.push(...baseWords);

      const textGroup = new THREE.Group();
      scene.add(textGroup);

      function makeTextTexture(text, shadowColor) {
        const canvas = document.createElement("canvas");
        canvas.width = 512; canvas.height = 128;
        const ctx = canvas.getContext("2d");
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        ctx.font = "bold 60px Georgia";
        ctx.textAlign = "center";
        ctx.textBaseline = "middle";
        ctx.fillStyle = "#fff";
        ctx.shadowColor = shadowColor;
        ctx.shadowBlur = 30;
        ctx.fillText(text, canvas.width / 2, canvas.height / 2);
        return new THREE.CanvasTexture(canvas);
      }

      let currentWordColor = "#ff66ff";
      const wordColorSelector = document.getElementById("wordColorSelector");
      wordColorSelector.addEventListener("change", (e) => {
        currentWordColor = e.target.value;
        textGroup.clear();
        for (let i = 0; i < WORDS.length; i++) {
          const tex = makeTextTexture(WORDS[i], currentWordColor);
          const mat = new THREE.SpriteMaterial({ map: tex, transparent: true });
          const sprite = new THREE.Sprite(mat);
          sprite.scale.set(50, 16, 1);
          const phi = Math.acos(2 * Math.random() - 1);
          const theta = Math.random() * Math.PI * 2;
          const radius = 150 + 120 * Math.random();
          sprite.position.set(
            radius * Math.sin(phi) * Math.cos(theta),
            radius * Math.cos(phi),
            radius * Math.sin(phi) * Math.sin(theta)
          );
          sprite.userData = { phi, theta, radius, speed: 0.001 + 0.001 * Math.random() };
          textGroup.add(sprite);
        }
      });

      // Inicializar palabras
      for (let i = 0; i < WORDS.length; i++) {
        const tex = makeTextTexture(WORDS[i], currentWordColor);
        const mat = new THREE.SpriteMaterial({ map: tex, transparent: true });
        const sprite = new THREE.Sprite(mat);
        sprite.scale.set(50, 16, 1);
        const phi = Math.acos(2 * Math.random() - 1);
        const theta = Math.random() * Math.PI * 2;
        const radius = 150 + 120 * Math.random();
        sprite.position.set(
          radius * Math.sin(phi) * Math.cos(theta),
          radius * Math.cos(phi),
          radius * Math.sin(phi) * Math.sin(theta)
        );
        sprite.userData = { phi, theta, radius, speed: 0.001 + 0.001 * Math.random() };
        textGroup.add(sprite);
      }

      // Configuración del brillo (glow)
      const glowColorSelector = document.getElementById("glowColorSelector");
      glowColorSelector.addEventListener("change", (e) => {
        const [inner, outer] = e.target.value.split('|');
        updateGlow(inner, outer);
        glow.material.map = glowMaterial.map;
        glow.material.needsUpdate = true;
      });

      // Controles de cámara
      let dragging = false;
      let lastX = 0, lastY = 0;
      let autoRotate = true;
      let rotX = 0.2, rotY = 0;
      let targetDist = 300, currentDist = 300;

      function onDown(e) {
        dragging = true;
        autoRotate = false;
        const touch = e.touches ? e.touches[0] : e;
        lastX = touch.clientX;
        lastY = touch.clientY;
      }

      function onMove(e) {
        if (!dragging) return;
        const touch = e.touches ? e.touches[0] : e;
        const deltaX = touch.clientX - lastX;
        const deltaY = touch.clientY - lastY;
        rotY -= deltaX * 0.01;
        rotX = Math.max(-1.2, Math.min(1.2, rotX - deltaY * 0.01));
        lastX = touch.clientX;
        lastY = touch.clientY;
      }

      function onUp() {
        dragging = false;
        setTimeout(() => { autoRotate = true; }, 3000);
      }

      window.addEventListener("mousedown", onDown);
      window.addEventListener("mousemove", onMove);
      window.addEventListener("mouseup", onUp);
      window.addEventListener("touchstart", onDown, { passive: true });
      window.addEventListener("touchmove", onMove, { passive: false });
      window.addEventListener("touchend", onUp, { passive: true });

      window.addEventListener("wheel", (e) => {
        targetDist += 0.25 * e.deltaY;
        targetDist = Math.max(160, Math.min(600, targetDist));
        autoRotate = false;
        setTimeout(() => { autoRotate = true; }, 3000);
      }, { passive: true });

      let pinchStart = 0;
      window.addEventListener("touchmove", (e) => {
        if (e.touches && e.touches.length === 2) {
          e.preventDefault();
          const dx = e.touches[0].clientX - e.touches[1].clientX;
          const dy = e.touches[0].clientY - e.touches[1].clientY;
          const dist = Math.hypot(dx, dy);
          if (pinchStart) {
            targetDist += (pinchStart - dist) * 0.5;
            targetDist = Math.max(160, Math.min(600, targetDist));
            autoRotate = false;
            setTimeout(() => { autoRotate = true; }, 3000);
          }
          pinchStart = dist;
        }
      }, { passive: false });

      window.addEventListener("touchend", () => { pinchStart = 0; }, { passive: true });

      // Animación
      let t = 0;
      function tick() {
        requestAnimationFrame(tick);
        t += 0.01;

        if (autoRotate) {
          rotY += 0.002;
          rotX = 0.2 + 0.1 * Math.sin(t * 0.3);
        }

        ring1.rotation.z += 0.002;
        ring2.rotation.z -= 0.0015;

        const glowScale = 500 * (1 + 0.03 * Math.sin(0.4 * t));
        glow.scale.set(glowScale, glowScale, 1);

        const coreScale = 1 + 0.05 * Math.sin(3 * t);
        core.scale.set(coreScale, coreScale, coreScale);

        textGroup.children.forEach(sprite => {
          sprite.material.opacity = 0.8 + 0.2 * Math.sin(2 * t + sprite.userData.radius * 0.01);
          sprite.userData.theta += sprite.userData.speed;
          const { phi, theta, radius } = sprite.userData;
          sprite.position.x = radius * Math.sin(phi) * Math.cos(theta);
          sprite.position.z = radius * Math.sin(phi) * Math.sin(theta);
        });

        currentDist += 0.06 * (targetDist - currentDist);
        const cosX = Math.cos(rotX);
        const sinX = Math.sin(rotX);
        const cosY = Math.cos(rotY);
        const sinY = Math.sin(rotY);
        camera.position.set(currentDist * sinY * cosX, currentDist * sinX, currentDist * cosY * cosX);
        camera.lookAt(0, 0, 0);

        renderer.render(scene, camera);
      }

      tick();

      window.addEventListener("resize", () => {
        camera.aspect = window.innerWidth / window.innerHeight;
        camera.updateProjectionMatrix();
        renderer.setSize(window.innerWidth, window.innerHeight);
      });
    }

    // Cargar Three.js dinámicamente
    const script = document.createElement('script');
    script.src = 'https://cdn.jsdelivr.net/npm/three@0.148.0/build/three.min.js';
    document.head.appendChild(script);
  </script>
</body>
</html>
