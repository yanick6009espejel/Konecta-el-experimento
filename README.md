```html
<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Konecta | EL EXPERIMENTO</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700;900&family=Manrope:wght@200;400;600;800&family=Syncopate:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Tipografías y Variables */
        :root {
            --gold: #D4AF37;
            --dark-bg: #030303;
        }
        body {
            font-family: 'Manrope', sans-serif;
            background-color: var(--dark-bg);
            color: #ffffff;
            overflow-x: hidden;
        }
        h1, h2, h3, .font-cinzel {
            font-family: 'Cinzel', serif;
        }
        .font-syncopate {
            font-family: 'Syncopate', sans-serif;
        }

        /* Efectos Visuales Premium */
        .glass-panel {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .gold-text {
            background: linear-gradient(to right, #BF953F, #FCF6BA, #B38728, #FBF5B7, #AA771C);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        /* Botón Rojo Magnético */
        .btn-red-glow {
            background: linear-gradient(135deg, #8b0000 0%, #ff0000 100%);
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.4), inset 0 0 10px rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        .btn-red-glow:hover, .btn-red-glow:active {
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.8), inset 0 0 15px rgba(255, 255, 255, 0.4);
            transform: scale(1.02);
        }

        /* Auras de los Especialistas */
        .aura-card {
            position: relative;
            overflow: hidden;
            transition: transform 0.4s ease;
        }
        .aura-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, var(--aura-color) 0%, transparent 60%);
            opacity: 0.15;
            z-index: 0;
            pointer-events: none;
            transition: opacity 0.4s ease;
        }
        .aura-card:hover::before, .aura-card:active::before {
            opacity: 0.3;
        }
        .aura-content {
            position: relative;
            z-index: 1;
        }
        
        /* Colores Específicos */
        .aura-orange { --aura-color: #ff8c00; border-left: 2px solid #ff8c00; }
        .aura-white { --aura-color: #ffffff; border-left: 2px solid #ffffff; }
        .aura-pink { --aura-color: #ff1493; border-left: 2px solid #ff1493; }
        .aura-gray { --aura-color: #a9a9a9; border-left: 2px solid #a9a9a9; }
        .aura-red { --aura-color: #ff0000; border-left: 2px solid #ff0000; }
        .aura-green { --aura-color: #00ff00; border-left: 2px solid #00ff00; }
        .aura-purple { --aura-color: #8a2be2; border-left: 2px solid #8a2be2; }
        .aura-yellow { --aura-color: #ffd700; border-left: 2px solid #ffd700; }

        /* Background Smoke Fijo */
        .bg-smoke {
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background: radial-gradient(circle at 50% 50%, rgba(20,20,20,0.8) 0%, #030303 100%);
            z-index: -2;
        }
        .bg-orb {
            position: fixed;
            top: 20%; left: 50%; transform: translate(-50%, -50%);
            width: 300px; height: 300px;
            background: radial-gradient(circle, rgba(212, 175, 55, 0.08) 0%, transparent 70%);
            filter: blur(40px);
            z-index: -1;
            animation: pulse 8s infinite alternate;
        }

        /* Animaciones */
        @keyframes pulse {
            0% { transform: translate(-50%, -50%) scale(1); opacity: 0.5; }
            100% { transform: translate(-50%, -50%) scale(1.5); opacity: 1; }
        }
        @keyframes glitch {
            0% { text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), -0.025em 0.05em 0 rgba(0,0,255,0.75); }
            14% { text-shadow: 0.05em 0 0 rgba(255,0,0,0.75), -0.05em -0.025em 0 rgba(0,255,0,0.75), -0.025em 0.05em 0 rgba(0,0,255,0.75); }
            15% { text-shadow: -0.05em -0.025em 0 rgba(255,0,0,0.75), 0.025em 0.025em 0 rgba(0,255,0,0.75), -0.05em -0.05em 0 rgba(0,0,255,0.75); }
            49% { text-shadow: -0.05em -0.025em 0 rgba(255,0,0,0.75), 0.025em 0.025em 0 rgba(0,255,0,0.75), -0.05em -0.05em 0 rgba(0,0,255,0.75); }
            50% { text-shadow: 0.025em 0.05em 0 rgba(255,0,0,0.75), 0.05em 0 0 rgba(0,255,0,0.75), 0 -0.05em 0 rgba(0,0,255,0.75); }
            99% { text-shadow: 0.025em 0.05em 0 rgba(255,0,0,0.75), 0.05em 0 0 rgba(0,255,0,0.75), 0 -0.05em 0 rgba(0,0,255,0.75); }
            100% { text-shadow: -0.025em 0 0 rgba(255,0,0,0.75), -0.025em -0.025em 0 rgba(0,255,0,0.75), -0.025em -0.05em 0 rgba(0,0,255,0.75); }
        }
        .glitch-text {
            position: relative;
        }
        .glitch-text:hover {
            animation: glitch 1s linear infinite;
        }

        /* Scroll Reveal */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.5, 0, 0, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Utilidades para móviles */
        .section-min-h {
            min-height: 100vh;
            min-height: 100dvh;
        }
    </style>
</head>
<body class="antialiased selection:bg-red-900 selection:text-white">

    <!-- Backgrounds -->
    <div class="bg-smoke"></div>
    <div class="bg-orb"></div>

    <!-- Navegación Flotante -->
    <nav class="fixed bottom-4 left-1/2 transform -translate-x-1/2 z-50 glass-panel px-4 py-3 rounded-full flex gap-4 w-[90%] max-w-sm justify-between items-center shadow-2xl border border-white/10">
        <a href="#p1" class="text-xs font-bold tracking-widest text-white/50 hover:text-gold transition-colors">01</a>
        <a href="#p2" class="text-xs font-bold tracking-widest text-white/50 hover:text-gold transition-colors">02</a>
        <a href="#p3" class="text-xs font-bold tracking-widest text-white/50 hover:text-gold transition-colors">03</a>
        <a href="#p4" class="text-xs font-bold tracking-widest text-white/50 hover:text-gold transition-colors">04</a>
        <a href="#p5" class="text-xs font-bold tracking-widest text-white/50 hover:text-gold transition-colors">05</a>
    </nav>

    <!-- PÁGINA 1: HERO -->
    <section id="p1" class="section-min-h flex flex-col items-center justify-center px-6 relative pt-10 pb-24">
        <div class="absolute top-10 left-1/2 transform -translate-x-1/2 opacity-30">
            <!-- Representación SVG minimalista de Loto/Infinito (Inspirado en la imagen 1) -->
            <svg width="60" height="60" viewBox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="1" class="text-yellow-500">
                <path d="M50 10 C 20 40, 20 60, 50 80 C 80 60, 80 40, 50 10 Z"/>
                <path d="M50 30 C 35 50, 40 70, 50 80 C 60 70, 65 50, 50 30 Z"/>
                <path d="M30 75 C 10 75, 10 95, 30 95 C 50 95, 50 75, 70 75 C 90 75, 90 95, 70 95" stroke-width="2"/>
            </svg>
        </div>
        
        <div class="text-center mt-8 reveal active z-10 w-full">
            <h2 class="font-syncopate text-xs tracking-[0.3em] text-gray-400 mb-2 uppercase">El Despertar Inicia</h2>
            <h1 class="text-5xl sm:text-7xl font-bold font-cinzel gold-text tracking-widest mb-1 glitch-text">KONECTA</h1>
            
            <div class="w-full h-px bg-gradient-to-r from-transparent via-white/30 to-transparent my-6"></div>
            
            <h2 class="text-4xl sm:text-5xl font-black font-syncopate text-white leading-none tracking-tighter mix-blend-difference" style="text-shadow: 2px 2px 10px rgba(255,255,255,0.2);">
                EL <br><span class="text-transparent bg-clip-text bg-gradient-to-r from-white to-gray-500">EXPERIMENTO</span>
            </h2>
            
            <p class="mt-8 text-sm text-gray-300 font-light max-w-xs mx-auto italic">
                Manual de Experiencias Exclusivas y Optimización Humana Radical.
            </p>

            <div class="mt-12 glass-panel p-4 rounded-xl border border-white/10 inline-block backdrop-blur-md">
                <p class="font-syncopate text-xs text-gray-400 mb-1">FECHA CLASIFICADA</p>
                <p class="text-2xl font-bold tracking-widest text-white drop-shadow-md">02.AGOSTO.2026</p>
                <p class="text-[10px] uppercase tracking-widest text-red-500 font-bold mt-1">Plazas Estrictamente Limitadas</p>
            </div>

            <div class="mt-12 w-full flex justify-center">
                <a href="#p5" class="btn-red-glow font-syncopate text-white font-bold py-5 px-10 rounded-none w-full max-w-sm text-center text-sm">
                    KONÉCTATE AHORA
                </a>
            </div>
        </div>
        
        <!-- Indicador de scroll -->
        <div class="absolute bottom-24 left-1/2 transform -translate-x-1/2 animate-bounce opacity-50">
            <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path></svg>
        </div>
    </section>

    <!-- PÁGINA 2: EL CONCEPTO -->
    <section id="p2" class="section-min-h flex flex-col justify-center px-6 py-20 relative border-t border-white/5">
        <div class="reveal max-w-md mx-auto relative z-10">
            <span class="text-red-600 font-syncopate text-xs tracking-widest mb-4 block">/// EXPEDIENTE 001</span>
            <h2 class="text-3xl font-cinzel font-bold text-white mb-6">¿QUÉ ES <br><span class="gold-text">EL EXPERIMENTO?</span></h2>
            
            <div class="space-y-6 text-gray-300 font-light text-base leading-relaxed">
                <p class="text-xl font-medium text-white border-l-2 border-red-600 pl-4">
                    No somos terapia tradicional. No somos un webinar.
                </p>
                <p>
                    <strong>El Experimento</strong> es un espacio de intervención mental y psicoespiritual de élite diseñado para romper las cadenas invisibles que limitan tu potencial. 
                </p>
                <p class="glass-panel p-5 rounded-lg text-sm italic">
                    Reunimos a las mentes más brillantes de la neurobiología, el chamanismo ancestral y la reestructuración táctica en un evento digital maratónico sin precedentes. Coordinado por Konecta, 6 especialistas supremos y 2 invitados clasificados colisionarán contigo para detonar un estado de bienestar y soberanía absoluta.
                </p>
                <p class="text-sm font-bold text-gray-100 uppercase tracking-wide mt-4">
                    Este es un producto de alta inversión para quienes buscan resultados inmediatos, definitivos y radicales.
                </p>
                
                <h3 class="text-xl font-syncopate font-bold text-white text-center mt-10 pt-4 border-t border-white/10">
                    ¿Estás listo para <br><span class="text-red-500">hackear tu propia realidad?</span>
                </h3>
            </div>
        </div>
    </section>

    <!-- PÁGINA 3: ESPECIALISTAS -->
    <section id="p3" class="min-h-screen py-20 px-4 relative border-t border-white/5">
        <div class="reveal text-center mb-12 max-w-md mx-auto pt-10">
            <h2 class="text-3xl font-cinzel font-bold text-white mb-2">EL LINE-UP DE <span class="gold-text">ÉLITE</span></h2>
            <p class="text-xs font-syncopate text-gray-500 tracking-widest">NUESTROS ARQUITECTOS MENTALES</p>
        </div>

        <div class="grid grid-cols-1 gap-6 max-w-md mx-auto pb-24">
            
            <!-- Especialista 1 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-orange reveal">
                <div class="aura-content">
                    <h3 class="text-2xl font-cinzel font-bold text-white mb-1">PRISCILA</h3>
                    <p class="text-[10px] font-syncopate text-[#ff8c00] tracking-widest mb-3">CLARIFICACIÓN EXISTENCIAL Y BLINDAJE MENTAL</p>
                    <p class="text-sm text-gray-300 font-light italic mb-3">"¿Vives bajo las reglas de otros o bajo tu propio diseño?"</p>
                    <p class="text-xs text-gray-400">Desmantela el caos mental y la incertidumbre. Un enfoque de alta gama que purifica tus procesos de vida. Olvídate de las dudas: es hora de un blindaje mental definitivo.</p>
                </div>
            </div>

            <!-- Especialista 2 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-white reveal">
                <div class="aura-content">
                    <h3 class="text-2xl font-cinzel font-bold text-white mb-1">EL WAAZA</h3>
                    <p class="text-[10px] font-syncopate text-white tracking-widest mb-3">INTERVENCIÓN ESTRATÉGICA E INTROSPECCIÓN COLECTIVA</p>
                    <p class="text-sm text-gray-300 font-light italic mb-3">"El arte de leer tu mente antes de que hables."</p>
                    <p class="text-xs text-gray-400">El articulador táctico capaz de descifrar dinámicas ocultas. Herramientas de choque que activan un cambio inmediato sin que apenas sientas la intervención. El espejo definitivo.</p>
                </div>
            </div>

            <!-- Especialista 3 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-pink reveal">
                <div class="aura-content">
                    <h3 class="text-2xl font-cinzel font-bold text-white mb-1">LINDA</h3>
                    <p class="text-[10px] font-syncopate text-[#ff1493] tracking-widest mb-3">REESTRUCTURACIÓN PSICOESPIRITUAL</p>
                    <p class="text-sm text-gray-300 font-light italic mb-3">"Desmantela tus heridas de la infancia y recupera tu soberanía."</p>
                    <p class="text-xs text-gray-400">Metodología de choque que destruye patrones limitantes mediante visualizaciones creativas de alta intensidad. Un proceso premium para mentes exigentes.</p>
                </div>
            </div>

            <!-- Especialista 4 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-gray reveal">
                <div class="aura-content">
                    <h3 class="text-2xl font-cinzel font-bold text-white mb-1">NOÉ</h3>
                    <p class="text-[10px] font-syncopate text-[#a9a9a9] tracking-widest mb-3">SABIDURÍA ANCESTRAL Y CHAMANISMO DE ÉLITE</p>
                    <p class="text-sm text-gray-300 font-light italic mb-3">"La 'Otra Ciencia' que la explicación convencional oculta."</p>
                    <p class="text-xs text-gray-400">El puente hacia el misticismo cuántico. Interviene directamente en tu energía mediante técnicas ancestrales tras un riguroso diagnóstico. Excluye el prejuicio; esto es poder puro.</p>
                </div>
            </div>

            <!-- Especialista 5 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-red reveal">
                <div class="aura-content">
                    <h3 class="text-2xl font-cinzel font-bold text-white mb-1">LEVI</h3>
                    <p class="text-[10px] font-syncopate text-[#ff0000] tracking-widest mb-3">SANACIÓN INTEGRAL Y RECONEXIÓN CUÁNTICA</p>
                    <p class="text-sm text-gray-300 font-light italic mb-3">"El retorno a tu esencia indomable."</p>
                    <p class="text-xs text-gray-400">Respaldado por más de 7,000 intervenciones. Rompe reglas tradicionales para adaptarse orgánicamente a tu historia, devolviéndote magnetismo personal inmediato.</p>
                </div>
            </div>

            <!-- Especialista 6 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-green reveal">
                <div class="aura-content">
                    <h3 class="text-2xl font-cinzel font-bold text-white mb-1">YANICK</h3>
                    <p class="text-[10px] font-syncopate text-[#00ff00] tracking-widest mb-3">CREADOR DEL MÉTODO O.M.I. Y OPTIMIZACIÓN CONDUCTUAL</p>
                    <p class="text-sm text-gray-300 font-light italic mb-3">"Hackea la química de tu cerebro. Elimina el vacío existencial."</p>
                    <p class="text-xs text-gray-400">Interviene sobre redes de pensamiento y conductas destructivas mediante Hipnosis y EMDR. El reset definitivo para una vida soberana y de alto rendimiento.</p>
                </div>
            </div>

            <!-- Invitado Especial 1 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-yellow border border-[#ffd700]/30 reveal flex items-center justify-center min-h-[120px]">
                <div class="aura-content text-center">
                    <h3 class="text-xl font-syncopate font-bold text-[#ffd700] tracking-widest">INVITADO ESPECIAL</h3>
                    <p class="text-[10px] text-gray-400 mt-2">IDENTIDAD CLASIFICADA</p>
                </div>
            </div>

            <!-- Invitado Especial 2 -->
            <div class="glass-panel p-6 rounded-xl aura-card aura-purple border border-[#8a2be2]/30 reveal flex items-center justify-center min-h-[120px]">
                <div class="aura-content text-center">
                    <h3 class="text-xl font-syncopate font-bold text-[#8a2be2] tracking-widest">INVITADO ESPECIAL</h3>
                    <p class="text-[10px] text-gray-400 mt-2">REVELACIÓN DE ALTO IMPACTO</p>
                </div>
            </div>

        </div>
    </section>

    <!-- PÁGINA 4: AGENDA -->
    <section id="p4" class="section-min-h flex flex-col justify-center px-6 py-20 relative border-t border-white/5">
        <div class="max-w-md mx-auto w-full pb-20">
            <h2 class="text-3xl font-cinzel font-bold text-white mb-10 text-center">EL <span class="gold-text">ITINERARIO</span></h2>
            
            <div class="relative border-l border-white/20 ml-3 space-y-8 pb-8">
                
                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-white rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#fff]"></div>
                    <p class="font-syncopate text-xs text-white mb-1">09:30 HRS</p>
                    <h4 class="font-bold text-lg">Apertura Absoluta</h4>
                    <p class="text-xs text-gray-400">Encuadre del experimento y activación colectiva de alto impacto.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#ff8c00] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#ff8c00]"></div>
                    <p class="font-syncopate text-xs text-[#ff8c00] mb-1">10:00 HRS</p>
                    <h4 class="font-bold text-lg text-white">Priscila</h4>
                    <p class="text-xs text-gray-400">Clarificación existencial de alto nivel.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-white rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#fff]"></div>
                    <p class="font-syncopate text-xs text-white mb-1">11:30 HRS</p>
                    <h4 class="font-bold text-lg text-white">El Waaza</h4>
                    <p class="text-xs text-gray-400">Lectura de necesidades profundas.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#ff1493] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#ff1493]"></div>
                    <p class="font-syncopate text-xs text-[#ff1493] mb-1">13:00 HRS</p>
                    <h4 class="font-bold text-lg text-white">Linda</h4>
                    <p class="text-xs text-gray-400">Reestructuración psicoespiritual.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#a9a9a9] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#a9a9a9]"></div>
                    <p class="font-syncopate text-xs text-[#a9a9a9] mb-1">14:30 HRS</p>
                    <h4 class="font-bold text-lg text-white">Noé</h4>
                    <p class="text-xs text-gray-400">La intervención cuántica y espiritual.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#ff0000] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#ff0000]"></div>
                    <p class="font-syncopate text-xs text-[#ff0000] mb-1">16:00 HRS</p>
                    <h4 class="font-bold text-lg text-white">Levi</h4>
                    <p class="text-xs text-gray-400">Sanación emocional de alto volumen.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#00ff00] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#00ff00]"></div>
                    <p class="font-syncopate text-xs text-[#00ff00] mb-1">17:30 HRS</p>
                    <h4 class="font-bold text-lg text-white">Yanick</h4>
                    <p class="text-xs text-gray-400">Neuroregulación de élite.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#8a2be2] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#8a2be2] animate-pulse"></div>
                    <p class="font-syncopate text-xs text-[#8a2be2] mb-1">HORARIO SECRETO</p>
                    <h4 class="font-bold text-lg text-white">Invitado Especial</h4>
                    <p class="text-xs text-gray-400">Revelación de alto impacto.</p>
                </div>

                <div class="reveal relative pl-6">
                    <div class="absolute w-3 h-3 bg-[#ffd700] rounded-full -left-[6.5px] top-1 shadow-[0_0_10px_#ffd700] animate-pulse"></div>
                    <p class="font-syncopate text-xs text-[#ffd700] mb-1">HORARIO SECRETO</p>
                    <h4 class="font-bold text-lg text-white">Invitado Especial</h4>
                    <p class="text-xs text-gray-400">Cierre magistral del experimento.</p>
                </div>
            </div>
            
            <div class="glass-panel p-4 mt-8 border-l-4 border-red-600 rounded-r text-sm text-gray-300">
                <span class="text-red-500 font-bold">⚠️ AVISO DE ADMISIÓN:</span> Abstenerse mentes cerradas, escépticas o que busquen entretenimiento pasivo. Aquí venimos a transformarnos radicalmente.
            </div>
        </div>
    </section>

    <!-- PÁGINA 5: CHECKOUT Y LEGAL -->
    <section id="p5" class="section-min-h flex flex-col justify-center px-6 py-20 relative border-t border-white/5 bg-gradient-to-t from-black to-transparent">
        <div class="max-w-md mx-auto w-full pb-20 reveal">
            
            <div class="text-center mb-8">
                <h2 class="text-3xl font-cinzel font-bold text-white mb-2">ASEGURA TU <span class="text-red-600">ACCESO</span></h2>
                <p class="text-gray-400 text-sm">FASE 1: PRECIO DE FUNDADORES</p>
            </div>

            <div class="glass-panel border border-white/20 p-8 text-center rounded-xl relative overflow-hidden mb-8">
                <div class="absolute top-0 right-0 bg-red-600 text-[10px] font-bold px-3 py-1 font-syncopate tracking-widest text-white">CUPOS LIMITADOS</div>
                <h3 class="text-5xl font-light text-white mb-2 font-cinzel">$150 <span class="text-lg text-gray-400">USD</span></h3>
                <p class="text-xs text-gray-400 italic mb-6">Culmina: Fecha por programar</p>
                <button class="btn-red-glow font-syncopate text-white font-bold py-4 px-8 w-full text-sm">ADQUIRIR PASE DE ÉLITE</button>
            </div>

            <!-- Formulario de dudas -->
            <form class="space-y-4 mb-12">
                <h4 class="font-syncopate text-xs text-gray-400 tracking-widest border-b border-white/10 pb-2 mb-4">¿TIENES DUDAS? APLICA AQUÍ</h4>
                <div>
                    <input type="text" placeholder="NOMBRE COMPLETO" class="w-full bg-black/50 border border-white/20 rounded p-4 text-sm text-white focus:outline-none focus:border-gold transition-colors placeholder-gray-600">
                </div>
                <div>
                    <input type="email" placeholder="CORREO ELECTRÓNICO" class="w-full bg-black/50 border border-white/20 rounded p-4 text-sm text-white focus:outline-none focus:border-gold transition-colors placeholder-gray-600">
                </div>
                <div>
                    <textarea placeholder="COMENTARIO O MOTIVO DE ACCESO" rows="3" class="w-full bg-black/50 border border-white/20 rounded p-4 text-sm text-white focus:outline-none focus:border-gold transition-colors placeholder-gray-600 resize-none"></textarea>
                </div>
                <button type="button" class="w-full bg-white text-black font-syncopate font-bold text-xs py-4 hover:bg-gray-200 transition-colors">ENVIAR SOLICITUD</button>
            </form>

            <!-- Nota Legal (Priscila) -->
            <div class="border-t border-white/10 pt-8 text-[10px] text-gray-500 leading-relaxed text-justify opacity-60 hover:opacity-100 transition-opacity">
                <p class="mb-2"><strong>Cláusula informativa:</strong> Esto no es terapia psicológica, este es un espacio de reflexión personal. Esto no constituye atención médica, psicológica, psiquiátrica, ni asesoría legal y no sustituye bajo ninguna circunstancia servicios profesionales de salud. Aquí no se realizan diagnósticos, ni tratamientos de salud física o mental.</p>
                <p class="mb-2">Al participar, la persona reconoce que el servicio es voluntario y que las decisiones que tome son de su exclusiva responsabilidad y con fines de entretenimiento.</p>
                <p>De igual forma no se aceptan devoluciones.<br><br>Atte.<br>Priscilla Carvajal | Equipo Konecta</p>
            </div>
            
        </div>
    </section>

    <!-- Lógica de interacciones -->
    <script>
        // Animación de aparición al hacer scroll (Scroll Reveal)
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");
            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 100;
                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("active");
                }
            }
        }
        window.addEventListener("scroll", reveal);
        reveal(); // Trigger on load

        // Resaltado dinámico del menú de navegación
        const sections = document.querySelectorAll("section");
        const navLinks = document.querySelectorAll("nav a");

        window.addEventListener("scroll", () => {
            let current = "";
            sections.forEach((section) => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (pageYOffset >= sectionTop - sectionHeight / 3) {
                    current = section.getAttribute("id");
                }
            });

            navLinks.forEach((a) => {
                a.classList.remove("text-gold", "font-black");
                a.classList.add("text-white/50");
                if (a.getAttribute("href").includes(current)) {
                    a.classList.remove("text-white/50");
                    a.classList.add("text-gold", "font-black");
                }
            });
        });
    </script>
</body>
</html>

```
