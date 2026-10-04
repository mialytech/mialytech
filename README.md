# mialytech
<!DOCTYPE html>
<html lang="pt-BR" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Cyber Quest: TI & Support Portfolio</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&family=Plus+Jakarta+Sans:wght@500;700;800&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        pixel: ['"Press Start 2P"', 'monospace'],
                        vt: ['"VT323"', 'monospace'],
                        sans: ['"Plus Jakarta Sans"', 'sans-serif'],
                    },
                    colors: {
                        cyber: {
                            bg: '#0a0612',
                            panel: '#150c26',
                            border: '#ff3b94',
                            pink: '#ff3b94',
                            magenta: '#e00070',
                            purple: '#9d4edd',
                            lavender: '#e0aaff',
                            cyan: '#00f5d4',
                            yellow: '#ffee38',
                            dark: '#110920'
                        }
                    },
                    boxShadow: {
                        'arcade-pink': '0 0 15px rgba(255, 59, 148, 0.6), inset 0 0 10px rgba(255, 59, 148, 0.4)',
                        'arcade-cyan': '0 0 15px rgba(0, 245, 212, 0.6)',
                        'glow-pink': '0 0 30px rgba(255, 59, 148, 0.4)'
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #0a0612;
            color: #f8f8f2;
            font-family: 'VT323', monospace;
            overflow-x: hidden;
            user-select: none;
            -webkit-user-select: none;
            touch-action: manipulation;
        }

        /* CRT Scanline Shader Overlay */
        .crt-overlay {
            background: linear-gradient(
                rgba(18, 16, 16, 0) 50%, 
                rgba(0, 0, 0, 0.25) 50%
            ), linear-gradient(
                90deg,
                rgba(255, 0, 0, 0.03),
                rgba(0, 255, 0, 0.01),
                rgba(0, 0, 255, 0.03)
            );
            background-size: 100% 4px, 6px 100%;
            pointer-events: none;
        }

        /* Marquee Animation */
        @keyframes marquee {
            0% { transform: translateX(0%); }
            100% { transform: translateX(-50%); }
        }

        .animate-marquee {
            display: flex;
            width: max-content;
            animation: marquee 14s linear infinite;
        }

        /* Glowing text effect */
        .text-glow-pink {
            text-shadow: 0 0 8px #ff3b94, 0 0 16px #e00070;
        }
        .text-glow-cyan {
            text-shadow: 0 0 8px #00f5d4, 0 0 16px #00bbf9;
        }

        /* Custom Pixel Buttons - FIXED Invalid border-color CSS Property */
        .pixel-btn {
            box-shadow: 3px 3px 0 currentColor, inset -2px -2px 0 rgba(0,0,0,0.4);
            transition: all 0.1s ease;
        }
        .pixel-btn:active {
            transform: translate(2px, 2px);
            box-shadow: 1px 1px 0 currentColor;
        }

        /* Floating Pixel Particles */
        @keyframes floatUp {
            0% { transform: translateY(0) scale(1); opacity: 1; }
            100% { transform: translateY(-80px) scale(0.6); opacity: 0; }
        }
        .float-particle {
            position: absolute;
            animation: floatUp 2.5s ease-out forwards;
            pointer-events: none;
            font-family: 'Press Start 2P', monospace;
            font-size: 10px;
        }

        canvas {
            image-rendering: pixelated;
            image-rendering: crisp-edges;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #0a0612; }
        ::-webkit-scrollbar-thumb { background: #ff3b94; border-radius: 3px; }
    .hidden { display: none !important; }
        body { padding-top: env(safe-area-inset-top, 0px); padding-bottom: env(safe-area-inset-bottom, 0px); }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between relative selection:bg-cyber-pink selection:text-white">

    <!-- CRT Visual Effect Layer -->
    <div id="crt-layer" class="crt-overlay fixed inset-0 z-30 transition-opacity duration-300"></div>

    <!-- BACKGROUND ANIMATED MARQUEE -->
    <header class="w-full bg-cyber-panel border-b-2 border-cyber-pink/60 py-2 overflow-hidden z-20">
        <div class="animate-marquee whitespace-nowrap text-lg tracking-wider text-cyber-lavender flex items-center gap-8 font-vt">
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
            <span class="flex items-center gap-2 pr-12"><span class="text-cyber-pink">🎮</span> SEJA BEM VINDO AO MEU PORTIFOLIO</span>
        </div>
    </header>

    <!-- MAIN GAME SUITE CONTAINER -->
    <main class="flex-1 flex flex-col items-center justify-center p-2 sm:p-4 md:p-6 z-10 max-w-6xl mx-auto w-full">

        <!-- ARCADE HUD HEADER BAR -->
        <div class="w-full bg-cyber-panel border-2 border-cyber-pink rounded-t-xl p-3 flex flex-wrap items-center justify-between gap-3 shadow-arcade-pink font-pixel text-xs">
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded bg-cyber-bg border border-cyber-pink flex items-center justify-center text-cyber-pink text-lg shadow-inner">
                    <span class="">🥷</span>
                </div>
                <div>
                    <div class="text-cyber-pink text-glow-pink font-bold flex items-center gap-2">
                        <span id="player-name-display">DEV / ANALISTA DE TI</span>
                        <span class="text-[9px] bg-cyber-purple/60 px-1.5 py-0.5 rounded text-white">LVL 21</span>
                    </div>
                    <div class="text-[10px] text-cyber-lavender font-vt text-base">Especialista em Suporte & Infraestrutura</div>
                </div>
            </div>

            <!-- XP & Health Bars -->
            <div class="flex items-center gap-4 text-xs font-vt text-lg">
                <div class="flex flex-col">
                    <span class="text-cyber-cyan text-xs font-pixel flex justify-between">HP <span>100/100</span></span>
                    <div class="w-28 sm:w-36 h-3 bg-cyber-bg border border-cyber-cyan rounded-sm p-0.5">
                        <div class="h-full bg-cyber-cyan w-full rounded-sm"></div>
                    </div>
                </div>

                <div class="flex flex-col">
                    <span class="text-cyber-yellow text-xs font-pixel flex justify-between">XP <span id="xp-counter">1500</span></span>
                    <div class="w-28 sm:w-36 h-3 bg-cyber-bg border border-cyber-yellow rounded-sm p-0.5">
                        <div id="xp-bar" class="h-full bg-cyber-yellow w-[75%] rounded-sm transition-all duration-300"></div>
                    </div>
                </div>
            </div>

            <!-- Retro Controls / CRT Toggle -->
            <div class="flex items-center gap-2 font-vt text-lg">
                <button onclick="toggleAudio()" id="audio-btn" class="px-2 py-1 bg-cyber-bg border border-cyber-pink hover:bg-cyber-pink/20 rounded text-cyber-pink transition-all flex items-center gap-1">
                    <span class="" id="audio-icon">🔊</span>
                    <span class="hidden sm:inline">SOM</span>
                </button>
                <button onclick="toggleCRT()" class="px-2 py-1 bg-cyber-bg border border-cyber-cyan hover:bg-cyber-cyan/20 rounded text-cyber-cyan transition-all flex items-center gap-1">
                    <span class="">📺</span>
                    <span class="hidden sm:inline">CRT</span>
                </button>
            </div>
        </div>

        <!-- ARCADE SCREEN CANVAS CONTAINER -->
        <div class="w-full bg-cyber-bg border-2 border-t-0 border-cyber-pink rounded-b-xl overflow-hidden relative shadow-glow-pink flex flex-col items-center justify-center p-2">
            
            <!-- Floating Interaction Helper Prompt -->
            <div id="action-prompt" onclick="triggerCurrentStation()" class="absolute top-4 bg-cyber-panel/90 border border-cyber-yellow text-cyber-yellow px-4 py-1.5 rounded-full font-pixel text-xs animate-bounce shadow-lg z-20 hidden flex items-center gap-2">
                <span class="text-cyber-yellow">👆</span>
                <span id="prompt-text">PRESSIONE [ESPAÇO] OU CLIQUE PARA INTERAGIR</span>
            </div>

            <!-- Canvas Viewport -->
            <canvas id="gameCanvas" class="w-full max-w-[800px] h-auto aspect-[2/1] bg-cyber-bg rounded border border-cyber-purple/40 cursor-pointer"></canvas>

            <!-- Quick Station Navigation Buttons for Mobile/Mouse Clicking -->
            <div class="w-full max-w-[800px] mt-2 grid grid-cols-2 sm:grid-cols-5 gap-1.5 font-pixel text-[10px]">
                <button onclick="moveToStation('terminal')" class="px-2 py-2 bg-cyber-panel border border-cyber-pink text-cyber-pink hover:bg-cyber-pink hover:text-black transition-all rounded text-center">
                    <span class="block text-sm mb-1">💻</span> 1.HABILIDADES
                </button>
                <button onclick="moveToStation('server')" class="px-2 py-2 bg-cyber-panel border border-cyber-purple text-cyber-purple hover:bg-cyber-purple hover:text-white transition-all rounded text-center">
                    <span class="block text-sm mb-1">🖥️</span> 2.INFRA / REDES
                </button>
                <button onclick="moveToStation('forensics')" class="px-2 py-2 bg-cyber-panel border border-cyber-cyan text-cyber-cyan hover:bg-cyber-cyan hover:text-black transition-all rounded text-center">
                    <span class="block text-sm mb-1">🛡️</span> 3.SEGURANÇA
                </button>
                <button onclick="moveToStation('arcade')" class="px-2 py-2 bg-cyber-panel border border-cyber-yellow text-cyber-yellow hover:bg-cyber-yellow hover:text-black transition-all rounded text-center">
                    <span class="block text-sm mb-1">🎮</span> 4.MINI-GAME
                </button>
                <button onclick="moveToStation('comms')" class="px-2 py-2 bg-cyber-panel border border-emerald-400 text-emerald-400 hover:bg-emerald-400 hover:text-black transition-all rounded text-center col-span-2 sm:col-span-1">
                    <span class="block text-sm mb-1">💬</span> 5.CONTATO
                </button>
            </div>

        </div>

    </main>

    <!-- INTERACTIVE STATION MODAL DIALOGS -->
    <div id="modal-overlay" onclick="if(event.target===this)closeModal()" class="fixed inset-0 bg-black/80 backdrop-blur-md z-40 hidden flex items-center justify-center p-3">
        
        <div class="w-full max-w-2xl bg-cyber-panel border-2 border-cyber-pink rounded-xl shadow-arcade-pink overflow-hidden flex flex-col max-h-[90vh]">
            
            <!-- Modal Header -->
            <div class="bg-cyber-bg px-4 py-3 border-b border-cyber-pink flex items-center justify-between font-pixel text-xs">
                <div class="flex items-center gap-2 text-cyber-pink text-glow-pink">
                    <span id="modal-icon" class="">💻</span>
                    <span id="modal-title">ESTAÇÃO DE TRABALHO</span>
                </div>
                <button onclick="closeModal()" class="w-6 h-6 rounded bg-cyber-pink text-black font-bold flex items-center justify-center hover:bg-white transition-all">✕</button>
            </div>

            <!-- Modal Body Content -->
            <div id="modal-body" class="p-4 sm:p-6 overflow-y-auto font-vt text-lg sm:text-xl leading-relaxed text-gray-200">
                <!-- Content injected dynamically via JS -->
            </div>

            <!-- Modal Footer -->
            <div class="bg-cyber-bg px-4 py-2 border-t border-cyber-pink/40 flex justify-end font-pixel text-xs">
                <button onclick="closeModal()" class="px-4 py-2 bg-cyber-pink text-black font-bold rounded hover:bg-white transition-all">
                    [FECHAR ESTAÇÃO]
                </button>
            </div>

        </div>

    </div>

    <!-- MINI-GAME MODAL -->
    <div id="minigame-modal" onclick="if(event.target===this)closeMiniGame()" class="fixed inset-0 bg-black/90 backdrop-blur-md z-50 hidden flex items-center justify-center p-3">
        <div class="w-full max-w-xl bg-cyber-panel border-2 border-cyber-yellow rounded-xl shadow-arcade-cyan p-4 flex flex-col items-center text-center font-vt">
            <div class="font-pixel text-sm text-cyber-yellow mb-2 text-glow-cyan">⚡ DESAFIO DA SERVIDORA: FIX THE BUG!</div>
            <p class="text-gray-300 text-lg mb-4">Clique nos cabos com falha antes que o servidor superaqueça totalmente!</p>

            <!-- Mini game stats -->
            <div class="flex justify-between w-full max-w-md font-pixel text-xs text-cyber-lavender mb-3">
                <span>PONTOS: <span id="mg-score" class="text-cyber-yellow">0</span></span>
                <span>TEMPO: <span id="mg-timer" class="text-cyber-pink">15</span>s</span>
            </div>

            <!-- Cable grid game arena -->
            <div id="mg-grid" class="grid grid-cols-3 gap-3 w-full max-w-md h-64 bg-cyber-bg p-3 border border-cyber-yellow/40 rounded">
                <!-- Cable cards injected dynamically -->
            </div>

            <button onclick="closeMiniGame()" class="mt-4 px-6 py-2 bg-cyber-yellow text-black font-pixel text-xs rounded hover:bg-white transition-all">
                SAIR DO DESAFIO
            </button>
        </div>
    </div>

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-6 right-6 bg-cyber-pink text-black font-pixel text-xs px-4 py-3 rounded-lg shadow-arcade-pink flex items-center gap-2 transform translate-y-20 opacity-0 transition-all duration-300 z-50">
        <span class="text-sm">🏆</span>
        <span id="toast-text">Conquista Desbloqueada!</span>
    </div>

    <!-- AUDIO & GAME LOGIC -->
    <script>
        // --- 1. WEB AUDIO API CHIPTUNE SOUND GENERATOR ---
        let audioCtx = null;
        let soundEnabled = true;

        function initAudio() {
            if (!audioCtx) {
                const AudioContextClass = window.AudioContext || window.webkitAudioContext;
                if (AudioContextClass) {
                    audioCtx = new AudioContextClass();
                }
            }
            if (audioCtx && audioCtx.state === 'suspended') {
                audioCtx.resume();
            }
        }

        function playSound(type) {
            if (!soundEnabled) return;
            initAudio();
            if (!audioCtx) return;

            try {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.connect(gain);
                gain.connect(audioCtx.destination);

                const now = audioCtx.currentTime;

                if (type === 'step') {
                    osc.type = 'triangle';
                    osc.frequency.setValueAtTime(140, now);
                    osc.frequency.exponentialRampToValueAtTime(40, now + 0.05);
                    gain.gain.setValueAtTime(0.05, now);
                    gain.gain.linearRampToValueAtTime(0, now + 0.05);
                    osc.start(now);
                    osc.stop(now + 0.05);
                } else if (type === 'interact') {
                    osc.type = 'square';
                    osc.frequency.setValueAtTime(400, now);
                    osc.frequency.setValueAtTime(800, now + 0.08);
                    gain.gain.setValueAtTime(0.1, now);
                    gain.gain.linearRampToValueAtTime(0, now + 0.18);
                    osc.start(now);
                    osc.stop(now + 0.18);
                } else if (type === 'score') {
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(523.25, now); // C5
                    osc.frequency.setValueAtTime(659.25, now + 0.08); // E5
                    osc.frequency.setValueAtTime(783.99, now + 0.16); // G5
                    gain.gain.setValueAtTime(0.15, now);
                    gain.gain.linearRampToValueAtTime(0, now + 0.3);
                    osc.start(now);
                    osc.stop(now + 0.3);
                }
            } catch (e) {
                console.warn("Audio playback interrupted:", e);
            }
        }

        function toggleAudio() {
            soundEnabled = !soundEnabled;
            if (soundEnabled) initAudio();
            const icon = document.getElementById('audio-icon');
            icon.textContent = soundEnabled ? '🔊' : '🔇';
            showToast(soundEnabled ? "Som Retro Ativado! 🔊" : "Som Desativado 🔇");
        }

        function toggleCRT() {
            const crt = document.getElementById('crt-layer');
            crt.classList.toggle('opacity-0');
            showToast("Efeito CRT Alternado! 📺");
        }

        // --- 2. CANVAS TOP-DOWN RPG ENGINE ---
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');

        // Fixed Canvas Game World Resolution
        canvas.width = 800;
        canvas.height = 400;

        // Player state
        const player = {
            x: 400,
            y: 280,
            width: 24,
            height: 32,
            speed: 3.5,
            direction: 'down',
            animFrame: 0,
            animTimer: 0
        };

        // Input state
        const keys = {
            up: false,
            down: false,
            left: false,
            right: false
        };

        // Interactive Stations in the Room
        const stations = [
            {
                id: 'terminal',
                name: 'Terminal de Código',
                subtitle: 'Acesse minhas Habilidades de TI',
                x: 120, y: 100, width: 80, height: 60,
                color: '#ff3b94', icon: 'fa-terminal',
                activated: false
            },
            {
                id: 'server',
                name: 'Racks de Servidores',
                subtitle: 'Infraestrutura, Redes & Servidores',
                x: 320, y: 100, width: 100, height: 60,
                color: '#9d4edd', icon: 'fa-server',
                activated: false
            },
            {
                id: 'forensics',
                name: 'Estação de Segurança',
                subtitle: 'Segurança da Informação & Log Analysis',
                x: 560, y: 100, width: 80, height: 60,
                color: '#00f5d4', icon: 'fa-shield-halved',
                activated: false
            },
            {
                id: 'arcade',
                name: 'Arcade do Servidor',
                subtitle: 'Mini-Game: Fix the Cables!',
                x: 180, y: 280, width: 70, height: 70,
                color: '#ffee38', icon: 'fa-gamepad',
                activated: false
            },
            {
                id: 'comms',
                name: 'Centro de Comunicações',
                subtitle: 'Entre em Contato / Redes Sociais',
                x: 580, y: 280, width: 80, height: 60,
                color: '#34d399', icon: 'fa-comments',
                activated: false
            }
        ];

        let currentActiveStation = null;
        const clamp = (v, a, b) => Math.max(a, Math.min(b, v));
        let target = null, pendingStation = null, lastT = performance.now();
        const modalOpen = () => !document.getElementById('modal-overlay').classList.contains('hidden') ||
                                !document.getElementById('minigame-modal').classList.contains('hidden');
        let totalXP = 1500;

        // Player Particle Effects
        let floatingParticles = [];

        function spawnParticle(text, x, y, color) {
            floatingParticles.push({
                text: text,
                x: x,
                y: y,
                color: color,
                opacity: 1,
                life: 60
            });
        }

        // Main Draw Loop
        function renderGame(now) {
            now = now || performance.now();
            const dt = Math.min((now - lastT) / 16.667, 3); lastT = now;
            // Clear Screen (Dark Obsidian Floor)
            ctx.fillStyle = '#0a0612';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // Draw Cyber Tile Floor Grid
            ctx.strokeStyle = 'rgba(255, 59, 148, 0.08)';
            ctx.lineWidth = 1;
            const tileSize = 40;
            for (let x = 0; x < canvas.width; x += tileSize) {
                ctx.beginPath();
                ctx.moveTo(x, 0);
                ctx.lineTo(x, canvas.height);
                ctx.stroke();
            }
            for (let y = 0; y < canvas.height; y += tileSize) {
                ctx.beginPath();
                ctx.moveTo(0, y);
                ctx.lineTo(canvas.width, y);
                ctx.stroke();
            }

            // Draw Decorative Cables on Floor
            ctx.strokeStyle = '#e00070';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.moveTo(160, 160); ctx.lineTo(160, 220); ctx.lineTo(360, 220); ctx.lineTo(360, 160);
            ctx.stroke();

            ctx.strokeStyle = '#00f5d4';
            ctx.beginPath();
            ctx.moveTo(600, 160); ctx.lineTo(600, 240); ctx.lineTo(215, 240); ctx.lineTo(215, 280);
            ctx.stroke();

            // Draw Stations
            stations.forEach(st => {
                // Station Shadow / Glow Base
                ctx.fillStyle = st.color + '22';
                ctx.fillRect(st.x - 5, st.y - 5, st.width + 10, st.height + 10);

                // Station Body
                ctx.fillStyle = '#150c26';
                ctx.fillRect(st.x, st.y, st.width, st.height);

                ctx.strokeStyle = st.color;
                ctx.lineWidth = 2;
                ctx.strokeRect(st.x, st.y, st.width, st.height);

                // Station LED Screen Details
                ctx.fillStyle = st.color;
                ctx.fillRect(st.x + 8, st.y + 8, st.width - 16, 16);

                // Animated Blink Lights
                if (Math.floor(Date.now() / 300) % 2 === 0) {
                    ctx.fillStyle = '#ffee38';
                    ctx.fillRect(st.x + st.width - 12, st.y + st.height - 12, 6, 6);
                }

                // Station Label Header
                ctx.font = '10px "Press Start 2P"';
                ctx.fillStyle = st.color;
                ctx.textAlign = 'center';
                ctx.fillText(st.id.toUpperCase(), st.x + st.width / 2, st.y - 12);
            });

            // Movimento (independente da taxa de quadros, diagonal normalizada)
            let dx = (keys.right ? 1 : 0) - (keys.left ? 1 : 0);
            let dy = (keys.down ? 1 : 0) - (keys.up ? 1 : 0);
            if (modalOpen()) { dx = 0; dy = 0; }
            if (dx || dy) {
                target = null; pendingStation = null;
                const len = Math.hypot(dx, dy); dx /= len; dy /= len;
                if (dy) player.direction = dy > 0 ? 'down' : 'up';
                if (dx) player.direction = dx > 0 ? 'right' : 'left';
            } else if (target && !modalOpen()) {
                const tx = target.x - player.x, ty = target.y - player.y, d = Math.hypot(tx, ty);
                if (d <= player.speed * dt) {
                    player.x = target.x; player.y = target.y; target = null;
                    if (pendingStation) { const st = pendingStation; pendingStation = null; triggerStation(st); }
                } else { dx = tx / d; dy = ty / d; }
            }
            const moving = !!(dx || dy);
            if (moving) {
                player.x = clamp(player.x + dx * player.speed * dt, 20, canvas.width - 20);
                player.y = clamp(player.y + dy * player.speed * dt, 40, canvas.height - 30);
                player.animTimer++;
                if (player.animTimer % 8 === 0) {
                    player.animFrame = (player.animFrame + 1) % 4;
                    playSound('step');
                }
            }

            // Draw Female Tech Avatar Sprite (Pixel Art style)
            drawPlayerSprite(player.x, player.y, player.direction, player.animFrame);

            // Check Proximity to Stations
            currentActiveStation = null;
            stations.forEach(st => {
                const dist = Math.hypot((player.x - (st.x + st.width / 2)), (player.y - (st.y + st.height / 2)));
                if (dist < 65) {
                    currentActiveStation = st;

                    // Draw Interaction Indicator
                    ctx.fillStyle = '#ffee38';
                    ctx.font = '12px "Press Start 2P"';
                    ctx.textAlign = 'center';
                    ctx.fillText('[ESPAÇO / AÇÃO]', player.x, player.y - 45);
                }
            });

            // Update Action Prompt HUD
            const prompt = document.getElementById('action-prompt');
            const promptText = document.getElementById('prompt-text');
            if (currentActiveStation && !modalOpen()) {
                prompt.classList.remove('hidden');
                const pt = `CLIQUE PARA ABRIR: ${currentActiveStation.name.toUpperCase()}`; if (promptText.textContent !== pt) promptText.textContent = pt;
            } else {
                prompt.classList.add('hidden');
            }

            // Render Floating Text Particles
            for (let i = floatingParticles.length - 1; i >= 0; i--) {
                const p = floatingParticles[i];
                p.y -= 0.8;
                p.opacity -= 0.015;
                p.life--;

                ctx.fillStyle = p.color;
                ctx.globalAlpha = Math.max(0, p.opacity);
                ctx.font = '10px "Press Start 2P"';
                ctx.textAlign = 'center';
                ctx.fillText(p.text, p.x, p.y);
                ctx.globalAlpha = 1.0;

                if (p.life <= 0) floatingParticles.splice(i, 1);
            }

            requestAnimationFrame(renderGame);
        }

        // Draw Pixel Character Avatar
        function drawPlayerSprite(x, y, dir, frame) {
            ctx.save();
            ctx.translate(x, y);

            // Shadow
            ctx.fillStyle = 'rgba(0,0,0,0.4)';
            ctx.beginPath();
            ctx.ellipse(0, 14, 10, 4, 0, 0, Math.PI * 2);
            ctx.fill();

            // Legs Bobbing animation
            const legOffset = (frame % 2 === 0) ? -2 : 2;

            // Hair/Head (Pink Cyber Hair)
            ctx.fillStyle = '#ff3b94';
            ctx.fillRect(-10, -32, 20, 14);

            // Face
            ctx.fillStyle = '#ffd1b3';
            ctx.fillRect(-8, -26, 16, 10);

            // VR Headset / Cyber Glasses
            ctx.fillStyle = '#00f5d4';
            ctx.fillRect(-7, -24, 14, 4);

            // Jacket / Body (Purple Cyber Jacket)
            ctx.fillStyle = '#9d4edd';
            ctx.fillRect(-9, -16, 18, 18);

            // Jacket Neon Accents
            ctx.fillStyle = '#ff3b94';
            ctx.fillRect(-9, -16, 3, 18);
            ctx.fillRect(6, -16, 3, 18);

            // Pants / Shoes
            ctx.fillStyle = '#150c26';
            ctx.fillRect(-7 + legOffset, 2, 5, 10);
            ctx.fillRect(2 - legOffset, 2, 5, 10);

            ctx.restore();
        }

        // Input Keyboard Listeners
        window.addEventListener('keydown', e => {
            if (e.key === 'Escape') { closeModal(); closeMiniGame(); return; }
            const isBtn = ['BUTTON', 'A'].includes(e.target.tagName);
            if (['ArrowUp', 'ArrowDown', 'ArrowLeft', 'ArrowRight'].includes(e.key) || (e.key === ' ' && !isBtn)) e.preventDefault();
            if (isBtn && (e.key === ' ' || e.key === 'Enter')) return;
            if (modalOpen()) return;
            initAudio();
            if (e.key === 'ArrowUp' || e.key === 'w' || e.key === 'W') keys.up = true;
            if (e.key === 'ArrowDown' || e.key === 's' || e.key === 'S') keys.down = true;
            if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') keys.left = true;
            if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') keys.right = true;
            if ((e.key === ' ' || e.key === 'Enter') && !e.repeat) triggerCurrentStation();
        });

        window.addEventListener('keyup', e => {
            if (e.key === 'ArrowUp' || e.key === 'w' || e.key === 'W') keys.up = false;
            if (e.key === 'ArrowDown' || e.key === 's' || e.key === 'S') keys.down = false;
            if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') keys.left = false;
            if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') keys.right = false;
        });

        // Touch Control Button Event Binding with Improved Mobile Support
        function bindTouchBtn(btnId, keyName) {
            const btn = document.getElementById(btnId);
            if (!btn) return;
            
            const startPress = (e) => {
                if (e.cancelable) e.preventDefault();
                initAudio();
                keys[keyName] = true;
            };

            const endPress = (e) => {
                if (e.cancelable) e.preventDefault();
                keys[keyName] = false;
            };

            btn.addEventListener('pointerdown', (e) => { e.preventDefault(); keys[keyName] = true; });
            ['pointerup', 'pointerleave', 'pointercancel'].forEach(ev => btn.addEventListener(ev, () => { keys[keyName] = false; }));
            btn.addEventListener('mouseleave', endPress);
        }

        // FIXED: Accurate Canvas Click Coordinates Scaling Calculation
        canvas.addEventListener('click', (e) => {
            initAudio();
            const rect = canvas.getBoundingClientRect();
            
            // Calculate scale ratio between actual display size and internal canvas coordinate space
            const scaleX = canvas.width / rect.width;
            const scaleY = canvas.height / rect.height;

            const clickX = (e.clientX - rect.left) * scaleX;
            const clickY = (e.clientY - rect.top) * scaleY;

            const hit = stations.find(st => clickX >= st.x - 10 && clickX <= st.x + st.width + 10 && clickY >= st.y - 25 && clickY <= st.y + st.height + 10);
            if (hit) {
                target = { x: hit.x + hit.width / 2, y: Math.min(hit.y + hit.height + 20, canvas.height - 30) };
                pendingStation = hit;
            } else {
                target = { x: clamp(clickX, 20, canvas.width - 20), y: clamp(clickY, 40, canvas.height - 30) };
                pendingStation = null;
            }
        });

        // --- 3. STATION MODAL CONTENT & LOGIC ---
        function triggerCurrentStation() {
            if (modalOpen()) return;
            triggerStation(currentActiveStation);
        }

        function triggerStation(st) {
            if (!st) return;
            currentActiveStation = st;
            Object.keys(keys).forEach(k => keys[k] = false);
            
            playSound('interact');
            
            if (!st.activated) {
                st.activated = true;
                addXP(300, "+300 XP: ESTAÇÃO DESBLOQUEADA!");
            }

            if (st.id === 'arcade') {
                openMiniGame();
                return;
            }

            openModal(st.id);
        }

        function moveToStation(stationId) {
            initAudio();
            const st = stations.find(s => s.id === stationId);
            if (st) {
                player.x = st.x + st.width / 2;
                player.y = st.y + st.height + 20;
                currentActiveStation = st;
                triggerCurrentStation();
            }
        }

        function openModal(stationId) {
            const overlay = document.getElementById('modal-overlay');
            const title = document.getElementById('modal-title');
            const icon = document.getElementById('modal-icon');
            const body = document.getElementById('modal-body');

            overlay.classList.remove('hidden');

            if (stationId === 'terminal') {
                title.innerText = 'HABILIDADES & COMPETÊNCIAS';
                icon.textContent = '💻';
                body.innerHTML = `
                    <div class="space-y-4 font-sans text-sm">
                        <div class="p-3 bg-cyber-bg border border-cyber-pink/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-pink text-xs mb-2">⚡ SUPORTE TÉCNICO & HELP DESK (N1/N2)</h3>
                            <p class="text-gray-300">Atendimento de chamados com foco em cumprimento de SLA, diagnósticos rápidos de hardware/software e excelente comunicação com usuários finais.</p>
                        </div>
                        <div class="p-3 bg-cyber-bg border border-cyber-purple/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-purple text-xs mb-2">💻 SISTEMAS & AMBIENTES</h3>
                            <p class="text-gray-300">Administração de contas no Active Directory (AD), políticas GPO, Office 365, sistemas Windows e comandos em Linux CLI.</p>
                        </div>
                        <div class="p-3 bg-cyber-bg border border-cyber-cyan/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-cyan text-xs mb-2">🛠️ MANUTENÇÃO & DISPOSITIVOS</h3>
                            <p class="text-gray-300">Formatação, montagem, substituição de peças, configuração de impressoras em rede, backup e restauração de arquivos.</p>
                        </div>
                    </div>
                `;
            } else if (stationId === 'server') {
                title.innerText = 'INFRAESTRUTURA & REDES';
                icon.textContent = '🖥️';
                body.innerHTML = `
                    <div class="space-y-4 font-sans text-sm">
                        <div class="p-3 bg-cyber-bg border border-cyber-purple/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-purple text-xs mb-2">🌐 CONFIGURAÇÃO DE REDES</h3>
                            <p class="text-gray-300">Conceitos fundamentais TCP/IP, cabeamento estruturado (Patch Panels/RJ45), configuração de Roteadores, Switches e redes Wi-Fi Corporativas.</p>
                        </div>
                        <div class="p-3 bg-cyber-bg border border-cyber-pink/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-pink text-xs mb-2">🖥️️ SERVIDORES & ARMAZENAMENTO</h3>
                            <p class="text-gray-300">Monitoramento de disponibilidade de servidores, rotinas de backup local/nuvem e manutenção preventiva de data center.</p>
                        </div>
                    </div>
                `;
            } else if (stationId === 'forensics') {
                title.innerText = 'SEGURANÇA DA INFORMAÇÃO';
                icon.textContent = '🛡️';
                body.innerHTML = `
                    <div class="space-y-4 font-sans text-sm">
                        <div class="p-3 bg-cyber-bg border border-cyber-cyan/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-cyan text-xs mb-2">🔒 PROTEÇÃO & PREVENÇÃO</h3>
                            <p class="text-gray-300">Aplicação de políticas de segurança contra Malware/Phishing, gestão de credenciais seguras e permissões de acesso por perfil.</p>
                        </div>
                        <div class="p-3 bg-cyber-bg border border-cyber-yellow/50 rounded-lg">
                            <h3 class="font-pixel text-cyber-yellow text-xs mb-2">📜 ANÁLISE DE LOGS & RECUPERAÇÃO</h3>
                            <p class="text-gray-300">Identificação de falhas no sistema operacional, análise de logs de eventos do Windows/Linux e plano de contingência para sinistros.</p>
                        </div>
                    </div>
                `;
            } else if (stationId === 'comms') {
                title.innerText = 'CENTRO DE CONTATO & REDES';
                icon.textContent = '💬';
                body.innerHTML = `
                    <div class="text-center space-y-4 font-sans">
                        <p class="text-gray-200">Gostou da apresentação em formato de jogo? Entre em contato para conversarmos sobre oportunidades!</p>
                        
                        <div class="flex flex-col gap-3 max-w-md mx-auto pt-2">
                            <button onclick="copyToClipboard('seu.email@exemplo.com')" class="px-4 py-3 bg-cyber-pink/20 border border-cyber-pink text-cyber-pink hover:bg-cyber-pink hover:text-black font-pixel text-xs rounded transition-all flex items-center justify-center gap-2">
                                <span class="">✉️</span> COPIAR E-MAIL (miquemlk557@gmail.com)
                            </button>

                            <a href="https://www.linkedin.com/in/mirelly--rodrigues" target="_blank" rel="noopener noreferrer" class="px-4 py-3 bg-cyber-purple/20 border border-cyber-purple text-cyber-purple hover:bg-cyber-purple hover:text-white font-pixel text-xs rounded transition-all flex items-center justify-center gap-2">
                                <span class="">💼</span> PERFIL NO LINKEDIN
                            </a>

                            <a href="https://github.com/mialytech?tab=repositories" target="_blank" rel="noopener noreferrer" class="px-4 py-3 bg-cyber-cyan/20 border border-cyber-cyan text-cyber-cyan hover:bg-cyber-cyan hover:text-black font-pixel text-xs rounded transition-all flex items-center justify-center gap-2">
                                <span class="">🐙</span> REPOSITÓRIOS GITHUB
                            </a>
                        </div>
                    </div>
                `;
            }
        }

        function closeModal() {
            document.getElementById('modal-overlay').classList.add('hidden');
        }

        // --- 4. MINI-GAME: FIX THE SERVER CABLES ---
        let mgScore = 0;
        let mgTimer = 15;
        let mgInterval = null;

        function openMiniGame() {
            document.getElementById('minigame-modal').classList.remove('hidden');
            mgScore = 0;
            mgTimer = 15;
            document.getElementById('mg-score').innerText = mgScore;
            document.getElementById('mg-timer').innerText = mgTimer;
            
            clearInterval(mgInterval);
            mgInterval = setInterval(() => {
                mgTimer--;
                document.getElementById('mg-timer').innerText = mgTimer;
                if (mgTimer <= 0) {
                    endMiniGame();
                }
            }, 1000);

            generateCableGrid();
        }

        function generateCableGrid() {
            const grid = document.getElementById('mg-grid');
            grid.innerHTML = '';
            const forced = Math.floor(Math.random() * 6);

            for (let i = 0; i < 6; i++) {
                const isBroken = i === forced || Math.random() > 0.4;
                const card = document.createElement('div');
                card.className = `border rounded p-2 flex flex-col items-center justify-center cursor-pointer transition-all ${
                    isBroken 
                    ? 'bg-red-900/40 border-red-500 text-red-400 hover:scale-105' 
                    : 'bg-emerald-900/40 border-emerald-500 text-emerald-400'
                }`;

                card.innerHTML = `
                    <span class="text-2xl mb-1">${isBroken ? '❌' : '✅'}</span>
                    <span class="font-pixel text-[9px]">${isBroken ? 'ERRO NO CABO' : 'OK'}</span>
                `;

                card.onclick = () => {
                    if (isBroken) {
                        playSound('score');
                        mgScore += 100;
                        document.getElementById('mg-score').innerText = mgScore;
                        addXP(100, "+100 XP: CABO REPARADO!");
                        generateCableGrid();
                    }
                };

                grid.appendChild(card);
            }
        }

        function endMiniGame() {
            clearInterval(mgInterval);
            playSound('score');
            showToast(`Mini-game Concluído! Pontuação: ${mgScore} PTS 🎉`);
            closeMiniGame();
        }

        function closeMiniGame() {
            clearInterval(mgInterval);
            document.getElementById('minigame-modal').classList.add('hidden');
        }

        // --- 5. GAMIFICATION & MODERN UTILS ---
        function addXP(amount, message) {
            totalXP += amount;
            document.getElementById('xp-counter').innerText = totalXP;
            document.getElementById('xp-bar').style.width = ((totalXP % 2000) / 20) + '%';
            spawnParticle(`+${amount} XP`, player.x, player.y - 30, '#ffee38');
            if (message) showToast(message);
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            const toastText = document.getElementById('toast-text');
            toastText.innerText = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            clearTimeout(window._tt);
            window._tt = setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 2500);
        }

        // FIXED: Modern Clipboard API with Executive Fallback
        async function copyToClipboard(text) {
            const done = () => { playSound('score'); showToast("E-mail copiado para a área de transferência! 🚀"); };
            const fallback = () => {
                const t = document.createElement('textarea');
                t.value = text; document.body.appendChild(t); t.select();
                try { document.execCommand('copy'); } catch (e) {}
                document.body.removeChild(t); done();
            };
            if (navigator.clipboard) navigator.clipboard.writeText(text).then(done, fallback); else fallback();
        }

        // Start Canvas Engine on Load
        window.onload = function() {
            requestAnimationFrame(renderGame);
        };
    </script>
</body>
</html>
