<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Idrissa Diouf</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }
        
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2rem;
        }
        
        nav a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            transition: all 0.3s ease;
            position: relative;
        }
        
        nav a:hover {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            transform: translateY(-2px);
        }
        
        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23ffffff" fill-opacity="0.1" d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,149.3C960,160,1056,160,1152,138.7C1248,117,1344,75,1392,53.3L1440,32L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>') no-repeat bottom;
            background-size: cover;
            animation: wave 6s ease-in-out infinite;
        }
        
        @keyframes wave {
            0%, 100% { transform: translateX(0); }
            50% { transform: translateX(-20px); }
        }
        
        .hero-content {
            z-index: 10;
            position: relative;
            animation: fadeInUp 1s ease-out;
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .hero .subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        
        .hero-description {
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            line-height: 1.8;
        }
        
        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }
        
        .cta-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        /* Sections */
        .section {
            padding: 6rem 0;
            background: white;
            position: relative;
        }
        
        .section:nth-child(even) {
            background: #f8f9fa;
        }
        
        .section h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
            position: relative;
        }
        
        .section h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 2px;
        }
        
        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(45deg, #667eea, #764ba2);
        }
        
        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }
        
        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #667eea;
        }
        
        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #333;
        }
        
        .skill-card p {
            color: #666;
            line-height: 1.6;
        }
        
        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }
        
        .project-image {
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .project-content {
            padding: 2rem;
        }
        
        .project-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #333;
        }
        
        .project-card p {
            color: #666;
            margin-bottom: 1rem;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }
        
        .tech-tag {
            background: #f0f2f5;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            color: #667eea;
        }
        
        /* Formation */
        .formation-timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .formation-timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(45deg, #667eea, #764ba2);
        }
        
        .timeline-item {
            position: relative;
            margin: 3rem 0;
            padding: 2rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            width: 45%;
            transition: all 0.3s ease;
        }
        
        .timeline-item:nth-child(odd) {
            left: 0;
        }
        
        .timeline-item:nth-child(even) {
            left: 55%;
        }
        
        .timeline-item:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }
        
        .timeline-item::before {
            content: '';
            position: absolute;
            top: 50%;
            right: -35px;
            width: 15px;
            height: 15px;
            background: #667eea;
            border-radius: 50%;
            transform: translateY(-50%);
        }
        
        .timeline-item:nth-child(even)::before {
            left: -35px;
        }
        
        .timeline-year {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 1rem;
        }
        
        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 3rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .form-group {
            margin-bottom: 2rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #333;
            font-weight: 500;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #f0f2f5;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
        }
        
        .submit-btn {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }
        
        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }
        
        /* Footer */
        footer {
            background: #333;
            color: white;
            padding: 2rem 0;
            text-align: center;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero .subtitle {
                font-size: 1.2rem;
            }
            
            .skills-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .timeline-item {
                width: 100%;
                left: 0 !important;
            }
            
            .timeline-item::before {
                left: -35px !important;
            }
            
            .formation-timeline::before {
                left: 0;
            }
            
            nav ul {
                flex-direction: column;
                gap: 1rem;
            }
        }
        
        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s ease-out forwards;
        }
        
        .fade-in:nth-child(1) { animation-delay: 0.1s; }
        .fade-in:nth-child(2) { animation-delay: 0.2s; }
        .fade-in:nth-child(3) { animation-delay: 0.3s; }
        .fade-in:nth-child(4) { animation-delay: 0.4s; }
        .fade-in:nth-child(5) { animation-delay: 0.5s; }
        .fade-in:nth-child(6) { animation-delay: 0.6s; }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#accueil">Accueil</a></li>
            <li><a href="#competences">Compétences</a></li>
            <li><a href="#projets">Projets</a></li>
            <li><a href="#formation">Formation</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="accueil" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Idrissa Diouf</h1>
                <p class="subtitle">Élève en Terminale Scientifique</p>
                <div class="hero-description">
                    <p>Passionné par la technologie, les sciences et l'innovation, je cultive une ambition claire : devenir enseignant-chercheur et contribuer activement au développement du monde numérique. Mon parcours en terminale scientifique avec spécialité mathématiques me permet d'acquérir les bases solides nécessaires pour atteindre mes objectifs.</p>
                </div>
                <a href="#competences" class="cta-button">Découvrir mon profil</a>
            </div>
        </div>
    </section>

    <section id="competences" class="section">
        <div class="container">
            <h2>Mes Compétences</h2>
            <div class="skills-grid">
                <div class="skill-card fade-in">
                    <div class="skill-icon">💻</div>
                    <h3>Développement Web</h3>
                    <p>Maîtrise des bases du HTML et CSS pour créer des sites web modernes et responsive. Capacité à structurer et styliser des pages web avec un souci du détail.</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">📊</div>
                    <h3>Outils Bureautiques</h3>
                    <p>Excellente maîtrise de la suite Office (Word, Excel, PowerPoint). Création de présentations professionnelles et analyse de données avec Excel.</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🎯</div>
                    <h3>Communication</h3>
                    <p>Excellentes compétences en communication écrite et orale. Expérience en tant que voix off et modérateur, capacité à transmettre des idées clairement.</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🤝</div>
                    <h3>Travail d'Équipe</h3>
                    <p>Esprit collaboratif développé à travers diverses expériences associatives et projets de groupe. Capacité à fédérer et à motiver une équipe.</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">🎭</div>
                    <h3>Créativité & Expression</h3>
                    <p>Expérience dans le domaine artistique avec la modération du club théâtre. Capacité à penser de manière créative et à s'exprimer avec aisance.</p>
                </div>
                <div class="skill-card fade-in">
                    <div class="skill-icon">📋</div>
                    <h3>Organisation</h3>
                    <p>Sens aigu de l'organisation et de la planification. Capacité à gérer plusieurs projets simultanément avec rigueur et méthodologie.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="projets" class="section">
        <div class="container">
            <h2>Mes Projets</h2>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-image">🌱</div>
                    <div class="project-content">
                        <h3>Projet Vidéo sur le Recyclage</h3>
                        <p>Réalisation d'une voix off pour un projet de sensibilisation au recyclage. Ce projet m'a permis de développer mes compétences en communication et de contribuer à une cause environnementale importante.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Communication</span>
                            <span class="tech-tag">Sensibilisation</span>
                            <span class="tech-tag">Environnement</span>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-image">👥</div>
                    <div class="project-content">
                        <h3>Projets de Groupe Scolaires</h3>
                        <p>Participation active à divers projets collaboratifs encadrés par les enseignants. Ces expériences m'ont permis de développer mon esprit d'équipe et mes capacités d'organisation.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Collaboration</span>
                            <span class="tech-tag">Recherche</span>
                            <span class="tech-tag">Présentation</span>
                        </div>
                    </div>
                </div>
                <div class="project-card fade-in">
                    <div class="project-image">🎭</div>
                    <div class="project-content">
                        <h3>Modération Club Théâtre</h3>
                        <p>Responsabilité de la modération du club théâtre scolaire. Coordination des activités, animation des séances et accompagnement des autres élèves dans leurs projets artistiques.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Leadership</span>
                            <span class="tech-tag">Animation</span>
                            <span class="tech-tag">Théâtre</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="formation" class="section">
        <div class="container">
            <h2>Formation & Expériences</h2>
            <div class="formation-timeline">
                <div class="timeline-item fade-in">
                    <div class="timeline-year">2024-2025</div>
                    <h3>Terminale Scientifique</h3>
                    <p><strong>Spécialité Mathématiques</strong></p>
                    <p>Formation approfondie en mathématiques, sciences physiques et chimiques. Développement des compétences analytiques et de résolution de problèmes complexes.</p>
                </div>
                <div class="timeline-item fade-in">
                    <div class="timeline-year">2024</div>
                    <h3>Modérateur Club Théâtre</h3>
                    <p><strong>Responsabilité associative</strong></p>
                    <p>Encadrement et animation des activités théâtrales de l'établissement. Développement du leadership et des compétences en gestion d'équipe.</p>
                </div>
                <div class="timeline-item fade-in">
                    <div class="timeline-year">2024</div>
                    <h3>Renforcements Informatique</h3>
                    <p><strong>Formation continue</strong></p>
                    <p>Participation à des sessions de renforcement en informatique pour approfondir mes connaissances techniques et rester à jour avec les nouvelles technologies.</p>
                </div>
                <div class="timeline-item fade-in">
                    <div class="timeline-year">2024</div>
                    <h3>Projet Vidéo Recyclage</h3>
                    <p><strong>Voix off et sensibilisation</strong></p>
                    <p>Contribution vocale à un projet de sensibilisation environnementale, développement des compétences en communication audiovisuelle.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="section">
        <div class="container">
            <h2>Me Contacter</h2>
            <div class="contact-form">
                <form>
                    <div class="form-group">
                        <label for="nom">Nom complet</label>
                        <input type="text" id="nom" name="nom" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="sujet">Sujet</label>
                        <input type="text" id="sujet" name="sujet" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Envoyer le message</button>
                </form>
                <div style="text-align: center; margin-top: 2rem; padding-top: 2rem; border-top: 1px solid #eee;">
                    <p><strong>Idrissa Diouf</strong></p>
                    <p>📧 idrissadiouffromfm@gmail.com</p>
                    <p>📱 +221 76 210 57 45</p>
                    <p>📍 Mbour, Sénégal</p>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2025 Idrissa Diouf. Tous droits réservés.</p>
        </div>
    </footer>

    <script>
        // Navigation smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Form submission handling
        document.querySelector('form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Merci pour votre message ! Je vous répondrai dans les plus brefs délais.');
            this.reset();
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Active navigation highlighting
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            const navLinks = document.querySelectorAll('nav a');
            
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (scrollY >= sectionTop - 200) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === `#${current}`) {
                    link.classList.add('active');
                }
            });
        });
    </script>
</body>
</html>
