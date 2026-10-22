<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>STARFIGHTER 3D: NEBULA VANGUARD</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;800;900&family=Share+Tech+Mono&display=swap" rel="stylesheet">
    <!-- Three.js CDN -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

    <style>
        * {
            user-select: none;
            -webkit-user-select: none;
            touch-action: manipulation;
        }

        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            font-family: 'Share Tech Mono', monospace;
            background-color: #01020a;
            color: #00f3ff;
        }

        .font-orbitron {
            font-family: 'Orbitron', sans-serif;
        }

        .hud-border {
            border: 1px solid rgba(0, 243, 255, 0.4);
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.2), inset 0 0 10px rgba(0, 243, 255, 0.1);
            background: rgba(4, 12, 28, 0.65);
            backdrop-filter: blur(8px);
        }

        .hud-border-magenta {
            border: 1px solid rgba(255, 0, 127, 0.4);
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.2), inset 0 0 10px rgba(255, 0, 127, 0.1);
            background: rgba(28, 4, 18, 0.65);
            backdrop-filter: blur(8px);
        }

        .cyber-btn {
            background: linear-gradient(135deg, rgba(0, 243, 255, 0.25), rgba(255, 0, 127, 0.25));
            border: 1px solid #00f3ff;
            text-shadow: 0 0 8px rgba(0, 243, 255, 0.8);
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.3);
            transition: all 0.2s ease;
        }

        .cyber-btn:hover {
            background: linear-gradient(135deg, rgba(0, 243, 255, 0.5), rgba(255, 0, 127, 0.5));
            box-shadow: 0 0 25px rgba(0, 243, 255, 0.7);
            transform: scale(1.03);
        }

        #canvas-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        /* Crosshair Reticle */
        #reticle {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 48px;
            height: 48px;
            pointer-events: none;
            z-index: 10;
        }

        /* Radar Canvas */
        #radar-canvas {
            border-radius: 50%;
            background: rgba(0, 20, 35, 0.75);
            border: 2px solid rgba(0, 243, 255, 0.6);
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.3);
        }
    </style>
