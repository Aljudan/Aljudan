<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ALJUDAN // Cyberpunk Hero Banner</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        body {
            background-color: #030303;
            color: #E2E8F0;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            user-select: none;
        }

        .font-orbitron {
            font-family: 'Orbitron', sans-serif;
        }

        .font-mono-tech {
            font-family: 'Share Tech Mono', monospace;
        }

        /* Scanline Overlay Effect */
        .scanlines {
            background: linear-gradient(
                to bottom,
                rgba(255,255,255,0),
                rgba(255,255,255,0) 50%,
                rgba(0, 0, 0, 0.4) 50%,
                rgba(0, 0, 0, 0.4)
            );
            background-size: 100% 4px;
            pointer-events: none;
        }

        /* Subtle Crimson Ambient Glow */
        .crimson-glow {
            text-shadow: 0 0 20px rgba(192, 0, 0, 0.75), 0 0 40px rgba(139, 0, 0, 0.4);
        }

        .crimson-box-glow {
            box-shadow: 0 0 25px rgba(192, 0, 0, 0.25), inset 0 0 15px rgba(192, 0, 0, 0.15);
        }

        /* CSS Glitch Effect for ALJUDAN Title */
        .glitch-text {
            position: relative;
            display: inline-block;
        }

        .glitch-text::before,
        .glitch-text::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            clip: rect(0, 0, 0, 0);
        }

        .glitch-active::before {
            left: -2px;
            text-shadow: 2px 0 #C00000;
            clip: rect(24px, 550px, 90px, 0);
            animation: glitch-anim 2s infinite linear alternate-reverse;
        }

        .glitch-active::after {
            left: 2px;
            text-shadow: -2px 0 #8B0000;
            clip: rect(85px, 550px, 140px, 0);
            animation: glitch-anim2 2.5s infinite linear alternate-reverse;
        }

        @keyframes glitch-anim {
            0% { clip: rect(12px, 9999px, 54px, 0); }
            20% { clip: rect(78px, 9999px, 12px, 0); }
            40% { clip: rect(32px, 9999px, 89px, 0); }
            60% { clip: rect(90px, 9999px, 6px, 0); }
            80% { clip: rect(45px, 9999px, 67px, 0); }
            100% { clip: rect(10px, 9999px, 98px, 0); }
        }

        @keyframes glitch-anim2 {
            0% { clip: rect(60px, 9999px, 20px, 0); }
            20% { clip: rect(10px, 9999px, 80px, 0); }
            40% { clip: rect(85px, 9999px, 30px, 0); }
            60% { clip: rect(20px, 9999px, 90px, 0); }
            80% { clip: rect(50px, 9999px, 10px, 0); }
            100% { clip: rect(95px, 9999px, 40px, 0); }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #050505;
        }
        ::-webkit-scrollbar-thumb {
            background: #3D0000;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #8B0000;
        }
    </style>
