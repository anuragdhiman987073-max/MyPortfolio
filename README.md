# MyPortfolio
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Anurag Dhiman - Portfolio</title>
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  
  <style>
    /* CSS Variables & Global Styles */
    :root {
      --bg-dark: #070B19;
      --bg-card: #0D1329;
      --bg-card-hover: #131B38;
      --primary-blue: #2563EB;
      --primary-light: #3B82F6;
      --text-main: #FFFFFF;
      --text-muted: #94A3B8;
      --border-color: #1E293B;
      --font-family: 'Inter', sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      font-family: var(--font-family);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    /* Header Navigation */
    header {
      position: sticky;
      top: 0;
      background-color: rgba(7, 11, 25, 0.9);
      backdrop-filter: blur(10px);
      z-index: 1000;
      border-bottom: 1px solid var(--border-color);
    }

    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 70px;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 700;
    }

    .logo span {
      color: var(--primary-light);
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 25px;
      align-items: center;
    }

    .nav-links a {
      color: var(--text-muted);
      font-size: 0.95rem;
      font-weight: 500;
      transition: color 0.3s;
    }

    .nav-links a.active, 
    .nav-links a:hover {
      color: var(--primary-light);
    }

    .theme-toggle {
      background: none;
      border: none;
      color: var(--text-muted);
      font-size: 1.1rem;
      cursor: pointer;
      margin-left: 15px;
    }

    /* Hero Section */
    .hero {
      padding: 60px 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 40px;
    }

    .hero-content {
      flex: 1;
      max-width: 600px;
    }

    .role-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background-color: rgba(37, 99, 235, 0.1);
      border: 1px solid rgba(37, 99, 235, 0.3);
      color: var(--primary-light);
      padding: 6px 14px;
      border-radius: 20px;
      font-size: 0.85rem;
      margin-bottom: 20px;
    }

    .hero-title {
      font-size: 3.5rem;
      font-weight: 800;
      line-height: 1.1;
      margin-bottom: 10px;
    }

    .hero-title span {
      color: var(--primary-light);
    }

    .hero-subtitle {
      font-size: 1.25rem;
      font-weight: 600;
      color: var(--text-muted);
      margin-bottom: 15px;
    }

    .hero-description {
      color: var(--text-muted);
      font-size: 0.95rem;
      margin-bottom: 30px;
      line-height: 1.6;
    }

    .hero-buttons {
      display: flex;
      gap: 15px;
      margin-bottom: 30px;
    }

    .btn {
      padding: 10px 22px;
      border-radius: 6px;
      font-size: 0.9rem;
      font-weight: 600;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s;
    }

    .btn-primary {
      background-color: var(--primary-blue);
      color: white;
      border: none;
    }

    .btn-primary:hover {
      background-color: var(--primary-light);
    }

    .btn-secondary {
      background-color: transparent;
      border: 1px solid var(--border-color);
      color: white;
    }

    .btn-secondary:hover {
      background-color: var(--bg-card);
    }

    .social-links {
      display: flex;
      gap: 12px;
    }

    .social-btn {
      width: 40px;
      height: 40px;
      border-radius: 8px;
      background-color: var(--bg-card);
      border: 1px solid var(--border-color);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text-muted);
      transition: 0.3s;
    }

    .social-btn:hover {
      color: white;
      border-color: var(--primary-light);
    }

    .hero-image-container {
      position: relative;
      flex: 1;
      display: flex;
      justify-content: center;
    }

    .hero-image-bg {
      width: 380px;
      height: 380px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(37,99,235,0.3) 0%, rgba(7,11,25,0) 70%);
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 1;
    }

    .hero-image {
      width: 360px;
      height: 420px;
      object-fit: cover;
      border-radius: 50%;
      position: relative;
      z-index: 2;
    }

    /* Section Cards Common Style */
    .card {
      background-color: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      padding: 30px;
      margin-bottom: 25px;
    }

    .card-title {
      font-size: 1.25rem;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 20px;
    }

    .card-title i {
      color: var(--primary-light);
    }

    /* About Section */
    .about-grid {
      display: grid;
      grid-template-columns: 1.2fr 1fr;
      gap: 30px;
    }

    .about-info-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }

    .info-item {
      display: flex;
      align-items: flex-start;
      gap: 12px;
    }

    .info-item i {
      color: var(--primary-light);
      margin-top: 4px;
    }

    .info-item label {
      font-weight: 600;
      display: block;
      font-size: 0.9rem;
    }

    .info-item span {
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    /* Skills Section */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(110px, 1fr));
      gap: 15px;
    }

    .skill-card {
      background-color: rgba(255, 255, 255, 0.02);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 15px 10px;
      text-align: center;
      transition: transform 0.3s;
    }

    .skill-card:hover {
      transform: translateY(-5px);
      border-color: var(--primary-light);
    }

    .skill-icon {
      font-size: 2rem;
      margin-bottom: 8px;
      color: var(--primary-light);
    }

    .skill-name {
      font-size: 0.85rem;
      font-weight: 600;
      margin-bottom: 8px;
    }

    .rating-dots {
      display: flex;
      justify-content: center;
      gap: 4px;
    }

    .dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background-color: #334155;
    }

    .dot.filled {
      background-color: var(--primary-light);
    }

    /* Projects Section */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }

    .project-card {
      background-color: rgba(255, 255, 255, 0.02);
      border: 1px solid var(--border-color);
      border-radius: 8px;
      padding: 20px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .project-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 10px;
    }

    .project-title {
      font-size: 1.05rem;
      font-weight: 600;
      color: var(--primary-light);
    }

    .project-desc {
      color: var(--text-muted);
      font-size: 0.85rem;
      margin-bottom: 15px;
    }

    .project-tags {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .tag {
      background-color: rgba(37, 99, 235, 0.1);
      color: var(--text-muted);
      font-size: 0.75rem;
      padding: 4px 10px;
      border-radius: 4px;
      border: 1px solid var(--border-color);
    }

    /* Grid layout for Achievements & Certifications */
    .two-col-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 25px;
    }

    .list-item {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      font-size: 0.85rem;
      color: var(--text-muted);
      margin-bottom: 10px;
    }

    .list-item i {
      color: var(--primary-light);
      margin-top: 3px;
    }

    /* Education Timeline */
    .education-timeline {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
      position: relative;
    }

    .edu-item {
      border-left: 2px solid var(--primary-blue);
      padding-left: 15px;
    }

    .edu-degree {
      font-size: 0.95rem;
      font-weight: 600;
      color: var(--primary-light);
    }

    .edu-school {
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .edu-details {
      display: flex;
      justify-content: space-between;
      font-size: 0.8rem;
      color: var(--text-muted);
      margin-top: 5px;
    }

    /* Footer / Contact Banner */
    .connect-banner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      padding: 30px;
      margin-bottom: 30px;
    }

    .connect-text h3 {
      font-size: 1.2rem;
      margin-bottom: 5px;
    }

    .connect-text p {
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    .connect-details {
      display: flex;
      gap: 20px;
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    .connect-details div {
      display: flex;
      align-items: center;
      gap: 8px;
    }

    footer {
      text-align: center;
      padding: 20px 0;
      font-size: 0.8rem;
      color: var(--text-muted);
      border-top: 1px solid var(--border-color);
    }

    /* Responsive Adjustments */
    @media (max-width: 900px) {
      .hero, .about-grid, .two-col-grid, .education-timeline, .connect-banner, .projects-grid {
        grid-template-columns: 1fr;
        flex-direction: column;
      }
      .about-info-grid {
        grid-template-columns: 1fr;
      }
      .hero-title {
        font-size: 2.5rem;
      }
    }
  </style>
</head>
<body>

  <!-- Header -->
  <header>
    <div class="container navbar">
      <div class="logo">Anurag<span>.</span></div>
      <ul class="nav-links">
        <li><a href="#home" class="active">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#certifications">Certifications</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <button class="theme-toggle"><i class="fa-regular fa-moon"></i></button>
    </div>
  </header>

  <main class="container">
    
    <!-- Hero Section -->
    <section id="home" class="hero">
      <div class="hero-content">
        <div class="role-badge">
          <i class="fa-solid fa-code"></i> Java Developer
        </div>
        <h1 class="hero-title">Hi, I'm <br><span>Anurag Dhiman</span></h1>
        <p class="hero-subtitle">Java Developer | MCA Student | Problem Solver</p>
        <p class="hero-description">
          Motivated Java Developer pursuing MCA with strong foundations in Java, Advanced Java, MySQL, Oracle, OOP and SDLC. Passionate about building scalable applications and solving real-world problems.
        </p>
        <div class="hero-buttons">
          <a href="#" class="btn btn-primary"><i class="fa-solid fa-download"></i> Download Resume</a>
          <a href="#contact" class="btn btn-secondary"><i class="fa-regular fa-paper-plane"></i> Contact Me</a>
        </div>
        <div class="social-links">
          <a href="#" class="social-btn"><i class="fa-brands fa-linkedin-in"></i></a>
          <a href="#" class="social-btn"><i class="fa-brands fa-github"></i></a>
          <a href="#" class="social-btn"><i class="fa-regular fa-envelope"></i></a>
          <a href="#" class="social-btn"><i class="fa-solid fa-mobile-screen"></i></a>
        </div>
      </div>
      <div class="hero-image-container">
        <div class="hero-image-bg"></div>
        <!-- Replace src with your own image URL -->
        <img src="https://via.placeholder.com/360x420" alt="Anurag Dhiman" class="hero-image">
      </div>
    </section>

    <!-- About Me Section -->
    <section id="about" class="card">
      <div class="about-grid">
        <div>
          <h2 class="card-title"><i class="fa-regular fa-user"></i> About Me</h2>
          <p style="color: var(--text-muted); font-size: 0.9rem; line-height: 1.7;">
            I am an aspiring Java Developer currently pursuing MCA at KIET Group of Institutions. I love building applications that make a difference. I have experience in developing web-based applications and enjoy problem solving through clean, efficient code.
          </p>
        </div>
        <div class="about-info-grid">
          <div class="info-item">
            <i class="fa-regular fa-user"></i>
            <div>
              <label>Name:</label>
              <span>Anurag Dhiman</span>
            </div>
          </div>
          <div class="info-item">
            <i class="fa-solid fa-location-dot"></i>
            <div>
              <label>Location:</label>
              <span>Saharanpur, Uttar Pradesh</span>
            </div>
          </div>
          <div class="info-item">
            <i class="fa-regular fa-envelope"></i>
            <div>
              <label>Email:</label>
              <span>anuragdhiman987073@gmail.com</span>
            </div>
          </div>
          <div class="info-item">
            <i class="fa-solid fa-graduation-cap"></i>
            <div>
              <label>Degree:</label>
              <span>Master of Computer Applications</span>
            </div>
          </div>
          <div class="info-item">
            <i class="fa-solid fa-phone"></i>
            <div>
              <label>Phone:</label>
              <span>+91 9870733933</span>
            </div>
          </div>
          <div class="info-item">
            <i class="fa-solid fa-briefcase"></i>
            <div>
              <label>Experience:</label>
              <span>Fresher</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Technical Skills Section -->
    <section id="skills" class="card">
      <h2 class="card-title"><i class="fa-solid fa-code"></i> Technical Skills</h2>
      <div class="skills-grid">
        
        <div class="skill-card">
          <i class="fa-brands fa-java skill-icon"></i>
          <div class="skill-name">Java</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-solid fa-code skill-icon"></i>
          <div class="skill-name">Advanced Java</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-solid fa-database skill-icon"></i>
          <div class="skill-name">MySQL</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-solid fa-database skill-icon"></i>
          <div class="skill-name">Oracle</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-brands fa-html5 skill-icon"></i>
          <div class="skill-name">HTML5</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-brands fa-css3-alt skill-icon"></i>
          <div class="skill-name">CSS3</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-brands fa-github skill-icon"></i>
          <div class="skill-name">GitHub</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span><span class="dot"></span>
          </div>
        </div>

        <div class="skill-card">
          <i class="fa-solid fa-diagram-project skill-icon"></i>
          <div class="skill-name">SDLC & OOP</div>
          <div class="rating-dots">
            <span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot filled"></span><span class="dot"></span>
          </div>
        </div>

      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="card">
      <h2 class="card-title"><i class="fa-solid fa-layer-group"></i> Projects</h2>
      <div class="projects-grid">
        
        <div class="project-card">
          <div>
            <div class="project-header">
              <h3 class="project-title">Edu Connect - College ERP Portal</h3>
              <a href="#"><i class="fa-solid fa-arrow-up-right-from-square" style="color: var(--text-muted); font-size: 0.85rem;"></i></a>
            </div>
            <p class="project-desc">
              Developed a centralized ERP Portal for academic and administrative management. Implemented attendance tracking, result management, marks management, and role-based access for Students, Faculty, and Administrators.
            </p>
          </div>
          <div class="project-tags">
            <span class="tag">Java</span>
            <span class="tag">MySQL</span>
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
          </div>
        </div>

        <div class="project-card">
          <div>
            <div class="project-header">
              <h3 class="project-title">Bridge-UP (Mentor-Mentee Platform)</h3>
              <a href="#"><i class="fa-solid fa-arrow-up-right-from-square" style="color: var(--text-muted); font-size: 0.85rem;"></i></a>
            </div>
            <p class="project-desc">
              Developed a mentor-mentee platform connecting students with industry professionals for career guidance, skill development, and industry-focused mentorship. Participated in development, testing, and deployment activities.
            </p>
          </div>
          <div class="project-tags">
            <span class="tag">Java</span>
            <span class="tag">Web Development</span>
            <span class="tag">MySQL</span>
          </div>
        </div>

      </div>
    </section>

    <!-- Achievements & Certifications Split Section -->
    <div class="two-col-grid">
      
      <!-- Achievements -->
      <section class="card">
        <h2 class="card-title"><i class="fa-solid fa-trophy"></i> Achievements</h2>
        <div class="list-item">
          <i class="fa-regular fa-circle-check"></i>
          <span>Salesforce Agentblazer Champion (2026)</span>
        </div>
        <div class="list-item">
          <i class="fa-regular fa-circle-check"></i>
          <span>Salesforce Trailhead Points (42000+)</span>
        </div>
        <div class="list-item">
          <i class="fa-regular fa-circle-check"></i>
          <span>Achieved 2nd position at department level in INNOTECH competition</span>
        </div>
      </section>

      <!-- Certifications -->
      <section id="certifications" class="card">
        <h2 class="card-title"><i class="fa-solid fa-award"></i> Certifications</h2>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>Cisco Networking Academy - Networking Basics</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>NASSCOM - Gen AI (Skill Development Program)</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>NASSCOM - Digital Application Fundamentals (STEM)</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>Infosys Springboard - Java Programming Fundamentals</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>Linux for Beginners</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>Software Engineering, Web Design</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>Testing Basics and Test Management</span>
        </div>
        <div class="list-item">
          <i class="fa-solid fa-circle" style="font-size: 0.4rem;"></i>
          <span>GSSoC's 26 (Girlscript Summer of Code 2026)</span>
        </div>
      </section>

    </div>

    <!-- Education Section -->
    <section id="education" class="card">
      <h2 class="card-title"><i class="fa-solid fa-book-open"></i> Education</h2>
      <div class="education-timeline">
        
        <div class="edu-item">
          <div class="edu-degree">Master of Computer Applications (MCA)</div>
          <div class="edu-school">KIET Group of Institutions, Ghaziabad</div>
          <div class="edu-details">
            <span>2025 - Present</span>
            <span>CGPA: 6.0 (Till Present)</span>
          </div>
        </div>

        <div class="edu-item">
          <div class="edu-degree">Bachelor of Computer Application (BCA)</div>
          <div class="edu-school">S.D College Of Management Studies, Muzaffarnagar</div>
          <div class="edu-details">
            <span>2022 - 2025</span>
            <span>CGPA: 6.1</span>
          </div>
        </div>

      </div>
    </section>

    <!-- Let's Connect Banner -->
    <section id="contact" class="connect-banner">
      <div class="connect-text">
        <h3>Let's Connect</h3>
        <p>I'm always open to discussing new opportunities, projects or just having a chat about technology.</p>
      </div>
      <div>
        <a href="mailto:anuragdhiman987073@gmail.com" class="btn btn-primary">
          <i class="fa-regular fa-paper-plane"></i> Contact Me
        </a>
      </div>
    </section>

  </main>

  <!-- Footer -->
  <footer>
    <div class="container">
      &copy; 2026 Anurag Dhiman. All Rights Reserved.
    </div>
  </footer>

</body>
</html>