</head>
<body class="relative w-screen h-screen overflow-hidden select-none">

    <!-- 3D Canvas -->
    <div id="canvas-container"></div>

    <!-- HUD Overlay -->
    <div id="hud" class="absolute inset-0 z-10 pointer-events-none opacity-0 transition-opacity duration-500 p-4 md:p-6 flex flex-col justify-between">
        
        <!-- Top HUD Bar -->
        <div class="flex justify-between items-start">
            <!-- Health & Boost Gauges -->
            <div class="w-64 md:w-80 flex flex-col gap-2">
                <!-- Hull Shield Bar -->
                <div class="hud-border p-2 rounded-lg">
                    <div class="flex justify-between items-center text-xs font-bold mb-1">
                        <span class="text-cyan-300 flex items-center gap-1"><i class="fa-solid fa-shield-halved"></i> ESCUDO NAVE</span>
                        <span id="hud-shield-val" class="text-cyan-400 font-orbitron">100%</span>
                    </div>
                    <div class="w-full h-3 bg-slate-900 rounded-full overflow-hidden border border-cyan-500/40">
                        <div id="hud-shield-bar" class="h-full bg-gradient-to-r from-cyan-500 to-blue-500 w-full transition-all duration-200"></div>
                    </div>
                </div>

                <!-- Energy Boost Bar -->
                <div class="hud-border p-2 rounded-lg">
                    <div class="flex justify-between items-center text-xs font-bold mb-1">
                        <span class="text-yellow-300 flex items-center gap-1"><i class="fa-solid fa-bolt"></i> IMPULSO (BOOST)</span>
                        <span id="hud-boost-val" class="text-yellow-400 font-orbitron">100%</span>
                    </div>
                    <div class="w-full h-2 bg-slate-900 rounded-full overflow-hidden border border-yellow-500/40">
                        <div id="hud-boost-bar" class="h-full bg-gradient-to-r from-amber-500 to-yellow-300 w-full transition-all duration-150"></div>
                    </div>
                </div>
            </div>

            <!-- Score & Wave Stats -->
            <div class="hud-border p-3 rounded-lg flex flex-col items-center min-w-[140px] md:min-w-[180px]">
                <span class="text-[10px] text-cyan-300/70 font-bold uppercase tracking-widest">PUNTUACIÓN</span>
                <span id="hud-score" class="text-2xl md:text-3xl font-orbitron text-cyan-400 font-black">0</span>
                <div class="flex gap-4 mt-1 text-xs">
                    <span class="text-pink-400">OLEADA: <b id="hud-wave" class="font-orbitron">1</b></span>
                    <span class="text-yellow-400">RÉCORD: <b id="hud-high" class="font-orbitron">0</b></span>
                </div>
            </div>
        </div>

        <!-- Center Aiming Reticle -->
        <div id="reticle">
            <svg viewBox="0 0 100 100" class="w-full h-full stroke-cyan-400 fill-none opacity-80">
                <circle cx="50" cy="50" r="42" stroke-width="1.5" stroke-dasharray="6 4" />
                <circle cx="50" cy="50" r="12" stroke-width="2" />
                <line x1="50" y1="0" x2="50" y2="25" stroke-width="2" />
                <line x1="50" y1="75" x2="50" y2="100" stroke-width="2" />
                <line x1="0" y1="50" x2="25" y2="50" stroke-width="2" />
                <line x1="75" y1="50" x2="100" y2="50" stroke-width="2" />
            </svg>
        </div>

        <!-- Active Powerup Alert Indicator -->
        <div id="powerup-status" class="self-center mb-12 hidden">
            <div class="hud-border-magenta px-4 py-1.5 rounded-full text-xs font-orbitron font-bold text-pink-400 flex items-center gap-2 animate-pulse">
                <i id="powerup-icon" class="fa-solid fa-star"></i>
                <span id="powerup-text">CUÁDRUPLE LÁSER ACTIVO</span>
            </div>
        </div>

        <!-- Bottom HUD Bar -->
        <div class="flex justify-between items-end">
            <!-- Controls Hint -->
            <div class="hidden md:flex flex-col text-[11px] text-cyan-300/60 bg-slate-950/60 p-2 rounded-lg border border-cyan-500/20 backdrop-blur">
                <span>[MOUSE / WASD] Pilotar Nave</span>
                <span>[CLIC IZQ / ESPACIO] Disparar Láser</span>
                <span>[SHIFT] Impulso Motor</span>
                <span>[C] Cambiar Cámara (1a/3a persona)</span>
            </div>

            <!-- Radar / Minimap -->
            <div class="relative">
                <canvas id="radar-canvas" width="130" height="130"></canvas>
                <div class="absolute bottom-1 right-2 text-[9px] text-cyan-400/80 font-bold uppercase pointer-events-none">RADAR 360°</div>
            </div>
        </div>
    </div>

    <!-- UI Overlay Windows -->
    <div id="ui-overlay" class="absolute inset-0 z-20 flex items-center justify-center p-4 bg-slate-950/80 backdrop-blur-md transition-opacity duration-300">
        
        <!-- Start Screen -->
        <div id="start-screen" class="hud-border max-w-lg w-full p-6 md:p-8 rounded-2xl flex flex-col items-center text-center">
            <div class="w-16 h-16 mb-4 rounded-2xl bg-cyan-500/10 border border-cyan-400/40 flex items-center justify-center text-cyan-400 text-3xl shadow-[0_0_20px_rgba(0,243,255,0.3)]">
                <i class="fa-solid fa-shuttle-space"></i>
            </div>
            <h1 class="text-3xl md:text-5xl font-black font-orbitron text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-teal-300 to-pink-500 tracking-wider mb-2">
                NEBULA VANGUARD
            </h1>
            <p class="text-xs md:text-sm text-cyan-300/80 font-semibold tracking-widest uppercase mb-6">
                3D Space Dogfight & Asteroid Defense
            </p>

            <div class="w-full bg-slate-900/80 rounded-xl p-4 border border-cyan-500/30 mb-6 text-left text-xs text-slate-300 space-y-2">
                <div class="text-cyan-400 font-bold font-orbitron border-b border-cyan-500/30 pb-1 mb-2"><i class="fa-solid fa-crosshairs"></i> MISIONES DE COMBATE</div>
                <p>• Destruye asteroides y cazas alienígenas hostiles.</p>
                <p>• Recoge contenedores de energía (Reparación, Escudo, Láser Cuádruple).</p>
                <p>• Sobrevive a las oleadas progresivas de enemigos espacio profundo.</p>
            </div>

            <button onclick="startGame()" class="cyber-btn w-full py-4 rounded-xl text-cyan-300 font-orbitron text-lg font-bold tracking-widest uppercase mb-4 cursor-pointer flex items-center justify-center gap-2">
                <i class="fa-solid fa-play"></i> DESPEGAR A COMBATE
            </button>

            <!-- Audio Toggle -->
            <button onclick="toggleAudio()" class="text-xs text-slate-400 hover:text-cyan-300 flex items-center gap-2 cursor-pointer">
                <i id="sound-icon" class="fa-solid fa-volume-high text-cyan-400"></i>
                <span id="sound-text">SINTETIZADOR AUDIO: ACTIVADO</span>
            </button>
        </div>

        <!-- Game Over Screen -->
        <div id="gameover-screen" class="hud-border-magenta max-w-lg w-full p-6 md:p-8 rounded-2xl flex flex-col items-center text-center hidden">
            <h2 class="text-3xl md:text-4xl font-black font-orbitron text-pink-500 text-shadow-lg mb-1">
                NAVE DESTRUIDA
            </h2>
            <p class="text-xs text-slate-300 uppercase tracking-widest mb-6">Se perdió la señal del piloto en la nebulosa</p>

            <div class="w-full grid grid-cols-2 gap-3 mb-6">
                <div class="bg-slate-900/80 p-3 rounded-xl border border-cyan-500/30">
                    <span class="block text-[10px] text-cyan-300/70 font-bold uppercase">Puntuación Final</span>
                    <span id="final-score" class="text-2xl font-orbitron text-cyan-400 font-bold">0</span>
                </div>
                <div class="bg-slate-900/80 p-3 rounded-xl border border-pink-500/30">
                    <span class="block text-[10px] text-pink-300/70 font-bold uppercase">Oleada Alcanzada</span>
                    <span id="final-wave" class="text-2xl font-orbitron text-pink-400 font-bold">1</span>
                </div>
                <div class="bg-slate-900/80 p-3 rounded-xl border border-yellow-500/30">
                    <span class="block text-[10px] text-yellow-300/70 font-bold uppercase">Asteroides Rotos</span>
                    <span id="final-asteroids" class="text-xl font-orbitron text-yellow-400 font-bold">0</span>
                </div>
                <div class="bg-slate-900/80 p-3 rounded-xl border border-teal-500/30">
                    <span class="block text-[10px] text-teal-300/70 font-bold uppercase">Cazas Alienígenas</span>
                    <span id="final-drones" class="text-xl font-orbitron text-teal-400 font-bold">0</span>
                </div>
            </div>

            <button onclick="startGame()" class="cyber-btn w-full py-4 rounded-xl text-pink-300 border-pink-500 font-orbitron text-lg font-bold tracking-widest uppercase cursor-pointer flex items-center justify-center gap-2">
                <i class="fa-solid fa-rotate-right"></i> REINICIAR MISIÓN
            </button>
        </div>

    </div>

    <!-- Mobile Touch Controls Overlay -->
    <div id="mobile-controls" class="absolute inset-0 pointer-events-none z-15 md:hidden flex flex-col justify-between p-4">
        <div></div>
        <div class="flex justify-between items-end pointer-events-auto mb-16">
            <!-- Flight Control Pad -->
            <div class="grid grid-cols-3 gap-2 w-36 h-36 bg-slate-950/40 p-2 rounded-2xl border border-cyan-500/30 backdrop-blur">
                <div></div>
                <button ontouchstart="setMobileDir(0, -1)" ontouchend="setMobileDir(0, 0)" class="bg-cyan-500/20 active:bg-cyan-500/60 rounded-lg text-cyan-300 text-xl flex items-center justify-center"><i class="fa-solid fa-arrow-up"></i></button>
                <div></div>
                <button ontouchstart="setMobileDir(-1, 0)" ontouchend="setMobileDir(0, 0)" class="bg-cyan-500/20 active:bg-cyan-500/60 rounded-lg text-cyan-300 text-xl flex items-center justify-center"><i class="fa-solid fa-arrow-left"></i></button>
                <div class="bg-cyan-500/10 rounded-lg"></div>
                <button ontouchstart="setMobileDir(1, 0)" ontouchend="setMobileDir(0, 0)" class="bg-cyan-500/20 active:bg-cyan-500/60 rounded-lg text-cyan-300 text-xl flex items-center justify-center"><i class="fa-solid fa-arrow-right"></i></button>
                <div></div>
                <button ontouchstart="setMobileDir(0, 1)" ontouchend="setMobileDir(0, 0)" class="bg-cyan-500/20 active:bg-cyan-500/60 rounded-lg text-cyan-300 text-xl flex items-center justify-center"><i class="fa-solid fa-arrow-down"></i></button>
                <div></div>
            </div>

            <!-- Action Buttons -->
            <div class="flex flex-col gap-3">
                <button ontouchstart="mobileBoost(true)" ontouchend="mobileBoost(false)" class="w-16 h-16 rounded-2xl bg-amber-950/60 border border-amber-400/50 text-amber-300 text-2xl flex items-center justify-center active:scale-95"><i class="fa-solid fa-bolt"></i></button>
                <button ontouchstart="mobileFire()" class="w-20 h-20 rounded-2xl bg-pink-950/60 border border-pink-400/50 text-pink-300 text-3xl flex items-center justify-center active:scale-95"><i class="fa-solid fa-crosshairs"></i></button>
            </div>
        </div>
    </div>

    <!-- MAIN GAME LOGIC -->
    <script>
        // --- SYNTHESIZED WEB AUDIO ENGINE ---
        class WebAudioSynth {
            constructor() {
                this.ctx = null;
                this.enabled = true;
            }

            init() {
                if (!this.ctx) {
                    const AudioCtx = window.AudioContext || window.webkitAudioContext;
                    this.ctx = new AudioCtx();
                }
            }

            playLaser() {
                if (!this.enabled || !this.ctx) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'sawtooth';
                osc.frequency.setValueAtTime(880, this.ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(110, this.ctx.currentTime + 0.12);

                gain.gain.setValueAtTime(0.2, this.ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + 0.12);

                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + 0.12);
            }

            playEnemyLaser() {
                if (!this.enabled || !this.ctx) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'square';
                osc.frequency.setValueAtTime(400, this.ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(80, this.ctx.currentTime + 0.15);

                gain.gain.setValueAtTime(0.15, this.ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + 0.15);

                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + 0.15);
            }

            playExplosion(isBig = false) {
                if (!this.enabled || !this.ctx) return;
                const duration = isBig ? 0.6 : 0.3;
                const bufferSize = this.ctx.sampleRate * duration;
                const buffer = this.ctx.createBuffer(1, bufferSize, this.ctx.sampleRate);
                const data = buffer.getChannelData(0);
                for (let i = 0; i < bufferSize; i++) {
                    data[i] = Math.random() * 2 - 1;
                }

                const noise = this.ctx.createBufferSource();
                noise.buffer = buffer;

                const filter = this.ctx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.setValueAtTime(isBig ? 400 : 800, this.ctx.currentTime);
                filter.frequency.exponentialRampToValueAtTime(30, this.ctx.currentTime + duration);

                const gain = this.ctx.createGain();
                gain.gain.setValueAtTime(isBig ? 0.5 : 0.3, this.ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + duration);

                noise.connect(filter);
                filter.connect(gain);
                gain.connect(this.ctx.destination);

                noise.start();
                noise.stop(this.ctx.currentTime + duration);
            }

            playPowerup() {
                if (!this.enabled || !this.ctx) return;
                const notes = [523.25, 659.25, 783.99, 1046.50]; // C5, E5, G5, C6
                notes.forEach((freq, idx) => {
                    const osc = this.ctx.createOscillator();
                    const gain = this.ctx.createGain();
                    osc.type = 'sine';
                    osc.frequency.value = freq;
                    gain.gain.setValueAtTime(0.15, this.ctx.currentTime + idx * 0.05);
                    gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + idx * 0.05 + 0.1);
                    osc.connect(gain);
                    gain.connect(this.ctx.destination);
                    osc.start(this.ctx.currentTime + idx * 0.05);
                    osc.stop(this.ctx.currentTime + idx * 0.05 + 0.1);
                });
            }
        }

        const audioSynth = new WebAudioSynth();

        function toggleAudio() {
            audioSynth.enabled = !audioSynth.enabled;
            document.getElementById('sound-text').innerText = `SINTETIZADOR AUDIO: ${audioSynth.enabled ? 'ACTIVADO' : 'DESACTIVADO'}`;
            document.getElementById('sound-icon').className = audioSynth.enabled ? 'fa-solid fa-volume-high text-cyan-400' : 'fa-solid fa-volume-xmark text-slate-500';
        }

        // --- GLOBAL GAME VARIABLES ---
        let scene, camera, renderer;
        let playerShip, playerLight;
        let starfield, nebulaClouds;
        
        // Entities Containers
        let playerLasers = [];
        let enemyLasers = [];
        let asteroids = [];
        let enemyDrones = [];
        let powerups = [];
        let particleExplosions = [];

        // Game State
        let isGameRunning = false;
        let score = 0;
        let wave = 1;
        let shield = 100;
        let boostEnergy = 100;
        let isBoosting = false;
        let thirdPersonCamera = true;
        let quadLaserTimer = 0;

        // Stats Tracking
        let statAsteroidsDestroyed = 0;
        let statDronesDestroyed = 0;
        let highScore = localStorage.getItem('starfighter_high_score') || 0;

        // Control Inputs
        const mouse = { x: 0, y: 0 };
        const keys = {};
        const mobileDir = { x: 0, y: 0 };

        // Camera Shake State
        let shakeDuration = 0;
        let shakeIntensity = 0;

        // --- THREE.JS PROCEDURAL CREATION ---
        function initThreeEngine() {
            const container = document.getElementById('canvas-container');

            // 1. Scene & Fog
            scene = new THREE.Scene();
            scene.fog = new THREE.FogExp2(0x01020a, 0.0015);

            // 2. Camera
            camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 2000);

            // 3. Renderer
            renderer = new THREE.WebGLRenderer({ antialias: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
            renderer.toneMapping = THREE.ACESFilmicToneMapping;
            renderer.toneMappingExposure = 1.2;
            container.appendChild(renderer.domElement);

            // 4. Lighting System
            const ambientLight = new THREE.AmbientLight(0x1a2b4c, 1.2);
            scene.add(ambientLight);

            // Distant Sun Light
            const sunLight = new THREE.DirectionalLight(0xffffff, 2.0);
            sunLight.position.set(300, 200, -500);
            scene.add(sunLight);

            // Glowing Sun Sphere
            const sunGeo = new THREE.SphereGeometry(30, 32, 32);
            const sunMat = new THREE.MeshBasicMaterial({ color: 0xffddaa });
            const sunMesh = new THREE.Mesh(sunGeo, sunMat);
            sunMesh.position.copy(sunLight.position);
            scene.add(sunMesh);

            // Colored Ambient Nebulae Lights
            const cyanLight = new THREE.PointLight(0x00f3ff, 3, 400);
            cyanLight.position.set(-200, 100, -200);
            scene.add(cyanLight);

            const magentaLight = new THREE.PointLight(0xff007f, 3, 400);
            magentaLight.position.set(200, -100, -300);
            scene.add(magentaLight);

            // 5. Starfield Environment
            createStarfield();

            // 6. Player Ship
            createPlayerShip();

            // Event Listeners
            window.addEventListener('resize', onResize);
            window.addEventListener('mousemove', onMouseMove);
            window.addEventListener('keydown', (e) => { keys[e.code] = true; handleSpecialKeys(e); });
            window.addEventListener('keyup', (e) => { keys[e.code] = false; });
            window.addEventListener('mousedown', (e) => { if (e.button === 0 && isGameRunning) fireLaser(); });

            document.getElementById('hud-high').innerText = highScore;
        }

        function createStarfield() {
            const count = 3500;
            const geo = new THREE.BufferGeometry();
            const positions = new Float32Array(count * 3);
            const colors = new Float32Array(count * 3);

            for (let i = 0; i < count; i++) {
                positions[i * 3] = (Math.random() - 0.5) * 1600;
                positions[i * 3 + 1] = (Math.random() - 0.5) * 1600;
                positions[i * 3 + 2] = (Math.random() - 0.5) * 1600;

                // Cyan / Magenta / White star tint
                const colorType = Math.random();
                if (colorType > 0.7) {
                    colors[i * 3] = 0; colors[i * 3 + 1] = 0.95; colors[i * 3 + 2] = 1;
                } else if (colorType > 0.4) {
                    colors[i * 3] = 1; colors[i * 3 + 1] = 0; colors[i * 3 + 2] = 0.7;
                } else {
                    colors[i * 3] = 1; colors[i * 3 + 1] = 1; colors[i * 3 + 2] = 1;
                }
            }

            geo.setAttribute('position', new THREE.BufferAttribute(positions, 3));
            geo.setAttribute('color', new THREE.BufferAttribute(colors, 3));

            const mat = new THREE.PointsMaterial({
                size: 1.8,
                vertexColors: true,
                transparent: true,
                opacity: 0.85
            });

            starfield = new THREE.Points(geo, mat);
            scene.add(starfield);
        }

        function createPlayerShip() {
            playerShip = new THREE.Group();

            // Fuselage Main Body
            const bodyGeo = new THREE.ConeGeometry(0.8, 4.5, 8);
            bodyGeo.rotateX(Math.PI / 2);
            const bodyMat = new THREE.MeshStandardMaterial({
                color: 0x0f172a,
                metalness: 0.8,
                roughness: 0.2
            });
            const body = new THREE.Mesh(bodyGeo, bodyMat);
            playerShip.add(body);

            // Glowing Cockpit Glass
            const cockpitGeo = new THREE.SphereGeometry(0.5, 16, 16);
            cockpitGeo.scale(1, 0.6, 1.8);
            const cockpitMat = new THREE.MeshStandardMaterial({
                color: 0x00f3ff,
                emissive: 0x00f3ff,
                emissiveIntensity: 0.8,
                roughness: 0.1
            });
            const cockpit = new THREE.Mesh(cockpitGeo, cockpitMat);
            cockpit.position.set(0, 0.3, 0.2);
            playerShip.add(cockpit);

            // Wings
            const wingGeo = new THREE.BoxGeometry(4.2, 0.08, 1.6);
            const wingMat = new THREE.MeshStandardMaterial({ color: 0x1e293b, metalness: 0.9, roughness: 0.3 });
            const wings = new THREE.Mesh(wingGeo, wingMat);
            wings.position.set(0, 0, -0.2);
            playerShip.add(wings);

            // Wing Tip Laser Cannons
            const cannonGeo = new THREE.CylinderGeometry(0.06, 0.06, 1.2);
            cannonGeo.rotateX(Math.PI / 2);
            const cannonMat = new THREE.MeshStandardMaterial({ color: 0x00f3ff, emissive: 0x00f3ff, emissiveIntensity: 0.5 });
            
            const leftCannon = new THREE.Mesh(cannonGeo, cannonMat);
            leftCannon.position.set(-2.0, 0, 0.5);
            playerShip.add(leftCannon);

            const rightCannon = new THREE.Mesh(cannonGeo, cannonMat);
            rightCannon.position.set(2.0, 0, 0.5);
            playerShip.add(rightCannon);

            // Thruster Engines Glow
            const engineGeo = new THREE.CylinderGeometry(0.3, 0.1, 0.8, 16);
            engineGeo.rotateX(Math.PI / 2);
            const engineMat = new THREE.MeshBasicMaterial({ color: 0x00f3ff });
            const engine = new THREE.Mesh(engineGeo, engineMat);
            engine.position.set(0, 0, -2.2);
            playerShip.add(engine);

            // Dynamic Pointlight attached to Player
            playerLight = new THREE.PointLight(0x00f3ff, 1.5, 25);
            playerLight.position.set(0, 0, -2);
            playerShip.add(playerLight);

            scene.add(playerShip);
        }

        // --- PROCEDURAL SPONING PROCEDURES ---
        function createAsteroid(x, y, z, sizeType = 'LARGE') {
            let radius = 8;
            if (sizeType === 'MEDIUM') radius = 4;
            if (sizeType === 'SMALL') radius = 2;

            // Deformed Sphere Geometry for Jagged Asteroid Look
            const geo = new THREE.DodecahedronGeometry(radius, 2);
            const posAttr = geo.attributes.position;
            for (let i = 0; i < posAttr.count; i++) {
                const vx = posAttr.getX(i);
                const vy = posAttr.getY(i);
                const vz = posAttr.getZ(i);
                const noise = 1 + (Math.random() - 0.5) * 0.35;
                posAttr.setXYZ(i, vx * noise, vy * noise, vz * noise);
            }
            geo.computeVertexNormals();

            const mat = new THREE.MeshStandardMaterial({
                color: 0x475569,
                roughness: 0.9,
                metalness: 0.1
            });

            const asteroid = new THREE.Mesh(geo, mat);
            asteroid.position.set(x, y, z);
            asteroid.userData = {
                type: 'asteroid',
                size: sizeType,
                radius: radius,
                rotSpeed: new THREE.Vector3((Math.random() - 0.5) * 0.02, (Math.random() - 0.5) * 0.02, (Math.random() - 0.5) * 0.02),
                velocity: new THREE.Vector3((Math.random() - 0.5) * 0.1, (Math.random() - 0.5) * 0.1, (Math.random() - 0.5) * 0.1)
            };

            scene.add(asteroid);
            asteroids.push(asteroid);
        }

        function createEnemyDrone(x, y, z) {
            const drone = new THREE.Group();

            // Core Body
            const coreGeo = new THREE.OctahedronGeometry(1.2);
            const coreMat = new THREE.MeshStandardMaterial({
                color: 0xff0055,
                emissive: 0xff0055,
                emissiveIntensity: 0.6,
                metalness: 0.8
            });
            const core = new THREE.Mesh(coreGeo, coreMat);
            drone.add(core);

            // Outer Orbiting Rings
            const ringGeo = new THREE.TorusGeometry(2.0, 0.08, 8, 24);
            const ringMat = new THREE.MeshBasicMaterial({ color: 0xff007f });
            const ring = new THREE.Mesh(ringGeo, ringMat);
            drone.add(ring);

            drone.position.set(x, y, z);
            drone.userData = {
                type: 'drone',
                radius: 1.8,
                health: 3,
                lastShot: 0,
                ringMesh: ring
            };

            scene.add(drone);
            enemyDrones.push(drone);
        }

        function spawnPowerup(pos) {
            const types = ['HEALTH', 'QUAD', 'BOOST'];
            const pType = types[Math.floor(Math.random() * types.length)];

            const geo = new THREE.IcosahedronGeometry(1.0);
            let colorHex = 0x00f3ff;
            if (pType === 'HEALTH') colorHex = 0x00ff88;
            if (pType === 'QUAD') colorHex = 0xff007f;
            if (pType === 'BOOST') colorHex = 0xffcc00;

            const mat = new THREE.MeshStandardMaterial({
                color: colorHex,
                emissive: colorHex,
                emissiveIntensity: 0.8,
                wireframe: true
            });

            const pMesh = new THREE.Mesh(geo, mat);
            pMesh.position.copy(pos);
            pMesh.userData = { type: pType, radius: 1.2, rotSpeed: 0.03 };

            scene.add(pMesh);
            powerups.push(pMesh);
        }

        function createExplosion(pos, colorHex = 0xff5500, count = 30) {
            const geo = new THREE.BufferGeometry();
            const positions = [];
            const velocities = [];

            for (let i = 0; i < count; i++) {
                positions.push(pos.x, pos.y, pos.z);
                velocities.push(
                    (Math.random() - 0.5) * 1.5,
                    (Math.random() - 0.5) * 1.5,
                    (Math.random() - 0.5) * 1.5
                );
            }

            geo.setAttribute('position', new THREE.Float32BufferAttribute(positions, 3));
            const mat = new THREE.PointsMaterial({
                color: colorHex,
                size: 0.8,
                transparent: true,
                opacity: 1
            });

            const pSystem = new THREE.Points(geo, mat);
            pSystem.userData = { velocities: velocities, life: 1.0 };
            scene.add(pSystem);
            particleExplosions.push(pSystem);
        }

        // --- SHOOTING & WEAPONS ---
        function fireLaser() {
            if (!isGameRunning) return;
            audioSynth.playLaser();

            const isQuad = quadLaserTimer > 0;
            const offsets = isQuad ? [-2.0, -0.7, 0.7, 2.0] : [-1.8, 1.8];

            offsets.forEach(offX => {
                const laserGeo = new THREE.CylinderGeometry(0.08, 0.08, 2.5);
                laserGeo.rotateX(Math.PI / 2);
                const laserMat = new THREE.MeshBasicMaterial({ color: isQuad ? 0xff007f : 0x00f3ff });
                const laser = new THREE.Mesh(laserGeo, laserMat);

                // Spawn at Wingtip offset converted to world position
                const localSpawn = new THREE.Vector3(offX, 0, 1.5);
                localSpawn.applyQuaternion(playerShip.quaternion);
                laser.position.copy(playerShip.position).add(localSpawn);

                // Velocity directed along ship forward orientation
                const forward = new THREE.Vector3(0, 0, 1).applyQuaternion(playerShip.quaternion);
                laser.quaternion.copy(playerShip.quaternion);
                laser.userData = {
                    velocity: forward.multiplyScalar(4.5),
                    life: 80
                };

                scene.add(laser);
                playerLasers.push(laser);
            });
        }

        function enemyFireLaser(drone) {
            audioSynth.playEnemyLaser();
            const laserGeo = new THREE.SphereGeometry(0.4, 8, 8);
            const laserMat = new THREE.MeshBasicMaterial({ color: 0xff0055 });
            const laser = new THREE.Mesh(laserGeo, laserMat);

            laser.position.copy(drone.position);
            const dir = new THREE.Vector3().subVectors(playerShip.position, drone.position).normalize();
            laser.userData = {
                velocity: dir.multiplyScalar(2.2),
                life: 120
            };

            scene.add(laser);
            enemyLasers.push(laser);
        }

        // --- GAME WAVE MANAGER ---
        function spawnWave(waveNum) {
            // Spawn Asteroids around Player
            const numAsteroids = 10 + waveNum * 4;
            for (let i = 0; i < numAsteroids; i++) {
                const dist = 120 + Math.random() * 200;
                const theta = Math.random() * Math.PI * 2;
                const phi = (Math.random() - 0.5) * Math.PI;

                const x = playerShip.position.x + dist * Math.cos(phi) * Math.cos(theta);
                const y = playerShip.position.y + dist * Math.sin(phi);
                const z = playerShip.position.z + dist * Math.cos(phi) * Math.sin(theta);

                createAsteroid(x, y, z, 'LARGE');
            }

            // Spawn Enemy Drones
            const numDrones = 2 + Math.floor(waveNum * 1.5);
            for (let i = 0; i < numDrones; i++) {
                const dist = 150 + Math.random() * 100;
                const theta = Math.random() * Math.PI * 2;
                const x = playerShip.position.x + dist * Math.cos(theta);
                const y = playerShip.position.y + (Math.random() - 0.5) * 60;
                const z = playerShip.position.z + dist * Math.sin(theta);

                createEnemyDrone(x, y, z);
            }
        }

        // --- CONTROLS & CAMERA UPDATES ---
        function onMouseMove(e) {
            if (!isGameRunning) return;
            // Normalized Mouse Coordinates (-1 to 1)
            mouse.x = (e.clientX / window.innerWidth) * 2 - 1;
            mouse.y = -(e.clientY / window.innerHeight) * 2 + 1;
        }

        function setMobileDir(x, y) {
            mobileDir.x = x;
            mobileDir.y = y;
        }

        function mobileBoost(active) {
            isBoosting = active;
        }

        function mobileFire() {
            fireLaser();
        }

        function handleSpecialKeys(e) {
            if (e.code === 'KeyC') {
                thirdPersonCamera = !thirdPersonCamera;
            }
            if (e.code === 'Space') {
                if (isGameRunning) fireLaser();
            }
        }

        function triggerCameraShake(intensity = 0.8) {
            shakeDuration = 12;
            shakeIntensity = intensity;
        }

        // --- MAIN GAME LOOP ---
        function updateGame() {
            if (!isGameRunning) return;

            // 1. Player Flight Controls & Rotation
            const pitchSpeed = 0.035;
            const yawSpeed = 0.035;

            let inputPitch = -mouse.y + mobileDir.y;
            let inputYaw = -mouse.x - mobileDir.x;

            if (keys['KeyW'] || keys['ArrowUp']) inputPitch = -1;
            if (keys['KeyS'] || keys['ArrowDown']) inputPitch = 1;
            if (keys['KeyA'] || keys['ArrowLeft']) inputYaw = 1;
            if (keys['KeyD'] || keys['ArrowRight']) inputYaw = -1;

            // Apply Rotations to Player Quaternion
            playerShip.rotateX(inputPitch * pitchSpeed);
            playerShip.rotateY(inputYaw * yawSpeed);
            
            // Visual Bank/Roll Tilt effect
            playerShip.rotation.z = -inputYaw * 0.4;

            // Speed & Thrust
            isBoosting = keys['ShiftLeft'] || keys['ShiftRight'] || isBoosting;
            let currentSpeed = 0.8;

            if (isBoosting && boostEnergy > 0) {
                currentSpeed = 1.8;
                boostEnergy = Math.max(0, boostEnergy - 0.6);
            } else {
                boostEnergy = Math.min(100, boostEnergy + 0.25);
            }

            // Move Forward in Facing Direction
            const forwardDir = new THREE.Vector3(0, 0, 1).applyQuaternion(playerShip.quaternion);
            playerShip.position.add(forwardDir.multiplyScalar(currentSpeed));

            // Timers & Powerups
            if (quadLaserTimer > 0) {
                quadLaserTimer--;
                if (quadLaserTimer <= 0) {
                    document.getElementById('powerup-status').classList.add('hidden');
                }
            }

            // 2. Camera Positioning & Shake
            if (thirdPersonCamera) {
                const camOffset = new THREE.Vector3(0, 2.2, -8.5).applyQuaternion(playerShip.quaternion);
                camera.position.copy(playerShip.position).add(camOffset);
                
                const lookTarget = new THREE.Vector3(0, 0, 20).applyQuaternion(playerShip.quaternion).add(playerShip.position);
                camera.lookAt(lookTarget);
            } else {
                // First-person cockpit view
                const camOffset = new THREE.Vector3(0, 0.4, 0.2).applyQuaternion(playerShip.quaternion);
                camera.position.copy(playerShip.position).add(camOffset);
                const lookTarget = new THREE.Vector3(0, 0, 30).applyQuaternion(playerShip.quaternion).add(playerShip.position);
                camera.lookAt(lookTarget);
            }

            // Apply Camera Shake
            if (shakeDuration > 0) {
                camera.position.x += (Math.random() - 0.5) * shakeIntensity;
                camera.position.y += (Math.random() - 0.5) * shakeIntensity;
                shakeDuration--;
            }

            // 3. Update Player Lasers
            for (let i = playerLasers.length - 1; i >= 0; i--) {
                const laser = playerLasers[i];
                laser.position.add(laser.userData.velocity);
                laser.userData.life--;

                if (laser.userData.life <= 0) {
                    scene.remove(laser);
                    playerLasers.splice(i, 1);
                    continue;
                }

                // Check Hits against Asteroids
                for (let j = asteroids.length - 1; j >= 0; j--) {
                    const ast = asteroids[j];
                    if (laser.position.distanceTo(ast.position) < ast.userData.radius + 0.5) {
                        // Explosion & Destruction
                        createExplosion(ast.position, 0x8899aa, 20);
                        audioSynth.playExplosion(false);

                        // Split Large/Medium Asteroids into smaller ones
                        if (ast.userData.size === 'LARGE') {
                            createAsteroid(ast.position.x + 2, ast.position.y, ast.position.z, 'MEDIUM');
                            createAsteroid(ast.position.x - 2, ast.position.y, ast.position.z, 'MEDIUM');
                        } else if (ast.userData.size === 'MEDIUM') {
                            createAsteroid(ast.position.x + 1, ast.position.y, ast.position.z, 'SMALL');
                            createAsteroid(ast.position.x - 1, ast.position.y, ast.position.z, 'SMALL');
                        }

                        // Random chance to drop powerup
                        if (Math.random() < 0.15) spawnPowerup(ast.position);

                        score += 50;
                        statAsteroidsDestroyed++;

                        scene.remove(ast);
                        asteroids.splice(j, 1);

                        scene.remove(laser);
                        playerLasers.splice(i, 1);
                        break;
                    }
                }

                // Check Hits against Enemy Drones
                if (playerLasers[i]) {
                    for (let k = enemyDrones.length - 1; k >= 0; k--) {
                        const drone = enemyDrones[k];
                        if (laser.position.distanceTo(drone.position) < drone.userData.radius) {
                            drone.userData.health--;
                            createExplosion(laser.position, 0xff0055, 10);

                            if (drone.userData.health <= 0) {
                                createExplosion(drone.position, 0xff007f, 40);
                                audioSynth.playExplosion(true);
                                spawnPowerup(drone.position);
                                score += 250;
                                statDronesDestroyed++;
                                scene.remove(drone);
                                enemyDrones.splice(k, 1);
                            }

                            scene.remove(laser);
                            playerLasers.splice(i, 1);
                            break;
                        }
                    }
                }
            }

            // 4. Update Enemy Lasers
            for (let i = enemyLasers.length - 1; i >= 0; i--) {
                const elaser = enemyLasers[i];
                elaser.position.add(elaser.userData.velocity);
                elaser.userData.life--;

                if (elaser.userData.life <= 0) {
                    scene.remove(elaser);
                    enemyLasers.splice(i, 1);
                    continue;
                }

                // Check Hit Player
                if (elaser.position.distanceTo(playerShip.position) < 2.0) {
                    takeDamage(15);
                    scene.remove(elaser);
                    enemyLasers.splice(i, 1);
                }
            }

            // 5. Update Asteroids Movement & Player Collision
            asteroids.forEach(ast => {
                ast.rotation.x += ast.userData.rotSpeed.x;
                ast.rotation.y += ast.userData.rotSpeed.y;
                ast.position.add(ast.userData.velocity);

                if (ast.position.distanceTo(playerShip.position) < ast.userData.radius + 1.2) {
                    takeDamage(25);
                    createExplosion(ast.position, 0xffaa00, 25);
                }
            });

            // 6. Update Enemy Drones AI Behavior
            const now = Date.now();
            enemyDrones.forEach(drone => {
                drone.userData.ringMesh.rotation.z += 0.05;

                // Move slowly toward player
                const dirToPlayer = new THREE.Vector3().subVectors(playerShip.position, drone.position).normalize();
                drone.position.add(dirToPlayer.multiplyScalar(0.4));

                // Shoot at player periodically
                if (now - drone.userData.lastShot > 2200) {
                    if (drone.position.distanceTo(playerShip.position) < 180) {
                        enemyFireLaser(drone);
                        drone.userData.lastShot = now;
                    }
                }
            });

            // 7. Update Powerups
            for (let i = powerups.length - 1; i >= 0; i--) {
                const p = powerups[i];
                p.rotation.y += p.userData.rotSpeed;

                if (p.position.distanceTo(playerShip.position) < 3.0) {
                    audioSynth.playPowerup();

                    if (p.userData.type === 'HEALTH') {
                        shield = Math.min(100, shield + 35);
                    } else if (p.userData.type === 'QUAD') {
                        quadLaserTimer = 400; // 400 frames of quad laser
                        document.getElementById('powerup-text').innerText = "CUÁDRUPLE LÁSER ACTIVO";
                        document.getElementById('powerup-status').classList.remove('hidden');
                    } else if (p.userData.type === 'BOOST') {
                        boostEnergy = 100;
                    }

                    scene.remove(p);
                    powerups.splice(i, 1);
                }
            }

            // 8. Update Particle Explosions
            for (let i = particleExplosions.length - 1; i >= 0; i--) {
                const ps = particleExplosions[i];
                const positions = ps.geometry.attributes.position.array;
                const vels = ps.userData.velocities;

                for (let j = 0; j < vels.length / 3; j++) {
                    positions[j * 3] += vels[j * 3];
                    positions[j * 3 + 1] += vels[j * 3 + 1];
                    positions[j * 3 + 2] += vels[j * 3 + 2];
                }

                ps.geometry.attributes.position.needsUpdate = true;
                ps.userData.life -= 0.035;
                ps.material.opacity = ps.userData.life;

                if (ps.userData.life <= 0) {
                    scene.remove(ps);
                    particleExplosions.splice(i, 1);
                }
            }

            // Check Next Wave Condition
            if (asteroids.length === 0 && enemyDrones.length === 0) {
                wave++;
                spawnWave(wave);
            }

            // Update HUD Displays
            updateHUDUI();
            drawRadar();
        }

        function takeDamage(amount) {
            shield -= amount;
            triggerCameraShake(1.2);
            audioSynth.playExplosion(false);

            if (shield <= 0) {
                shield = 0;
                gameOver();
            }
        }

        function updateHUDUI() {
            document.getElementById('hud-shield-val').innerText = `${Math.round(shield)}%`;
            document.getElementById('hud-shield-bar').style.width = `${shield}%`;
            document.getElementById('hud-boost-val').innerText = `${Math.round(boostEnergy)}%`;
            document.getElementById('hud-boost-bar').style.width = `${boostEnergy}%`;
            document.getElementById('hud-score').innerText = score;
            document.getElementById('hud-wave').innerText = wave;
        }

        function drawRadar() {
            const canvas = document.getElementById('radar-canvas');
            const ctx = canvas.getContext('2d');
            const radius = canvas.width / 2;

            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Radar Grid Rings
            ctx.strokeStyle = 'rgba(0, 243, 255, 0.25)';
            ctx.beginPath();
            ctx.arc(radius, radius, radius - 4, 0, Math.PI * 2);
            ctx.arc(radius, radius, radius / 2, 0, Math.PI * 2);
            ctx.stroke();

            // Center Player Dot
            ctx.fillStyle = '#00f3ff';
            ctx.beginPath();
            ctx.arc(radius, radius, 3, 0, Math.PI * 2);
            ctx.fill();

            const radarRange = 220;

            // Draw Asteroids on Radar
            asteroids.forEach(ast => {
                const relPos = new THREE.Vector3().subVectors(ast.position, playerShip.position);
                if (relPos.length() < radarRange) {
                    const rx = radius + (relPos.x / radarRange) * (radius - 10);
                    const ry = radius + (relPos.z / radarRange) * (radius - 10);

                    ctx.fillStyle = '#94a3b8';
                    ctx.beginPath();
                    ctx.arc(rx, ry, 2, 0, Math.PI * 2);
                    ctx.fill();
                }
            });

            // Draw Enemy Drones on Radar
            enemyDrones.forEach(drone => {
                const relPos = new THREE.Vector3().subVectors(drone.position, playerShip.position);
                if (relPos.length() < radarRange) {
                    const rx = radius + (relPos.x / radarRange) * (radius - 10);
                    const ry = radius + (relPos.z / radarRange) * (radius - 10);

                    ctx.fillStyle = '#ff0055';
                    ctx.beginPath();
                    ctx.arc(rx, ry, 3.5, 0, Math.PI * 2);
                    ctx.fill();
                }
            });
        }

        function renderAnimate() {
            requestAnimationFrame(renderAnimate);
            updateGame();
            renderer.render(scene, camera);
        }

        function onResize() {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        }

        // --- GAME FLOW MANAGERS ---
        function startGame() {
            audioSynth.init();

            // Clear entities
            asteroids.forEach(a => scene.remove(a));
            enemyDrones.forEach(d => scene.remove(d));
            playerLasers.forEach(l => scene.remove(l));
            enemyLasers.forEach(el => scene.remove(el));
            powerups.forEach(p => scene.remove(p));

            asteroids = [];
            enemyDrones = [];
            playerLasers = [];
            enemyLasers = [];
            powerups = [];

            // Reset States
            playerShip.position.set(0, 0, 0);
            playerShip.quaternion.set(0, 0, 0, 1);
            score = 0;
            wave = 1;
            shield = 100;
            boostEnergy = 100;
            quadLaserTimer = 0;
            statAsteroidsDestroyed = 0;
            statDronesDestroyed = 0;

            isGameRunning = true;

            // Spawn first wave
            spawnWave(wave);

            // UI adjustments
            document.getElementById('ui-overlay').classList.add('opacity-0', 'pointer-events-none');
            document.getElementById('start-screen').classList.add('hidden');
            document.getElementById('gameover-screen').classList.add('hidden');
            document.getElementById('hud').classList.remove('opacity-0');
        }

        function gameOver() {
            isGameRunning = false;

            if (score > highScore) {
                highScore = score;
                localStorage.setItem('starfighter_high_score', highScore);
            }

            document.getElementById('final-score').innerText = score;
            document.getElementById('final-wave').innerText = wave;
            document.getElementById('final-asteroids').innerText = statAsteroidsDestroyed;
            document.getElementById('final-drones').innerText = statDronesDestroyed;
            document.getElementById('hud-high').innerText = highScore;

            document.getElementById('hud').classList.add('opacity-0');
            document.getElementById('ui-overlay').classList.remove('opacity-0', 'pointer-events-none');
            document.getElementById('gameover-screen').classList.remove('hidden');
        }

        window.onload = () => {
            initThreeEngine();
            renderAnimate();
        };
    </script>
</body>
</html>