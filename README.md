# index.html
index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blaise Kimiti | Geography & Environmental Specialist</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto+Slab:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2c786c;
            --secondary: #004445;
            --accent: #f8b400;
            --light: #faf5e4;
            --dark: #1a1a1a;
            --text: #333333;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            color: var(--text);
            line-height: 1.6;
            background-color: var(--light);
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Roboto Slab', serif;
            color: var(--secondary);
        }

        a {
            text-decoration: none;
            color: var(--primary);
            transition: all 0.3s ease;
        }

        a:hover {
            color: var(--accent);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation */
        header {
            background-color: white;
            box-shadow: var(--shadow);
            position: fixed;
            width: 100%;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        header.scrolled {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--primary);
        }

        .logo span {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            font-weight: 500;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.pexels.com/photos/2387793/pexels-photo-2387793.jpeg') no-repeat center center/cover;
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 68, 69, 0.7);
            z-index: -1;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
            animation: fadeIn 1.5s ease;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: white;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        .hero .btn {
            display: inline-block;
            background-color: var(--accent);
            color: var(--dark);
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .hero .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* About Section */
        .about {
            padding: 100px 0;
            background-color: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            display: inline-block;
            position: relative;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--accent);
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-img {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            animation: float 3s ease-in-out infinite;
        }

        .about-img img {
            width: 100%;
            height: auto;
            display: block;
        }

        .about-text {
            flex: 1;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
        }

        .about-text p {
            margin-bottom: 15px;
        }

        .skills {
            margin-top: 30px;
        }

        .skill-item {
            margin-bottom: 15px;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }

        .skill-bar {
            height: 10px;
            background-color: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background-color: var(--primary);
            border-radius: 5px;
            transition: width 1s ease;
        }

        /* Education Section */
        .education {
            padding: 100px 0;
            background-color: var(--light);
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
            padding: 40px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            width: 2px;
            background-color: var(--primary);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -1px;
        }

        .timeline-item {
            padding: 20px 40px;
            position: relative;
            width: 50%;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.5s ease;
        }

        .timeline-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .timeline-item:nth-child(odd) {
            left: 0;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
        }

        .timeline-content {
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: var(--shadow);
            position: relative;
        }

        .timeline-content::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: white;
            top: 30px;
            transform: rotate(45deg);
            box-shadow: 1px -1px 1px rgba(0, 0, 0, 0.1);
        }

        .timeline-item:nth-child(odd) .timeline-content::after {
            right: -10px;
        }

        .timeline-item:nth-child(even) .timeline-content::after {
            left: -10px;
        }

        .timeline-date {
            position: absolute;
            width: 120px;
            background-color: var(--accent);
            color: var(--dark);
            padding: 5px 10px;
            border-radius: 20px;
            text-align: center;
            font-weight: 600;
            top: 20px;
        }

        .timeline-item:nth-child(odd) .timeline-date {
            right: -150px;
        }

        .timeline-item:nth-child(even) .timeline-date {
            left: -150px;
        }

        .timeline-content h3 {
            margin-bottom: 10px;
        }

        .timeline-content p {
            margin-bottom: 10px;
        }

        .download-cv {
            display: inline-block;
            margin-top: 30px;
            background-color: var(--primary);
            color: white;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .download-cv:hover {
            background-color: var(--secondary);
            transform: translateY(-3px);
        }

        /* Interests Section */
        .interests {
            padding: 100px 0;
            background-color: white;
        }

        .interests-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            margin-top: 50px;
        }

        .interest-card {
            flex: 1 1 300px;
            max-width: 350px;
            background-color: var(--light);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            transform: translateY(20px);
            opacity: 0;
        }

        .interest-card.visible {
            transform: translateY(0);
            opacity: 1;
        }

        .interest-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .interest-img {
            height: 200px;
            overflow: hidden;
        }

        .interest-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .interest-card:hover .interest-img img {
            transform: scale(1.1);
        }

        .interest-content {
            padding: 20px;
        }

        .interest-content h3 {
            margin-bottom: 10px;
            color: var(--primary);
        }

        /* Projects Section */
        .projects {
            padding: 100px 0;
            background-color: var(--light);
        }

        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .project-img {
            height: 250px;
            overflow: hidden;
            position: relative;
        }

        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .project-card:hover .project-img img {
            transform: scale(1.1);
        }

        .project-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(44, 120, 108, 0.8), rgba(0, 68, 69, 0.9));
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover .project-overlay {
            opacity: 1;
        }

        .project-overlay a {
            color: white;
            font-size: 1.5rem;
            margin: 0 10px;
            transition: transform 0.3s ease;
        }

        .project-overlay a:hover {
            transform: translateY(-5px);
        }

        .project-content {
            padding: 20px;
        }

        .project-content h3 {
            margin-bottom: 10px;
        }

        .project-content p {
            margin-bottom: 15px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .project-tag {
            background-color: var(--light);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            color: var(--primary);
        }

        /* Contact Section */
        .contact {
            padding: 100px 0;
            background-color: white;
        }

        .contact-container {
            display: flex;
            gap: 50px;
            margin-top: 50px;
        }

        .contact-info {
            flex: 1;
        }

        .contact-info h3 {
            margin-bottom: 20px;
            font-size: 1.8rem;
        }

        .contact-details {
            margin-bottom: 30px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background-color: var(--light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: var(--primary);
            font-size: 1.2rem;
        }

        .contact-form {
            flex: 1;
            background-color: var(--light);
            padding: 30px;
            border-radius: 10px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: 'Poppins', sans-serif;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(44, 120, 108, 0.2);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        .submit-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            background-color: var(--secondary);
            transform: translateY(-3px);
        }

        /* Footer */
        footer {
            background-color: var(--secondary);
            color: white;
            padding: 30px 0;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 10px;
            color: white;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background-color: var(--accent);
            color: var(--dark);
            transform: translateY(-5px);
        }

        .copyright {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .about-content {
                flex-direction: column;
            }

            .timeline::before {
                left: 30px;
            }

            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 0;
            }

            .timeline-item:nth-child(even) {
                left: 0;
            }

            .timeline-item:nth-child(odd) .timeline-date,
            .timeline-item:nth-child(even) .timeline-date {
                left: 0;
                right: auto;
                top: -30px;
            }

            .timeline-item:nth-child(odd) .timeline-content::after,
            .timeline-item:nth-child(even) .timeline-content::after {
                left: 20px;
                right: auto;
                top: -10px;
                transform: rotate(-45deg);
            }

            .contact-container {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background-color: white;
                flex-direction: column;
                align-items: center;
                padding-top: 40px;
                transition: all 0.5s ease;
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 15px 0;
            }

            .hamburger {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1rem;
            }
        }

        @media (max-width: 576px) {
            .section-title h2 {
                font-size: 2rem;
            }

            .projects-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container">
            <nav>
                <div class="logo">Blaise<span>Kimiti</span></div>
                <ul class="nav-links">
                    <li><a href="#about">About</a></li>
                    <li><a href="#education">Education</a></li>
                    <li><a href="#interests">Interests</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Blaise Kimiti</h1>
            <p>Geography & Environmental Studies Specialist | GIS Expert | Sustainable Development Enthusiast</p>
            <a href="#about" class="btn">Explore My Journey</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-title">
                <h2>About Me</h2>
            </div>
            <div class="about-content">
                <div class="about-img">
                    <img src="Official_snap.jpg" alt="Blaise Kimiti">
                </div>
                <div class="about-text">
                    <h3>Hi! I'm Blaise Kimiti</h3>
                    <p>A dedicated and enthusiastic Bachelor of Arts in Geography and Environmental Studies student with a passion for environmental management, spatial data analysis, and sustainable development.</p>
                    <p>Proficient in GIS applications and skilled in research, report writing, and critical thinking. A proactive learner with excellent communication and problem-solving abilities, eager to apply academic knowledge in practical settings.</p>
                    
                    <div class="skills">
                        <div class="skill-item">
                            <div class="skill-name">
                                <span>ArcGIS Products</span>
                                <span>90%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 90%;"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">
                                <span>Spatial Data Analysis</span>
                                <span>85%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 85%;"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">
                                <span>Environmental Research</span>
                                <span>88%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 88%;"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-name">
                                <span>Report Writing</span>
                                <span>92%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" style="width: 92%;"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="education">
        <div class="container">
            <div class="section-title">
                <h2>Education & Experience</h2>
            </div>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Bachelor of Arts (Geography & Environmental Studies)</h3>
                        <h4>Catholic University of Eastern Africa</h4>
                        <p>Developed a strong understanding of physical and human geography, environmental management, and sustainable development.</p>
                        <p>Gained expertise in geographic information systems (GIS), remote sensing, and environmental impact assessments.</p>
                    </div>
                    <div class="timeline-date">2022 - 2026</div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Advanced GIS Certification</h3>
                        <p>Advanced skills in spatial analysis, cartography, and geodatabase management using ArcGIS products.</p>
                    </div>
                    <div class="timeline-date">2024</div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>Fundamentals of GIS Certification</h3>
                        <p>Mastered the basics of geographic information systems, including data collection, analysis, and visualization.</p>
                    </div>
                    <div class="timeline-date">2024</div>
                </div>
                
                </div>
            </div>
            <div style="text-align: center;">
                <a href="BLAISE_KIMITI_CV.pdf" class="download-cv" download>
                    <i class="fas fa-download"></i> Download My CV
                </a>
            </div>
        </div>
    </section>

    <!-- Interests Section -->
    <section id="interests" class="interests">
        <div class="container">
            <div class="section-title">
                <h2>My Interests</h2>
            </div>
            <div class="interests-container">
                <div class="interest-card">
                    <div class="interest-img">
                        <img src="https://media.istockphoto.com/id/1392287714/photo/human-hand-holding-green-environmental-tree-esg-icon-society-and-governance-sustainable.jpg?b=1&s=612x612&w=0&k=20&c=RVxnQ7WyEuidiGEn9PORSWHI2NIg2VNCUb8jJQh6s7k=" alt="Environmental Management">
                    </div>
                    <div class="interest-content">
                        <h3>Environmental Management</h3>
                        <p>Passionate about developing sustainable solutions for environmental challenges and promoting conservation efforts.</p>
                    </div>
                </div>
                <div class="interest-card">
                    <div class="interest-img">
                        <img src="https://media.istockphoto.com/id/182062885/photo/space-station-in-earth-orbit.jpg?b=1&s=612x612&w=0&k=20&c=JTFIFfmMk7RryyYhRbDhhgdPVQs7kFDIgvB4JmNqQ3Y=" alt="GIS Applications">
                    </div>
                    <div class="interest-content">
                        <h3>GIS Applications</h3>
                        <p>Fascinated by spatial data analysis and how geographic information systems can solve real-world problems.</p>
                    </div>
                </div>
                <div class="interest-card">
                    <div class="interest-img">
                        <img src="https://media.istockphoto.com/id/1450272068/photo/wind-sun-and-water-energy.jpg?b=1&s=612x612&w=0&k=20&c=kqzh30craD6AVukqNYdkovgcP4gxV3QN6lgs07b1YUg=" alt="Sustainable Development">
                    </div>
                    <div class="interest-content">
                        <h3>Sustainable Development</h3>
                        <p>Committed to finding balance between human needs and environmental protection for future generations.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <div class="section-title">
                <h2>My Projects</h2>
            </div>
            <div class="projects-container">
                <div class="project-card">
                    <div class="project-img">
                        <img src="https://media.istockphoto.com/id/1400218353/photo/green-technology-environmental-technology-concept-sustainable-development-goals-sdgs.jpg?b=1&s=612x612&w=0&k=20&c=440xtHbckR3TOrhKNBo-4mXpV8QY1V6NePgAvAjdFpM=" alt="Urban Heat Island Analysis">
                        <div class="project-overlay">
                            <a href="#"><i class="fas fa-link"></i></a>
                            <a href="#"><i class="fas fa-search"></i></a>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3>Urban Heat Island Analysis</h3>
                        <p>A comprehensive study of temperature variations in Nairobi using remote sensing data and GIS analysis to identify urban heat islands.</p>
                        <div class="project-tags">
                            <span class="project-tag">GIS</span>
                            <span class="project-tag">Remote Sensing</span>
                            <span class="project-tag">Urban Planning</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <img src="https://images.pexels.com/photos/31344103/pexels-photo-31344103/free-photo-of-lush-mountain-stream-surrounded-by-greenery.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Watershed Management">
                        <div class="project-overlay">
                            <a href="#"><i class="fas fa-link"></i></a>
                            <a href="#"><i class="fas fa-search"></i></a>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3>Watershed Management Plan</h3>
                        <p>Developed a sustainable watershed management strategy for the Tana River basin, incorporating community input and scientific data.</p>
                        <div class="project-tags">
                            <span class="project-tag">Environmental</span>
                            <span class="project-tag">Hydrology</span>
                            <span class="project-tag">Community</span>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <img src="https://images.pexels.com/photos/171328/pexels-photo-171328.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Land Use Change">
                        <div class="project-overlay">
                            <a href="#"><i class="fas fa-link"></i></a>
                            <a href="#"><i class="fas fa-search"></i></a>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3>Land Use Change Detection</h3>
                        <p>Used multi-temporal satellite imagery to analyze land use changes in the Nairobi Metropolitan area over the past 20 years.</p>
                        <div class="project-tags">
                            <span class="project-tag">GIS</span>
                            <span class="project-tag">Remote Sensing</span>
                            <span class="project-tag">Change Detection</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contact Me</h2>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Let's Connect</h3>
                    <p>Feel free to reach out for collaborations, questions, or just to say hello!</p>
                    
                    <div class="contact-details">
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div>
                                <h4>Location</h4>
                                <p>Nairobi, Kenya</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div>
                                <h4>Email</h4>
                                <p>kimitiblaise@gmail.com</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-phone-alt"></i>
                            </div>
                            <div>
                                <h4>Phone</h4>
                                <p>+254 115 915 230</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" name="subject" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Your Message</label>
                            <textarea id="message" name="message" required></textarea>
                        </div>
                        <button type="submit" class="submit-btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="social-links">
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
            </div>
            <p class="copyright">&copy; 2024 Blaise Kimiti. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        // Mobile Navigation
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.innerHTML = navLinks.classList.contains('active') ? 
                '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.innerHTML = '<i class="fas fa-bars"></i>';
            });
        });

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Scroll animation for timeline items
        const timelineItems = document.querySelectorAll('.timeline-item');
        const interestCards = document.querySelectorAll('.interest-card');

        function checkScroll() {
            const triggerBottom = window.innerHeight * 0.8;

            timelineItems.forEach(item => {
                const itemTop = item.getBoundingClientRect().top;
                if (itemTop < triggerBottom) {
                    item.classList.add('visible');
                }
            });

            interestCards.forEach(card => {
                const cardTop = card.getBoundingClientRect().top;
                if (cardTop < triggerBottom) {
                    card.classList.add('visible');
                }
            });
        }

        window.addEventListener('scroll', checkScroll);
        window.addEventListener('load', checkScroll);

        // Form submission
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! I will get back to you soon.');
            contactForm.reset();
        });
    </script>
</body>
</html>
