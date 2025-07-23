<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3ra Semana de la Mecatrónica - UNAJ</title>
    <style>
        /* Variables de colores */
        :root {
            --vino: #8a0000;
            --vino-oscuro: #5a0000;
            --negro: #121212;
            --gris-oscuro: #222;
            --gris: #f5f5f5;
            --blanco: #ffffff;
        }

        /* Estilos generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            background-color: var(--gris);
            color: var(--negro);
            background-image: linear-gradient(to bottom, rgba(138, 0, 0, 0.05), transparent 200px);
        }

        /* Encabezado */
        header {
            background: linear-gradient(135deg, var(--vino), var(--negro));
            color: var(--blanco);
            padding: 3rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
        }

        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at top right, var(--vino-oscuro), transparent 70%);
            opacity: 0.8;
            z-index: 0;
        }

        .header-content {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            font-weight: 700;
        }

        .subtitle {
            font-size: 1.5rem;
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: rgba(255, 255, 255, 0.9);
        }

        .date {
            background-color: var(--vino-oscuro);
            display: inline-block;
            padding: 0.7rem 2rem;
            border-radius: 30px;
            font-weight: bold;
            font-size: 1.2rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            margin-top: 1rem;
        }

        /* Barra de navegación */
        nav {
            background-color: var(--negro);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 15px rgba(0,0,0,0.4);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
        }

        nav li {
            margin: 0 0.5rem;
        }

        nav a {
            color: var(--blanco);
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            padding: 1rem 1.5rem;
            display: block;
            transition: all 0.3s ease;
            position: relative;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        nav a::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 0;
            height: 3px;
            background-color: var(--vino);
            transition: all 0.3s ease;
            transform: translateX(-50%);
        }

        nav a:hover {
            color: var(--vino);
        }

        nav a:hover::after {
            width: 100%;
        }

        /* Contenido principal */
        .container {
            max-width: 1200px;
            margin: 3rem auto;
            padding: 0 2rem;
        }

        .section {
            background-color: var(--blanco);
            border-radius: 10px;
            padding: 2.5rem;
            margin-bottom: 3rem;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            border-left: 5px solid var(--vino);
            position: relative;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        .section::before {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 100px;
            height: 100px;
            background: linear-gradient(45deg, var(--vino), transparent);
            border-radius: 0 0 0 100px;
            z-index: 0;
            opacity: 0.1;
        }

        .section-title {
            color: var(--vino);
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 1;
            padding-bottom: 0.8rem;
            border-bottom: 2px solid var(--gris);
            font-weight: 700;
        }

        .highlight {
            background: linear-gradient(to right, var(--negro), var(--vino));
            color: var(--blanco);
            padding: 1.8rem;
            border-radius: 8px;
            margin: 2rem 0;
            box-shadow: 0 5px 15px rgba(0,0,0,0.15);
            position: relative;
            z-index: 1;
            border-left: 4px solid var(--vino-oscuro);
        }

        .event-list {
            list-style-type: none;
            padding: 0;
            margin: 1.5rem 0;
        }

        .event-list li {
            background-color: rgba(138, 0, 0, 0.05);
            margin-bottom: 0.8rem;
            padding: 1.2rem;
            border-left: 4px solid var(--vino);
            border-radius: 4px;
            transition: transform 0.3s, background-color 0.3s;
            position: relative;
        }

        .event-list li:hover {
            transform: translateX(8px);
            background-color: rgba(138, 0, 0, 0.1);
        }

        .event-time {
            font-weight: bold;
            color: var(--vino);
            display: block;
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        /* Galería */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }

        .gallery-item {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.15);
            height: 250px;
            transition: transform 0.3s, box-shadow 0.3s;
            background-color: var(--gris);
            border: 1px solid rgba(138, 0, 0, 0.1);
        }

        .gallery-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.25);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: linear-gradient(to top, rgba(10, 10, 10, 0.9), transparent);
            color: var(--blanco);
            padding: 1.2rem;
            transform: translateY(100%);
            transition: transform 0.3s;
            text-align: center;
            font-weight: 600;
        }

        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }

        /* Formulario de contacto */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2.5rem;
            margin-top: 2rem;
        }

        .contact-info {
            background: linear-gradient(to bottom right, var(--negro), var(--vino-oscuro));
            color: var(--blanco);
            padding: 2.5rem;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.15);
        }

        .contact-info h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--blanco);
            border-bottom: 2px solid var(--vino);
            padding-bottom: 0.5rem;
            display: inline-block;
        }

        .contact-info p {
            margin-bottom: 1.2rem;
            display: flex;
            align-items: flex-start;
            line-height: 1.8;
        }

        .contact-info i {
            margin-right: 1rem;
            color: var(--vino);
            min-width: 24px;
            font-weight: bold;
        }

        .website-link {
            display: inline-block;
            background-color: var(--vino);
            color: var(--blanco);
            padding: 1rem 2.2rem;
            text-decoration: none;
            border-radius: 4px;
            font-weight: 600;
            margin-top: 1.2rem;
            transition: all 0.3s;
            border: 1px solid var(--vino-oscuro);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .website-link:hover {
            background-color: var(--vino-oscuro);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        /* Pie de página */
        footer {
            background: linear-gradient(135deg, var(--vino), var(--negro));
            color: var(--blanco);
            text-align: center;
            padding: 4rem 0;
            margin-top: 3rem;
            position: relative;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        footer::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at bottom left, var(--vino-oscuro), transparent 70%);
            opacity: 0.7;
            z-index: 0;
        }

        .footer-content {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .footer-logo {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 1.5rem;
            color: var(--blanco);
        }

        .footer-logo span {
            color: var(--vino);
        }

        .footer-links {
            display: flex;
            justify-content: center;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: var(--blanco);
            margin: 0 1.2rem;
            text-decoration: none;
            transition: color 0.3s;
            font-weight: 500;
        }

        .footer-links a:hover {
            color: var(--vino);
        }

        .copyright {
            margin-top: 2rem;
            font-size: 1rem;
            opacity: 0.8;
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 1.5rem 0;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .social-icon:hover {
            background-color: var(--vino);
            transform: translateY(-5px);
        }

        /* Responsive */
        @media (max-width: 900px) {
            .contact-grid {
                grid-template-columns: 1fr;
            }
            
            nav ul {
                flex-wrap: wrap;
            }
            
            nav li {
                margin: 0.3rem;
            }
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
            }
            
            .gallery {
                grid-template-columns: 1fr;
            }
            
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            
            nav li {
                width: 100%;
                text-align: center;
            }

            .section {
                padding: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <!-- Encabezado -->
    <header>
        <div class="header-content">
            <h1>3ra Semana de la Mecatrónica</h1>
            <p class="subtitle">Universidad Nacional de Juliaca - Facultad de Ingeniería Mecatrónica</p>
            <div class="date">9 y 10 de Julio de 2025</div>
        </div>
    </header>
    
    <!-- Barra de navegación -->
    <nav>
        <div class="nav-container">
            <ul>
                <li><a href="#inauguracion">Inauguración</a></li>
                <li><a href="#talleres">Talleres</a></li>
                <li><a href="#proyectos">Proyectos</a></li>
                <li><a href="#galeria">Galería</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </div>
    </nav>
    
    <!-- Contenido principal -->
    <div class="container">
        <!-- Sección de Inauguración -->
        <section id="inauguracion" class="section">
            <h2 class="section-title">Inauguración del Evento</h2>
            <p>La Tercera Semana de la Mecatrónica se llevó a cabo los días 9 y 10 de julio de 2025, marcando un hito importante en la difusión del conocimiento tecnológico y la innovación en nuestra universidad.</p>
            
            <div class="highlight">
                <p>El 9 de julio no solo marcó el inicio de nuestro evento, sino que también coincidió con la celebración del <strong>Día Mundial de la Ingeniería Mecatrónica</strong>, lo que añadió un significado especial a esta edición.</p>
            </div>
            
            <p>La ceremonia de inauguración contó con la presencia de distinguidas autoridades universitarias, docentes, estudiantes e invitados especiales del sector industrial. El evento comenzó con palabras de bienvenida del Decano de la Facultad, seguido de ponencias magistrales de expertos en mecatrónica y automatización.</p>
            
            <p>Durante los dos días del evento, los asistentes pudieron disfrutar de:</p>
            <ul class="event-list">
                <li>Conferencias con expertos nacionales e internacionales</li>
                <li>Demostraciones de tecnología de punta</li>
                <li>Exposición de proyectos estudiantiles</li>
                <li>Talleres técnicos especializados</li>
                <li>Concurso de proyectos innovadores</li>
            </ul>
        </section>
        
        <!-- Sección de Talleres -->
        <section id="talleres" class="section">
            <h2 class="section-title">Talleres Técnicos</h2>
            <p>La programación de talleres técnicos fue uno de los pilares fundamentales de esta tercera edición, ofreciendo a los participantes la oportunidad de adquirir conocimientos prácticos en diversas áreas de la mecatrónica.</p>
            
            <h3>Miércoles 9 de Julio (2:00 PM - 5:00 PM)</h3>
            <ul class="event-list">
                <li><span class="event-time">Taller 1:</span> Diseño y fabricación PCB con Software Proteus - Ing. Edwin Fredy Chambi Mamani</li>
                <li><span class="event-time">Taller 2:</span> Programación en LabVIEW con Arduino & ESP32 - Mg. John Carlos Quispe Chambi</li>
                <li><span class="event-time">Taller 3:</span> Diseño e Impresión 3D con SolidWorks - M.Sc. Ayrton Ronaldo Rojas Calla</li>
                <li><span class="event-time">Taller 4:</span> Programación de PLC Schneider - Ing. Geyson Aquise Miranda</li>
            </ul>
            
            <h3>Jueves 10 de Julio (9:00 AM - 12:00 PM)</h3>
            <ul class="event-list">
                <li><span class="event-time">Taller 5:</span> Uso de equipos de medición (Osciloscopio & G. F.) - M.Sc. Javier Alvaro Rivera Suaña</li>
                <li><span class="event-time">Taller 6:</span> Autotrónica - Ing. Cesar Iglesias Mamani Yujra</li>
                <li><span class="event-time">Taller 7:</span> Inteligencia Artificial - M.Sc. Ferdinand Pineda Ancco</li>
                <li><span class="event-time">Taller 8:</span> Programación PLC LOGO - Dr. Máximo Amancio Montalvo Adco</li>
            </ul>
            
            <div class="highlight">
                <p>Los talleres contaron con una gran participación estudiantil, demostrando el interés por las nuevas tecnologías y su aplicación en soluciones ingenieriles.</p>
            </div>
        </section>
        
        <!-- Sección de Proyectos -->
        <section id="proyectos" class="section">
            <h2 class="section-title">Concurso de Proyectos de Automatización</h2>
            <p>Uno de los momentos más esperados de la semana fue el concurso de proyectos innovadores, donde los estudiantes de la carrera de Ingeniería Mecatrónica presentaron sus trabajos desarrollados durante el semestre.</p>
            
            <p>Los proyectos aprobados para participar en la 3ra Semana de Ingeniería Mecatrónica fueron:</p>
            
            <ul class="event-list">
                <li>Medidor de Calidad de Aire</li>
                <li>Sistema de Automatización y Control IoT para el llenado de Agua en dos Tanques</li>
                <li>Llenadora automática de botellas con PLC Mitsubishi FX2N y visión artificial</li>
                <li>Sistema de seguridad alimentada con fuente variable</li>
                <li>Prototipo Automatizado de Sellado y Clasificación de Cajas con Micro PLC Basado en ATmega328P</li>
                <li>Sistema Automatizado de Clasificación y Conteo de Cajas con Fajas Transportadoras Secuenciales Controladas por PLC</li>
                <li>Prototipado de una máquina CNC para el grabado de placas PCB</li>
                <li>Detector de radiación solar</li>
                <li>Sistema de Control y Monitoreo Inteligente de Temperatura y Humedad en Invernaderos mediante PID e IoT</li>
                <li>Adquisición y Procesamiento Eficiente de Señales Electrocardiográficas en FPGA Cyclone IV</li>
                <li>Sistema Automatizado de Embotellado con Transporte y Sellado Integrado</li>
                <li>Sistema de Control de Acceso Dual con reconocimiento facial</li>
                <li>Sensor de gas con cierre Automatizado</li>
                <li>Diseño e Implementación de un Sistema de Clasificación por Color con Banda Transportadora y Pistón Neumático Controlado por PLC basado en ATmega328</li>
                <li>Desarrollo de un Sistema de Control Térmico para Incubadora Mediante PID y Tecnología Dimmer con ESP32</li>
                <li>Máquina de ensayo de tensión en fibras textiles para el análisis de la resistencia del material</li>
                <li>Sistema de cultivo de hongos automatizado y monitorizado con IoT</li>
            </ul>
        </section>
        
        <!-- Sección de Galería -->
        <section id="galeria" class="section">
            <h2 class="section-title">Galería de Fotos</h2>
            <p>Revive los mejores momentos de la Tercera Semana de la Mecatrónica a través de nuestra galería fotográfica. Puedes reemplazar estas imágenes con tus propias fotos del evento.</p>
            
            <div class="gallery">
                <div class="gallery-item">
                    <img src="demostracion..png" alt="Talleres técnicos">
                    <div class="gallery-caption">Talleres técnicos</div>
                </div>
                <div class="gallery-item">
                    <img src="demostracion de proyectos.png" alt="Demostración de proyectos">
                    <div class="gallery-caption">Demostración de proyectos</div>
                </div>
                <div class="gallery-item">
                    <img src="talleres.png" alt="Conferencias magistrales">
                    <div class="gallery-caption">Conferencias magistrales</div>
                </div>
                <div class="gallery-item">
                    <img src="ceremonia.png" alt="Ceremonia de inauguración">
                    <div class="gallery-caption">Ceremonia de inauguración</div>
                </div>
            </div>
        </section>
        
        <!-- Sección de Contacto -->
        <section id="contacto" class="section">
            <h2 class="section-title">Contacto y Reconocimientos</h2>
            <p>La organización de la Tercera Semana de la Mecatrónica agradece a todos los participantes, ponentes, docentes y estudiantes que hicieron posible este evento.</p>
            
            <div class="contact-grid">
                <div class="contact-info">
                    <h3>Información de Contacto</h3>
                    <p>Facultad de Ingeniería Mecatrónica<br>
                    Universidad Nacional de Juliaca<br>
                    ESTUDIANTES DE LA UNAJ <br>
                    Av. Nueva Zelandia 631, Juliaca 21101</p>
                    <p>Teléfono: +51 98953****</p>
                    <p>Email: 2025108016.est@unaj.edu.pe <br>
                     2025108024.est@unaj.edu.pe <br>
                     2025108004.est@unaj.edu.pe </p>
                    
                    <a href="https://sites.google.com/view/semana-mecatronica2025/inicio?authuser=0" class="website-link" target="_blank">Visitar Sitio Web Oficial</a>
                </div>
                
                <div>
                    <h3>Reconocimientos Especiales</h3>
                    <ul class="event-list">
                        <li>Comité Organizador - Por su dedicación y esfuerzo</li>
                        <li>Docentes de la Facultad - Por su apoyo y mentoría</li>
                        <li>Estudiantes Voluntarios - Por su compromiso y trabajo</li>
                        <li>Patrocinadores - Por hacer posible este evento</li>
                        <li>Invitados Especiales - Por compartir su conocimiento</li>
                    </ul>
                </div>
            </div>
        </section>
    </div>
    
    <!-- Pie de página -->
    <footer>
        <div class="footer-content">
            <div class="footer-logo">Mecatrónica</span> UNAJ</div>
            <p>Formando a los ingenieros del futuro con excelencia académica</p>
            
            <div class="social-icons">
                <div class="social-icon">
                    <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24"><path d="M22.675 0h-21.35c-.732 0-1.325.593-1.325 1.325v21.351c0 .731.593 1.324 1.325 1.324h11.495v-9.294h-3.128v-3.622h3.128v-2.671c0-3.1 1.893-4.788 4.659-4.788 1.325 0 2.463.099 2.795.143v3.24l-1.918.001c-1.504 0-1.795.715-1.795 1.763v2.313h3.587l-.467 3.622h-3.12v9.293h6.116c.73 0 1.323-.593 1.323-1.325v-21.35c0-.732-.593-1.325-1.325-1.325z"/></svg>
                </div>
                <div class="social-icon">
                    <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
                </div>
                <div class="social-icon">
                    <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24"><path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/></svg>
                </div>
                <div class="social-icon">
                    <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24"><path d="M4.98 3.5c0 1.381-1.11 2.5-2.48 2.5s-2.48-1.119-2.48-2.5c0-1.38 1.11-2.5 2.48-2.5s2.48 1.12 2.48 2.5zm.02 4.5h-5v16h5v-16zm7.982 0h-4.968v16h4.969v-8.399c0-4.67 6.029-5.052 6.029 0v8.399h4.988v-10.131c0-7.88-8.922-7.593-11.018-3.714v-2.155z"/></svg>
                </div>
            </div>
            
            <div class="footer-links">
                <a href="#inauguracion">Inauguración</a>
                <a href="#talleres">Talleres</a>
                <a href="#proyectos">Proyectos</a>
                <a href="#galeria">Galería</a>
                <a href="#contacto">Contacto</a>
            </div>
            
            <p class="copyright">&copy; 2025 Universidad Nacional de Juliaca - Facultad de Ingeniería Mecatrónica. <br> 
Todos los derechos reservados.</p>
        </div>
    </footer>
</body>
</html>