</head>
<body class="min-h-screen bg-[#050505] text-gray-200 flex flex-col items-center justify-between p-3 sm:p-6 md:p-8 select-none">

    <!-- Navigation / Toolbar Header -->
    <header class="w-full max-w-7xl flex flex-col sm:flex-row justify-between items-center gap-4 mb-4 z-20">
        <div class="flex items-center space-x-3">
            <div class="w-3 h-3 bg-[#C00000] rounded-full animate-ping"></div>
            <span class="font-mono-tech text-xs tracking-widest text-red-500/80 uppercase">STATUS: SYSTEM OVERRIDE // ALJUDAN ONLINE</span>
        </div>

        <!-- Controls Group -->
        <div class="flex flex-wrap items-center justify-center gap-2 sm:gap-3">
            <button id="audio-toggle" class="flex items-center space-x-2 px-3 py-1.5 bg-[#0A0A0A] border border-[#3D0000] hover:border-[#C00000] rounded-md transition duration-300 text-xs font-mono-tech text-gray-300 hover:text-white">
                <svg id="audio-icon" class="w-4 h-4 text-red-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5.586 15H4a1 1 1 01-1-1v-4a1 1 1 011-1h1.586l4.707-4.707C10.923 3.663 12 4.109 12 5v14c0 .891-1.077 1.337-1.707.707L5.586 15z"></path>
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2"></path>
                </svg>
                <span id="audio-text">AMBIENT: OFF</span>
            </button>

            <button id="glitch-toggle" class="flex items-center space-x-2 px-3 py-1.5 bg-[#0A0A0A] border border-[#3D0000] hover:border-[#C00000] rounded-md transition duration-300 text-xs font-mono-tech text-gray-300 hover:text-white">
                <svg class="w-4 h-4 text-red-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path>
                </svg>
                <span>BURST GLITCH</span>
            </button>

            <button id="export-btn" class="flex items-center space-x-2 px-4 py-1.5 bg-[#8B0000] hover:bg-[#C00000] text-white rounded-md transition duration-300 text-xs font-mono-tech shadow-lg shadow-red-900/30">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-4l-4 4m0 0l-4-4m4 4V4"></path>
                </svg>
                <span>EXPORT BANNER</span>
            </button>
        </div>
    </header>

    <!-- Main 16:9 Hero Banner Container -->
    <main class="relative w-full max-w-7xl aspect-[16/9] bg-[#050505] rounded-xl overflow-hidden border border-[#3D0000]/60 shadow-2xl crimson-box-glow my-auto flex flex-col justify-between p-6 sm:p-10 md:p-14 group">
        
        <!-- Interactive HTML Canvas background -->
        <canvas id="hero-canvas" class="absolute inset-0 w-full h-full object-cover z-0 cursor-crosshair"></canvas>

        <!-- Scanlines layer -->
        <div id="scanline-layer" class="scanlines absolute inset-0 z-10 opacity-70 pointer-events-none"></div>

        <!-- Ambient Vignette Layer -->
        <div class="absolute inset-0 bg-radial-vignette pointer-events-none z-10" style="background: radial-gradient(circle at center, transparent 40%, rgba(5,5,5,0.85) 100%);"></div>

        <!-- Overlay Layer 1: HUD Grid & Corner Accents -->
        <div class="absolute inset-0 z-20 pointer-events-none p-4 sm:p-8 flex flex-col justify-between">
            <!-- Top HUD info -->
            <div class="flex justify-between items-start font-mono-tech text-[10px] sm:text-xs text-red-500/60 tracking-wider">
                <div class="flex items-center space-x-2">
                    <span class="inline-block w-2 h-2 bg-[#C00000]"></span>
                    <span>SEC_LEVEL: RED // [PIRATE_NET]</span>
                </div>
                <div class="text-right">
                    <span>POS: 35.6762° N, 139.6503° E</span>
                    <br>
                    <span id="hud-clock" class="text-gray-500">00:00:00 UTC</span>
                </div>
            </div>

            <!-- Bottom HUD Accent Lines -->
            <div class="flex justify-between items-end font-mono-tech text-[10px] sm:text-xs text-red-500/50">
                <div>
                    <span class="text-gray-600 block">SYSTEM OVERRIDE ENGINE v4.0.4</span>
                    <span class="text-red-700">SYS.LOC // RED_SEAS_ABYSS</span>
                </div>
                <div class="flex space-x-1">
                    <span class="w-1.5 h-3 bg-[#C00000]"></span>
                    <span class="w-1.5 h-3 bg-[#8B0000]"></span>
                    <span class="w-1.5 h-3 bg-[#3D0000]"></span>
                    <span class="w-1.5 h-3 bg-gray-800"></span>
                </div>
            </div>
        </div>

        <!-- Overlay Layer 2: Main Banner Content / Typography -->
        <div class="relative z-20 h-full flex flex-col justify-center max-w-xl pointer-events-none">
            <!-- Subtitle badge -->
            <div class="inline-flex items-center space-x-2 bg-[#180000]/80 border border-[#8B0000]/40 px-3 py-1 rounded-sm w-fit mb-3 backdrop-blur-sm">
                <span class="w-1.5 h-1.5 bg-[#C00000] rounded-full animate-pulse"></span>
                <p class="font-mono-tech text-xs sm:text-sm text-red-400 tracking-widest uppercase">
                    404 // ENTER THE VOID
                </p>
            </div>

            <!-- MAIN TITLE: ALJUDAN -->
            <h1 id="main-title" class="glitch-text font-orbitron font-black text-5xl sm:text-7xl md:text-8xl lg:text-9xl text-white tracking-tighter uppercase leading-none crimson-glow my-2" data-text="ALJUDAN">
                ALJUDAN
            </h1>

            <!-- Stylized Tagline / Description -->
            <p class="font-mono-tech text-xs sm:text-sm md:text-base text-gray-400 mt-2 sm:mt-4 leading-relaxed max-w-md bg-gradient-to-r from-[#050505]/90 to-transparent p-2 border-l-2 border-[#C00000]">
                ARCHITECT OF DIGITAL ANARCHY // NAVIGATING THE CYBERNETIC UNKNOWN.
            </p>

            <!-- Abstract Visual Accent Lines -->
            <div class="mt-6 flex items-center space-x-3 opacity-80">
                <div class="h-0.5 w-16 bg-[#C00000]"></div>
                <div class="h-0.5 w-4 bg-[#8B0000]"></div>
                <div class="h-0.5 w-2 bg-gray-600"></div>
                <span class="font-mono-tech text-[10px] text-gray-500 tracking-widest">SUB-NET // 0x7F89A</span>
            </div>
        </div>

    </main>

    <!-- Footer / Instructions -->
    <footer class="w-full max-w-7xl mt-4 flex flex-col sm:flex-row items-center justify-between text-xs font-mono-tech text-gray-500 gap-2 z-20">
        <p>✦ MOVE MOUSE OVER BANNER FOR INTERACTIVE PARALLAX & EMBERS</p>
        <p class="text-red-900/80">OPTIMIZED FOR HIGH-END GITHUB LANDING PAGES (16:9)</p>
    </footer>

    <script>
        const canvas = document.getElementById('hero-canvas');
        const ctx = canvas.getContext('2d');
        const mainTitle = document.getElementById('main-title');
        const hudClock = document.getElementById('hud-clock');

        // Mouse Parallax & Dynamic Light State
        let mouseX = 0;
        let mouseY = 0;
        let targetMouseX = 0;
        let targetMouseY = 0;
        let isHovered = false;

        // Visual Particles Array
        const particles = [];
        const particleCount = 75;

        // Audio System State (Web Audio API Drone)
        let audioCtx = null;
        let isAudioPlaying = false;
        let masterGain = null;
        let osc1 = null;
        let osc2 = null;

        // Resize Canvas with high DPI support
        function resizeCanvas() {
            const rect = canvas.getBoundingClientRect();
            canvas.width = rect.width;
            canvas.height = rect.height;
        }

        window.addEventListener('resize', resizeCanvas);

        // Update Clock
        function updateClock() {
            const now = new Date();
            hudClock.innerText = now.toUTCString().split(' ')[4] + ' UTC';
        }
        setInterval(updateClock, 1000);
        updateClock();

        // Particle Class (Embers & Code Dust)
        class Particle {
            constructor() {
                this.reset();
            }

            reset() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = (Math.random() - 0.3) * 0.8;
                this.speedY = -(Math.random() * 1.2 + 0.3); // Drift upward like ashes
                this.opacity = Math.random() * 0.7 + 0.3;
                this.color = Math.random() > 0.3 ? '#C00000' : (Math.random() > 0.5 ? '#8B0000' : '#FFFFFF');
                this.life = Math.random() * 200 + 100;
                this.maxLife = this.life;
            }

            update() {
                this.x += this.speedX + (mouseX - canvas.width / 2) * 0.0005;
                this.y += this.speedY;
                this.life--;

                if (this.life <= 0 || this.y < 0 || this.x < 0 || this.x > canvas.width) {
                    this.reset();
                    this.y = canvas.height + 10;
                }
            }

            draw() {
                const currentOpacity = (this.life / this.maxLife) * this.opacity;
                ctx.save();
                ctx.globalAlpha = currentOpacity;
                ctx.fillStyle = this.color;
                ctx.shadowColor = '#C00000';
                ctx.shadowBlur = this.size * 4;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // Initialize Particles
        for (let i = 0; i < particleCount; i++) {
            particles.push(new Particle());
        }

        function drawCitySkyline(parallaxX, parallaxY) {
            const w = canvas.width;
            const h = canvas.height;

            // Distant Industrial Silhouette Structures
            ctx.save();
            ctx.fillStyle = '#080202';
            ctx.beginPath();

            // Layer 1: Far Buildings
            const layer1X = parallaxX * 0.02;
            ctx.rect(w * 0.1 + layer1X, h * 0.35, w * 0.08, h * 0.65);
            ctx.rect(w * 0.22 + layer1X, h * 0.45, w * 0.06, h * 0.55);
            ctx.rect(w * 0.35 + layer1X, h * 0.3, w * 0.12, h * 0.7);
            ctx.rect(w * 0.55 + layer1X, h * 0.25, w * 0.1, h * 0.75);
            ctx.rect(w * 0.7 + layer1X, h * 0.4, w * 0.15, h * 0.6);
            ctx.fill();

            // Layer 2: Closer Silhouette with Cranes & Antennas
            ctx.fillStyle = '#0A0505';
            const layer2X = parallaxX * 0.05;
            ctx.beginPath();
            ctx.rect(w * 0.05 + layer2X, h * 0.5, w * 0.12, h * 0.5);
            ctx.rect(w * 0.28 + layer2X, h * 0.4, w * 0.09, h * 0.6);
            ctx.rect(w * 0.48 + layer2X, h * 0.55, w * 0.14, h * 0.45);
            ctx.rect(w * 0.68 + layer2X, h * 0.32, w * 0.08, h * 0.68);
            ctx.rect(w * 0.82 + layer2X, h * 0.48, w * 0.12, h * 0.52);
            ctx.fill();

            // Subtle Red Neon Windows / Lights in Distance
            ctx.fillStyle = 'rgba(192, 0, 0, 0.4)';
            ctx.fillRect(w * 0.3 + layer2X, h * 0.45, 2, 12);
            ctx.fillRect(w * 0.31 + layer2X, h * 0.48, 2, 8);
            ctx.fillRect(w * 0.7 + layer2X, h * 0.38, 3, 20);
            ctx.fillRect(w * 0.72 + layer2X, h * 0.42, 2, 15);

            ctx.restore();
        }

        function drawPirateCharacter(parallaxX, parallaxY) {
            const w = canvas.width;
            const h = canvas.height;

            // Anchor point for central-right character positioning
            const charX = w * 0.72 + parallaxX * 0.08;
            const charY = h * 0.88 + parallaxY * 0.04;
            const scale = Math.min(w, h) * 0.0028;

            ctx.save();
            ctx.translate(charX, charY);

            // Time-based wind animation for coat movement
            const time = Date.now() * 0.003;
            const coatFlutter1 = Math.sin(time) * 12 * scale;
            const coatFlutter2 = Math.cos(time * 1.3) * 18 * scale;

            // Character Dynamic Crimson Rim Light Blur
            ctx.shadowColor = '#C00000';
            ctx.shadowBlur = 35;

            // --- 1. Long Coat (Back & Tail) - Swaying in Wind ---
            ctx.fillStyle = '#050505';
            ctx.strokeStyle = '#C00000';
            ctx.lineWidth = 2.5 * scale;

            ctx.beginPath();
            // Left Coat Flare
            ctx.moveTo(-35 * scale, -110 * scale);
            ctx.quadraticCurveTo(-70 * scale + coatFlutter1, -50 * scale, -110 * scale + coatFlutter2, 10 * scale);
            ctx.quadraticCurveTo(-60 * scale, -10 * scale, -25 * scale, -20 * scale);

            // Right Coat Flare
            ctx.lineTo(25 * scale, -20 * scale);
            ctx.quadraticCurveTo(55 * scale, -10 * scale, 90 * scale + coatFlutter1 * 0.5, 15 * scale);
            ctx.quadraticCurveTo(60 * scale + coatFlutter2 * 0.5, -40 * scale, 35 * scale, -110 * scale);
            ctx.closePath();
            ctx.fill();
            ctx.stroke();

            // --- 2. Main Body Silhouette ---
            ctx.fillStyle = '#080808';
            ctx.beginPath();
            // Legs/Boots
            ctx.rect(-22 * scale, -40 * scale, 16 * scale, 45 * scale);
            ctx.rect(6 * scale, -40 * scale, 16 * scale, 45 * scale);
            // Torso & Shoulders
            ctx.moveTo(-30 * scale, -120 * scale);
            ctx.lineTo(30 * scale, -120 * scale);
            ctx.lineTo(22 * scale, -40 * scale);
            ctx.lineTo(-22 * scale, -40 * scale);
            ctx.closePath();
            ctx.fill();

            // --- 3. High Collar / Bandana & Mysterious Head ---
            // Neck / High Cyber Collar
            ctx.beginPath();
            ctx.moveTo(-18 * scale, -120 * scale);
            ctx.lineTo(-24 * scale, -145 * scale);
            ctx.lineTo(24 * scale, -145 * scale);
            ctx.lineTo(18 * scale, -120 * scale);
            ctx.closePath();
            ctx.fill();
            ctx.stroke();

            // Head & Anime Hair Silhouette
            ctx.beginPath();
            ctx.arc(0, -158 * scale, 16 * scale, 0, Math.PI * 2);
            ctx.fill();

            // Spiky Anime Hair Strokes Silhouette
            ctx.beginPath();
            ctx.moveTo(-14 * scale, -162 * scale);
            ctx.lineTo(-28 * scale, -170 * scale);
            ctx.lineTo(-12 * scale, -174 * scale);
            ctx.lineTo(-5 * scale, -188 * scale);
            ctx.lineTo(8 * scale, -176 * scale);
            ctx.lineTo(22 * scale, -182 * scale);
            ctx.lineTo(16 * scale, -165 * scale);
            ctx.lineTo(26 * scale, -156 * scale);
            ctx.lineTo(14 * scale, -148 * scale);
            ctx.closePath();
            ctx.fill();
            ctx.stroke();

            // --- 4. Crimson Rim Highlights on Edges ---
            ctx.shadowBlur = 15;
            ctx.strokeStyle = '#FF2222';
            ctx.lineWidth = 1.8 * scale;

            // Hair Highlights
            ctx.beginPath();
            ctx.moveTo(-28 * scale, -170 * scale);
            ctx.lineTo(-12 * scale, -174 * scale);
            ctx.lineTo(-5 * scale, -188 * scale);
            ctx.stroke();

            // Shoulder Rim Highlights
            ctx.beginPath();
            ctx.moveTo(-32 * scale, -120 * scale);
            ctx.lineTo(-24 * scale, -145 * scale);
            ctx.moveTo(32 * scale, -120 * scale);
            ctx.lineTo(24 * scale, -145 * scale);
            ctx.stroke();

            ctx.restore();
        }

        function render() {
            // Smooth Parallax Interpolation
            mouseX += (targetMouseX - mouseX) * 0.05;
            mouseY += (targetMouseY - mouseY) * 0.05;

            const parallaxX = (mouseX - canvas.width / 2);
            const parallaxY = (mouseY - canvas.height / 2);

            // Clear Background
            ctx.fillStyle = '#050505';
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // 1. Soft Red Radial Ambient Lighting behind character
            const glowGradient = ctx.createRadialGradient(
                canvas.width * 0.7, canvas.height * 0.5, 20,
                canvas.width * 0.7, canvas.height * 0.5, canvas.width * 0.45
            );
            glowGradient.addColorStop(0, 'rgba(192, 0, 0, 0.28)');
            glowGradient.addColorStop(0.5, 'rgba(61, 0, 0, 0.12)');
            glowGradient.addColorStop(1, 'rgba(5, 5, 5, 0)');
            ctx.fillStyle = glowGradient;
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            // 2. Cyberpunk Background Cityscape
            drawCitySkyline(parallaxX, parallaxY);

            // 3. Interactive Volumetric Fog / Smoke
            ctx.save();
            ctx.globalAlpha = 0.15;
            const fogGrad = ctx.createLinearGradient(0, canvas.height * 0.4, 0, canvas.height);
            fogGrad.addColorStop(0, 'transparent');
            fogGrad.addColorStop(0.5, '#3D0000');
            fogGrad.addColorStop(1, '#050505');
            ctx.fillStyle = fogGrad;
            ctx.fillRect(0, canvas.height * 0.4, canvas.width, canvas.height * 0.6);
            ctx.restore();

            // 4. Pirate Character Render
            drawPirateCharacter(parallaxX, parallaxY);

            // 5. Update & Render Flying Crimson Embers/Particles
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });

            // 6. Interactive Cursor Crimson Light Effect
            if (isHovered) {
                const cursorGlow = ctx.createRadialGradient(
                    mouseX, mouseY, 0,
                    mouseX, mouseY, 180
                );
                cursorGlow.addColorStop(0, 'rgba(192, 0, 0, 0.15)');
                cursorGlow.addColorStop(1, 'rgba(0, 0, 0, 0)');
                ctx.fillStyle = cursorGlow;
                ctx.beginPath();
                ctx.arc(mouseX, mouseY, 180, 0, Math.PI * 2);
                ctx.fill();
            }

            requestAnimationFrame(render);
        }

        // Mouse Parallax Trackers
        canvas.addEventListener('mousemove', (e) => {
            const rect = canvas.getBoundingClientRect();
            targetMouseX = e.clientX - rect.left;
            targetMouseY = e.clientY - rect.top;
            isHovered = true;
        });

        canvas.addEventListener('mouseleave', () => {
            targetMouseX = canvas.width / 2;
            targetMouseY = canvas.height / 2;
            isHovered = false;
        });

        function toggleAudio() {
            const audioText = document.getElementById('audio-text');
            const audioIcon = document.getElementById('audio-icon');

            if (!isAudioPlaying) {
                // Initialize Audio Context on user interaction
                if (!audioCtx) {
                    audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                }

                if (audioCtx.state === 'suspended') {
                    audioCtx.resume();
                }

                // Master Gain
                masterGain = audioCtx.createGain();
                masterGain.gain.setValueAtTime(0.12, audioCtx.currentTime);
                masterGain.connect(audioCtx.destination);

                // Deep Cyber Synth Drone Oscillator 1
                osc1 = audioCtx.createOscillator();
                osc1.type = 'sawtooth';
                osc1.frequency.setValueAtTime(55, audioCtx.currentTime); // A1 note

                // Lowpass Filter for Dark Ambiance
                const filter = audioCtx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.setValueAtTime(220, audioCtx.currentTime);

                // Sub Oscillator 2
                osc2 = audioCtx.createOscillator();
                osc2.type = 'sine';
                osc2.frequency.setValueAtTime(27.5, audioCtx.currentTime); // A0 Sub

                osc1.connect(filter);
                osc2.connect(filter);
                filter.connect(masterGain);

                osc1.start();
                osc2.start();

                isAudioPlaying = true;
                audioText.innerText = "AMBIENT: ON";
                audioIcon.classList.add("animate-pulse");
            } else {
                if (masterGain) {
                    masterGain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + 0.5);
                    setTimeout(() => {
                        osc1.stop();
                        osc2.stop();
                        isAudioPlaying = false;
                        audioText.innerText = "AMBIENT: OFF";
                        audioIcon.classList.remove("animate-pulse");
                    }, 500);
                }
            }
        }

        document.getElementById('audio-toggle').addEventListener('click', toggleAudio);

        document.getElementById('glitch-toggle').addEventListener('click', () => {
            mainTitle.classList.add('glitch-active');
            setTimeout(() => {
                mainTitle.classList.remove('glitch-active');
            }, 1200);
        });

        // Export Rendered Banner as Image
        document.getElementById('export-btn').addEventListener('click', () => {
            // Render one frame clear of overlays to canvas
            const tempCanvas = document.createElement('canvas');
            tempCanvas.width = 1920;
            tempCanvas.height = 1080;
            const tempCtx = tempCanvas.getContext('2d');

            // Draw current canvas state stretched to crisp 1080p
            tempCtx.drawImage(canvas, 0, 0, 1920, 1080);

            // Overlay Text Burn on PNG
            tempCtx.save();
            tempCtx.fillStyle = "#FFFFFF";
            tempCtx.font = "900 120px Orbitron, sans-serif";
            tempCtx.shadowColor = "#C00000";
            tempCtx.shadowBlur = 30;
            tempCtx.fillText("ALJUDAN", 120, 580);

            tempCtx.fillStyle = "#FF4444";
            tempCtx.font = "24px 'Share Tech Mono', monospace";
            tempCtx.fillText("404 // ENTER THE VOID", 125, 450);
            tempCtx.restore();

            // Trigger Download
            const imageURI = tempCanvas.toDataURL('image/png');
            const link = document.createElement('a');
            link.download = 'ALJUDAN-GitHub-Hero-Banner.png';
            link.href = imageURI;
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        });

        // Initialize Canvas Size & Start Animation Loop
        window.onload = () => {
            resizeCanvas();
            targetMouseX = canvas.width / 2;
            targetMouseY = canvas.height / 2;
            render();
        };
    </script>
</body>
</html>
