<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ecopontos Perto de Mim | Guia Oficial de Descarte Sustentável</title>
    <meta name="description" content="Encontre ecopontos e pontos de entrega voluntária (PEV) próximos a você. Guia de descarte de entulho, móveis e reciclagem com assistente de IA.">
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --primary: #059669;
            --primary-hover: #047857;
            --secondary: #0f172a;
            --accent: #fbbf24;
            --bg: #f8fafc;
            --text: #334155;
            --text-light: #64748b;
            --white: #ffffff;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }
        body { 
            font-family: 'Inter', sans-serif; 
            background-color: var(--bg); 
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container { max-width: 1200px; margin: 0 auto; padding: 0 1.5rem; }

        /* HEADER & NAV */
        header { width: 100%; }
        .navbar {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(12px);
            height: 80px;
            width: 100%;
            position: fixed;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid #e2e8f0;
            display: flex;
            align-items: center;
        }

        .nav-flex {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
        }

        .logo {
            font-weight: 800;
            font-size: 1.5rem;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .nav-menu {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-menu a {
            text-decoration: none;
            color: var(--secondary);
            font-weight: 600;
            font-size: 0.95rem;
            transition: var(--transition);
        }

        .nav-menu a:hover { color: var(--primary); }

        .mobile-toggle {
            display: none;
            background: none;
            border: none;
            cursor: pointer;
            padding: 10px;
        }

        .hamburger-line {
            display: block;
            width: 25px;
            height: 3px;
            background: var(--secondary);
            margin: 5px 0;
        }

        /* Mobile Drawer */
        .mobile-nav {
            position: fixed;
            top: 80px;
            left: 0;
            width: 100%;
            background: var(--white);
            padding: 1.5rem;
            box-shadow: var(--shadow);
            transform: translateY(-150%);
            transition: var(--transition);
            z-index: 999;
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .mobile-nav.open { transform: translateY(0); }
        .mobile-nav a {
            font-size: 1.1rem;
            font-weight: 600;
            text-decoration: none;
            color: var(--secondary);
            padding: 1.25rem;
            border-bottom: 1px solid #f1f5f9;
        }

        /* HERO SECTION */
        .hero {
            padding: 180px 0 100px;
            background: radial-gradient(circle at top right, #ecfdf5, #f8fafc);
            text-align: center;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 6vw, 4rem);
            font-weight: 900;
            color: var(--secondary);
            letter-spacing: -2px;
            line-height: 1.1;
            margin-bottom: 1.5rem;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--text-light);
            max-width: 700px;
            margin: 0 auto 3rem;
        }

        .search-container {
            background: var(--white);
            padding: 0.75rem;
            border-radius: 60px;
            display: flex;
            max-width: 650px;
            margin: 0 auto;
            box-shadow: var(--shadow-lg);
            border: 1px solid #e2e8f0;
        }

        .search-container input {
            flex: 1;
            border: none;
            padding: 0 2rem;
            font-size: 1.1rem;
            outline: none;
            border-radius: 60px;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
            border: none;
            padding: 1rem 2.5rem;
            border-radius: 60px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            white-space: nowrap;
        }

        .btn-primary:hover {
            background: var(--primary-hover);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(5, 150, 105, 0.3);
        }

        /* SECTION STYLES */
        .section { padding: 100px 0; }
        .section-header { text-align: center; margin-bottom: 5rem; }
        .section-header h2 { font-size: 2.5rem; font-weight: 800; color: var(--secondary); margin-bottom: 1rem; }
        .section-header p { color: var(--text-light); font-size: 1.1rem; }
        
        /* GRID CARDS */
        .grid-materials {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
        }

        .card {
            background: var(--white);
            padding: 3rem 2rem;
            border-radius: 32px;
            border: 1px solid #f1f5f9;
            transition: var(--transition);
            text-align: left;
        }

        .card:hover {
            transform: translateY(-12px);
            box-shadow: var(--shadow-lg);
            border-color: var(--primary);
        }

        .icon-box {
            width: 64px;
            height: 64px;
            background: #ecfdf5;
            border-radius: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            margin-bottom: 2rem;
        }

        .card h3 { margin-bottom: 1rem; color: var(--secondary); }
        .card p { color: var(--text-light); font-size: 0.95rem; }

        /* AI FEATURE SECTION */
        .ai-feature {
            background: var(--secondary);
            border-radius: 40px;
            padding: 6rem 2rem;
            color: var(--white);
            text-align: center;
            margin: 40px 0;
            position: relative;
            overflow: hidden;
        }

        .ai-feature::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -10%;
            width: 300px;
            height: 300px;
            background: var(--primary);
            filter: blur(120px);
            opacity: 0.15;
        }

        .ai-content { position: relative; z-index: 10; max-width: 800px; margin: 0 auto; }

        .ai-input-wrap {
            background: rgba(255,255,255,0.08);
            border: 1px solid rgba(255,255,255,0.15);
            border-radius: 24px;
            padding: 0.75rem;
            display: flex;
            gap: 1rem;
            margin-top: 3rem;
            transition: var(--transition);
        }

        .ai-input-wrap:focus-within {
            background: rgba(255,255,255,0.12);
            border-color: var(--primary);
        }

        .ai-input-wrap input {
            background: transparent;
            border: none;
            flex: 1;
            padding: 0.5rem 1rem;
            color: white;
            font-size: 1.1rem;
            outline: none;
        }

        .ai-input-wrap input::placeholder { color: rgba(255,255,255,0.4); }

        .ai-response-box {
            margin-top: 2.5rem;
            background: rgba(255,255,255,0.04);
            padding: 2rem;
            border-radius: 24px;
            border-left: 5px solid var(--primary);
            text-align: left;
            min-height: 120px;
            font-size: 1.05rem;
            color: #e2e8f0;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* FAQ ACCORDION-STYLE */
        .faq-list { max-width: 850px; margin: 0 auto; }
        .faq-item {
            background: var(--white);
            padding: 2rem;
            border-radius: 24px;
            border: 1px solid #e2e8f0;
            margin-bottom: 1.5rem;
            transition: var(--transition);
        }
        .faq-item:hover { border-color: var(--primary); }
        .faq-item h4 { color: var(--secondary); margin-bottom: 1rem; font-size: 1.2rem; }
        .faq-item p { color: var(--text-light); }

        /* FOOTER */
        footer {
            background: #020617;
            color: #94a3b8;
            padding: 100px 0 50px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 4rem;
            margin-bottom: 5rem;
        }

        .footer-logo {
            font-weight: 800;
            font-size: 1.5rem;
            color: var(--white);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 1.5rem;
        }

        .footer-title { color: var(--white); font-weight: 700; margin-bottom: 1.5rem; font-size: 1.1rem; }
        .footer-links { list-style: none; }
        .footer-links li { margin-bottom: 1rem; }
        .footer-links a { color: inherit; text-decoration: none; transition: 0.2s; }
        .footer-links a:hover { color: var(--primary); }

        .copyright {
            border-top: 1px solid #1e293b;
            padding-top: 40px;
            text-align: center;
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            .nav-menu { display: none; }
            .mobile-toggle { display: block; }
            .hero { padding: 140px 0 80px; }
            .hero h1 { font-size: 2.5rem; }
            .search-container { flex-direction: column; border-radius: 30px; padding: 1rem; }
            .btn-primary { width: 100%; border-radius: 20px; }
            .ai-input-wrap { flex-direction: column; border-radius: 20px; padding: 1rem; }
            .section { padding: 60px 0; }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav class="navbar">
        <div class="container nav-flex">
            <a href="#" class="logo">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M11 20A7 7 0 0 1 11 6a7 7 0 0 1 11 11v3h-3a7 7 0 0 1-7-7Z"/><path d="M11 6a7 7 0 0 0-7 7v3h3a7 7 0 0 0 7-7Z"/></svg>
                <span>EcoPortal</span>
            </a>
            <ul class="nav-menu">
                <li><a href="#buscar">Buscar</a></li>
                <li><a href="#materiais">Materiais</a></li>
                <li><a href="#ia">Consultar IA</a></li>
                <li><a href="#faq">FAQ</a></li>
            </ul>
            <button class="mobile-toggle" id="menuToggle">
                <span class="hamburger-line"></span>
                <span class="hamburger-line"></span>
                <span class="hamburger-line"></span>
            </button>
        </div>
    </nav>

    <!-- MOBILE DRAWER -->
    <div class="mobile-nav" id="mobileNav">
        <a href="#buscar">Buscar Ecoponto</a>
        <a href="#materiais">Materiais Aceitos</a>
        <a href="#ia">Consultar IA</a>
        <a href="#faq">Dúvidas Frequentes</a>
    </div>

    <!-- MAIN CONTENT -->
    <main>
        <!-- HERO -->
        <section class="hero">
            <div class="container">
                <h1>Ecopontos perto de mim</h1>
                <p>Encontre o local de descarte mais próximo e descubra como tratar seu resíduo de forma inteligente e sustentável.</p>
                <div class="search-container" id="buscar">
                    <input type="text" id="searchInput" placeholder="Digite seu bairro, cidade ou CEP...">
                    <button class="btn-primary" id="searchBtn">Encontrar Ecoponto</button>
                </div>
            </div>
        </section>

        <!-- MATERIALS SECTION -->
        <section class="section container" id="materiais">
            <div class="section-header">
                <h2>O que levar ao Ecoponto?</h2>
                <p>Conheça os principais materiais aceitos para descarte gratuito.</p>
            </div>
            <div class="grid-materials">
                <article class="card">
                    <div class="icon-box">🧱</div>
                    <h3>Entulho de Obras</h3>
                    <p>Até 1m³ diários de resíduos de construção civil como tijolos, azulejos e concreto de pequenas reformas.</p>
                </article>
                <article class="card">
                    <div class="icon-box">🛋️</div>
                    <h3>Móveis & Madeiras</h3>
                    <p>Sofás, armários velhos desmontados, mesas, cadeiras e restos de madeira em geral.</p>
                </article>
                <article class="card">
                    <div class="icon-box">🌿</div>
                    <h3>Podas & Jardim</h3>
                    <p>Restos de jardinagem, galhos secos e grama cortada de terrenos e jardins residenciais.</p>
                </article>
                <article class="card">
                    <div class="icon-box">♻️</div>
                    <h3>Recicláveis</h3>
                    <p>Papel, papelão, garrafas plásticas e metais encaminhados para centros de triagem e cooperativas.</p>
                </article>
            </div>
        </section>

        <!-- AI ASSISTANT -->
        <section class="container" id="ia">
            <div class="ai-feature">
                <div class="ai-content">
                    <h2>Dúvida sobre um material?</h2>
                    <p>Nosso guia inteligente informa instantaneamente se seu item pode ser levado ou onde descartá-lo.</p>
                    <div class="ai-input-wrap">
                        <input type="text" id="aiInput" placeholder="Ex: Lata de tinta, monitor, óleo de cozinha...">
                        <button class="btn-primary" id="aiBtn">Consultar Guia</button>
                    </div>
                    <div class="ai-response-box" id="aiResponse">
                        Aguardando sua consulta... Digite um material acima para obter orientação imediata.
                    </div>
                </div>
            </div>
        </section>

        <!-- FAQ SECTION -->
        <section class="section container" id="faq">
            <div class="section-header">
                <h2>Perguntas Frequentes</h2>
                <p>Tudo o que você precisa saber antes de ir ao posto de entrega.</p>
            </div>
            <div class="faq-list">
                <div class="faq-item">
                    <h4>Qual o horário de funcionamento padrão?</h4>
                    <p>A maioria dos ecopontos funciona de Segunda a Sábado, das 08:00 às 17:00. Alguns postos em capitais também abrem aos Domingos em horários reduzidos.</p>
                </div>
                <div class="faq-item">
                    <h4>Existe algum custo para descartar?</h4>
                    <p>Não. O serviço de ecoponto municipal é totalmente gratuito para o cidadão comum, visando evitar o descarte irregular em vias públicas.</p>
                </div>
                <div class="faq-item">
                    <h4>Posso levar lixo doméstico (orgânico)?</h4>
                    <p>Não. Lixo de cozinha e restos de alimentos devem ser destinados exclusivamente à coleta domiciliar convencional da sua prefeitura.</p>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div>
                    <a href="#" class="footer-logo">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M11 20A7 7 0 0 1 11 6a7 7 0 0 1 11 11v3h-3a7 7 0 0 1-7-7Z"/><path d="M11 6a7 7 0 0 0-7 7v3h3a7 7 0 0 0 7-7Z"/></svg>
                        EcoPortal
                    </a>
                    <p>Promovendo a sustentabilidade urbana através da informação clara e tecnologia acessível para todos.</p>
                </div>
                <div>
                    <div class="footer-title">Principais Capitais</div>
                    <ul class="footer-links">
                        <li><a href="#">Ecopontos São Paulo</a></li>
                        <li><a href="#">Ecopontos Rio de Janeiro</a></li>
                        <li><a href="#">Ecopontos Belo Horizonte</a></li>
                        <li><a href="#">Ecopontos Curitiba</a></li>
                    </ul>
                </div>
                <div>
                    <div class="footer-title">Institucional</div>
                    <ul class="footer-links">
                        <li><a href="#">Sobre o Projeto</a></li>
                        <li><a href="#">Política de Privacidade</a></li>
                        <li><a href="#">Termos de Uso</a></li>
                        <li><a href="#">Contato</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 EcoPortal Brasil - Guia Independente de Gestão de Resíduos.</p>
            </div>
        </div>
    </footer>

    <!-- LOGIC SCRIPTS -->
    <script type="importmap">
    {
      "imports": {
        "@google/genai": "https://esm.sh/@google/genai@^1.37.0"
      }
    }
    </script>
    <script type="module">
        import { GoogleGenAI } from "@google/genai";

        // DOM Elements
        const menuToggle = document.getElementById('menuToggle');
        const mobileNav = document.getElementById('mobileNav');
        const aiBtn = document.getElementById('aiBtn');
        const aiInput = document.getElementById('aiInput');
        const aiResponse = document.getElementById('aiResponse');
        const searchBtn = document.getElementById('searchBtn');
        const searchInput = document.getElementById('searchInput');

        // Mobile Menu Toggle
        menuToggle.addEventListener('click', () => {
            mobileNav.classList.toggle('open');
        });

        // Close mobile nav on link click
        mobileNav.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', () => {
                mobileNav.classList.remove('open');
            });
        });

        // Search redirection (simulated)
        searchBtn.addEventListener('click', () => {
            const val = searchInput.value.trim();
            if(val) {
                alert(`Buscando ecopontos em: ${val}. \nEm uma aplicação real, você seria redirecionado para o mapa com os resultados.`);
            }
        });

        // Gemini AI Assistant Integration
        async function handleAIQuery() {
            const query = aiInput.value.trim();
            if (!query) return;

            aiBtn.disabled = true;
            aiBtn.innerText = "Analisando...";
            aiResponse.style.opacity = "0.6";
            aiResponse.innerText = "Consultando legislações ambientais...";

            try {
                // Configuração da API usando a chave injetada pelo ambiente
                const ai = new GoogleGenAI({ apiKey: process.env.API_KEY });
                
                const response = await ai.models.generateContent({
                    model: 'gemini-3-flash-preview',
                    contents: `Atue como um especialista em descarte de resíduos e gestão ambiental no Brasil. O item ou material "${query}" pode ser levado a um Ecoponto municipal comum? 
                    Regras da resposta:
                    1. Inicie com "SIM", "NÃO" ou "DEPENDE" em negrito.
                    2. Explique brevemente o porquê.
                    3. Se não puder ser levado ao ecoponto, indique qual o local correto de descarte (ex: farmácias, logística reversa, coleta comum).
                    4. Responda em no máximo 3 frases curtas.`
                });

                aiResponse.style.opacity = "1";
                aiResponse.innerHTML = response.text || "Não conseguimos processar sua dúvida agora. Tente descrever o material de outra forma.";
            } catch (error) {
                console.error("Erro na consulta IA:", error);
                aiResponse.style.opacity = "1";
                aiResponse.innerText = "Desculpe, houve um erro ao conectar com o assistente inteligente. Por favor, tente novamente em alguns instantes.";
            } finally {
                aiBtn.disabled = false;
                aiBtn.innerText = "Consultar Guia";
            }
        }

        aiBtn.addEventListener('click', handleAIQuery);
        aiInput.addEventListener('keydown', (e) => {
            if (e.key === 'Enter') handleAIQuery();
        });
    </script>
</body>
</html>
