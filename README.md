<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hugo Norberto - Desarrollador Full-Stack</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .profile-header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
        }
        
        .profile-header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(102, 126, 234, 0.1), transparent);
            animation: rotate 20s linear infinite;
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .profile-content {
            position: relative;
            z-index: 1;
        }
        
        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 48px;
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }
        
        .name {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .title {
            font-size: 1.3rem;
            color: #666;
            margin-bottom: 20px;
            font-weight: 500;
        }
        
        .description {
            font-size: 1.1rem;
            color: #555;
            max-width: 800px;
            margin: 0 auto 30px;
            line-height: 1.8;
        }
        
        .contact-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: #666;
            text-decoration: none;
            padding: 10px 20px;
            border-radius: 50px;
            background: rgba(102, 126, 234, 0.1);
            transition: all 0.3s ease;
        }
        
        .contact-item:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateY(-2px);
        }
        
        .section {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        .section-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 30px;
            color: #333;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .section-title::before {
            content: '';
            width: 4px;
            height: 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 2px;
        }
        
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .tech-category {
            background: rgba(102, 126, 234, 0.05);
            padding: 20px;
            border-radius: 15px;
            border-left: 4px solid #667eea;
        }
        
        .tech-category h4 {
            font-size: 1.1rem;
            margin-bottom: 15px;
            color: #333;
            font-weight: 600;
        }
        
        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .tech-tag {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
        }
        
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            padding: 25px;
            border: 1px solid rgba(102, 126, 234, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(135deg, #667eea, #764ba2);
        }
        
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.2);
        }
        
        .project-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: #333;
        }
        
        .project-description {
            color: #666;
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        .project-tech {
            font-size: 0.9rem;
            color: #667eea;
            font-weight: 500;
            margin-bottom: 10px;
        }
        
        .project-role {
            font-size: 0.9rem;
            color: #888;
            font-style: italic;
        }
        
        .cert-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .cert-item {
            background: rgba(102, 126, 234, 0.05);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }
        
        .cert-name {
            font-weight: 600;
            color: #333;
            margin-bottom: 5px;
        }
        
        .cert-org {
            color: #666;
            font-size: 0.9rem;
        }
        
        .learning-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
        }
        
        .learning-item {
            background: rgba(118, 75, 162, 0.05);
            padding: 15px;
            border-radius: 10px;
            border-left: 4px solid #764ba2;
            color: #333;
        }
        
        .cta-section {
            text-align: center;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 40px;
            border-radius: 20px;
            margin-top: 30px;
        }
        
        .cta-title {
            font-size: 2rem;
            margin-bottom: 15px;
            font-weight: 700;
        }
        
        .cta-text {
            font-size: 1.1rem;
            margin-bottom: 25px;
            opacity: 0.9;
        }
        
        .cta-button {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }
        
        .cta-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
            
            .profile-header {
                padding: 25px;
            }
            
            .name {
                font-size: 2rem;
            }
            
            .contact-info {
                flex-direction: column;
                align-items: center;
            }
            
            .section {
                padding: 25px;
            }
            
            .tech-grid {
                grid-template-columns: 1fr;
            }
            
            .project-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="profile-header">
            <div class="profile-content">
                <div class="profile-img">👨💻</div>
                <h1 class="name">Hugo Norberto</h1>
                <p class="title">🎯 Desarrollador Full-Stack | Especialista en Soluciones Móviles & Web</p>
                <p class="description">
                    Ingeniero en Desarrollo y Gestión de Software especializado en crear aplicaciones robustas y escalables. 
                    Con experiencia sólida en desarrollo móvil nativo (Android/Kotlin) y desarrollo web moderno (Laravel/PHP), 
                    me enfoco en entregar soluciones tecnológicas que generen impacto real para usuarios y empresas.
                </p>
                <div class="contact-info">
                    <a href="#" class="contact-item">📍 Ocosingo, Chiapas</a>
                    <a href="mailto:hugonorberton@gmail.com" class="contact-item">📧 hugonorberton@gmail.com</a>
                    <a href="tel:+529191524467" class="contact-item">📱 (+52) 919 152 44 67</a>
                    <a href="https://linkedin.com/in/hugo-norberto-navarro-navarro-177801237" class="contact-item">🔗 LinkedIn</a>
                </div>
            </div>
        </div>

        <div class="section">
            <h2 class="section-title">🛠️ Stack Tecnológico</h2>
            <div class="tech-grid">
                <div class="tech-category">
                    <h4>Backend & APIs</h4>
                    <div class="tech-tags">
                        <span class="tech-tag">PHP</span>
                        <span class="tech-tag">Laravel</span>
                        <span class="tech-tag">Kotlin</span>
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">PL/SQL</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h4>Frontend & Móvil</h4>
                    <div class="tech-tags">
                        <span class="tech-tag">Jetpack Compose</span>
                        <span class="tech-tag">Flutter</span>
                        <span class="tech-tag">JavaScript</span>
                        <span class="tech-tag">HTML/CSS</span>
                        <span class="tech-tag">Tailwind CSS</span>
                        <span class="tech-tag">Livewire</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h4>Bases de Datos</h4>
                    <div class="tech-tags">
                        <span class="tech-tag">MySQL</span>
                        <span class="tech-tag">Firebase</span>
                        <span class="tech-tag">MongoDB</span>
                        <span class="tech-tag">Oracle</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h4>Herramientas & DevOps</h4>
                    <div class="tech-tags">
                        <span class="tech-tag">Git & GitHub</span>
                        <span class="tech-tag">Android Studio</span>
                        <span class="tech-tag">Figma</span>
                        <span class="tech-tag">Postman</span>
                        <span class="tech-tag">Scrum</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2 class="section-title">🧩 Proyectos Destacados</h2>
            <div class="project-grid">
                <div class="project-card">
                    <h3 class="project-title">📱 LigaSmartApp</h3>
                    <p class="project-description">
                        Aplicación móvil completa para gestión de torneos de fútbol, incluyendo administración de equipos, 
                        programación de partidos y seguimiento de estadísticas en tiempo real.
                    </p>
                    <p class="project-tech">Tecnologías: Kotlin + Firebase + Jetpack Compose</p>
                    <p class="project-role">Rol: Diseño UI/UX, desarrollo completo backend y frontend</p>
                </div>
                
                <div class="project-card">
                    <h3 class="project-title">💼 WebLabor – Sistema de Gestión Empresarial</h3>
                    <p class="project-description">
                        Plataforma web robusta para gestión de proyectos internos, control de tareas, 
                        seguimiento de tiempos y reportes avanzados para empresa de software.
                    </p>
                    <p class="project-tech">Tecnologías: Laravel + MySQL + Tailwind CSS</p>
                    <p class="project-role">Rol: Arquitectura de BD, desarrollo backend/frontend, módulo de reportes</p>
                </div>
                
                <div class="project-card">
                    <h3 class="project-title">🧾 Sistema de Gestión de Afiliados – CANACO</h3>
                    <p class="project-description">
                        Sistema web integral para la gestión de afiliados de la Cámara de Comercio, 
                        incluyendo registro, renovaciones, reportes y panel administrativo.
                    </p>
                    <p class="project-tech">Tecnologías: Laravel + MySQL + Livewire</p>
                    <p class="project-role">Rol: Desarrollo completo full-stack, diseño de BD y arquitectura</p>
                </div>
            </div>
        </div>

        <div class="section">
            <h2 class="section-title">📜 Certificaciones</h2>
            <div class="cert-list">
                <div class="cert-item">
                    <div class="cert-name">Desarrollador de Interfaces Gráficas</div>
                    <div class="cert-org">Fundación Carlos Slim</div>
                </div>
                <div class="cert-item">
                    <div class="cert-name">Programador de Microcontroladores</div>
                    <div class="cert-org">Fundación Carlos Slim</div>
                </div>
                <div class="cert-item">
                    <div class="cert-name">Técnico en Comunicaciones Inalámbricas</div>
                    <div class="cert-org">Fundación Carlos Slim</div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2 class="section-title">🌱 Actualmente Aprendiendo</h2>
            <div class="learning-list">
                <div class="learning-item">
                    🏗️ Arquitectura de software moderna y patrones de diseño
                </div>
                <div class="learning-item">
                    📱 Desarrollo multiplataforma avanzado con Flutter
                </div>
                <div class="learning-item">
                    🧪 Pruebas automatizadas y buenas prácticas DevOps
                </div>
                <div class="learning-item">
                    ☁️ Cloud Computing y servicios en la nube
                </div>
            </div>
        </div>

        <div class="cta-section">
            <h2 class="cta-title">🤝 ¡Colaboremos Juntos!</h2>
            <p class="cta-text">
                Estoy disponible para proyectos freelance, colaboraciones técnicas y oportunidades laborales. 
                Si tienes una idea innovadora o necesitas desarrollar una solución tecnológica, ¡conversemos!
            </p>
            <a href="mailto:hugonorberton@gmail.com" class="cta-button">📧 Contáctame</a>
        </div>
    </div>
</body>
</html>
