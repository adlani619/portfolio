<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mohamed Adlani - Web Developer Portfolio</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: #333;
      overflow-x: hidden;
    }

    /* Navbar */
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(10px);
      padding: 20px 0;
      box-shadow: 0 2px 20px rgba(0,0,0,0.1);
      z-index: 1000;
      transition: all 0.3s ease;
    }

    nav.scrolled {
      padding: 15px 0;
      background: rgba(255, 255, 255, 0.98);
    }

    nav ul {
      display: flex;
      justify-content: center;
      list-style: none;
      gap: 40px;
    }

    nav a {
      text-decoration: none;
      color: #667eea;
      font-weight: 600;
      transition: color 0.3s;
      position: relative;
    }

    nav a::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 0;
      width: 0;
      height: 2px;
      background: #667eea;
      transition: width 0.3s;
    }

    nav a:hover::after {
      width: 100%;
    }

    /* Hero Section */
    header {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: white;
      padding: 80px 20px 40px;
      position: relative;
    }

    .hero-content {
      animation: fadeInUp 1s ease;
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

    .hero-content h1 {
      font-size: 3.5em;
      margin-bottom: 20px;
      text-shadow: 2px 2px 10px rgba(0,0,0,0.3);
    }

    .hero-content p {
      font-size: 1.3em;
      margin-bottom: 30px;
      opacity: 0.95;
    }

    .btn {
      display: inline-block;
      padding: 15px 40px;
      background: white;
      color: #667eea;
      text-decoration: none;
      border-radius: 50px;
      font-weight: 600;
      transition: all 0.3s;
      box-shadow: 0 5px 20px rgba(0,0,0,0.2);
    }

    .btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 30px rgba(0,0,0,0.3);
    }

    /* Section Styles */
    section {
      max-width: 1200px;
      margin: 60px auto;
      padding: 60px 40px;
      background: white;
      border-radius: 20px;
      box-shadow: 0 10px 40px rgba(0,0,0,0.1);
      animation: fadeIn 0.8s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    section h2 {
      font-size: 2.5em;
      margin-bottom: 40px;
      color: #667eea;
      text-align: center;
      position: relative;
      padding-bottom: 15px;
    }

    section h2::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 4px;
      background: linear-gradient(90deg, #667eea, #764ba2);
      border-radius: 2px;
    }

    /* About Section */
    .about-content {
      display: flex;
      align-items: center;
      gap: 50px;
      flex-wrap: wrap;
    }

    .profile-img {
      width: 250px;
      height: 250px;
      border-radius: 50%;
      background: linear-gradient(135deg, #667eea, #764ba2);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 6em;
      color: white;
      box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
    }

    .about-text {
      flex: 1;
      min-width: 300px;
    }

    .about-text p {
      line-height: 1.8;
      font-size: 1.1em;
      color: #555;
    }

    /* Skills Section */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 30px;
      margin-top: 40px;
    }

    .skill-card {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      color: white;
      transition: transform 0.3s, box-shadow 0.3s;
      cursor: pointer;
    }

    .skill-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 40px rgba(102, 126, 234, 0.4);
    }

    .skill-card h3 {
      font-size: 1.3em;
      margin-bottom: 10px;
    }

    /* Projects Section */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 30px;
      margin-top: 40px;
    }

    .project-card {
      background: #f8f9fa;
      border-radius: 15px;
      overflow: hidden;
      transition: transform 0.3s, box-shadow 0.3s;
      cursor: pointer;
    }

    .project-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 40px rgba(0,0,0,0.15);
    }

    .project-header {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 30px;
      color: white;
    }

    .project-header h3 {
      font-size: 1.5em;
      margin-bottom: 10px;
    }

    .project-body {
      padding: 25px;
    }

    .project-body p {
      color: #666;
      line-height: 1.6;
    }

    .project-tags {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 15px;
    }

    .tag {
      background: #667eea;
      color: white;
      padding: 5px 15px;
      border-radius: 20px;
      font-size: 0.85em;
    }

    /* Contact Section */
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
      margin-top: 40px;
    }

    .contact-card {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      color: white;
      transition: transform 0.3s;
    }

    .contact-card:hover {
      transform: scale(1.05);
    }

    .contact-icon {
      font-size: 3em;
      margin-bottom: 15px;
    }

    .contact-card h3 {
      margin-bottom: 10px;
    }

    .contact-card a {
      color: white;
      text-decoration: none;
      word-break: break-all;
    }

    /* Footer */
    footer {
      background: rgba(255, 255, 255, 0.95);
      text-align: center;
      padding: 30px;
      margin-top: 60px;
      color: #667eea;
      font-weight: 600;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .hero-content h1 {
        font-size: 2.5em;
      }
      
      nav ul {
        gap: 20px;
        flex-wrap: wrap;
      }

      .about-content {
        flex-direction: column;
        text-align: center;
      }
      
      section {
        padding: 40px 20px;
        margin: 30px 20px;
      }
    }

    /* Scroll animations */
    .fade-in {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.6s, transform 0.6s;
    }

    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>
  <nav id="navbar">
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <header id="home">
    <div class="hero-content">
      <h1>Mohamed Adlani</h1>
      <p>Web Developer specialized in building modern and responsive applications</p>
      <p style="font-size: 1.1em; margin-bottom: 40px;">HTML / CSS / JavaScript / React / Vue / Django</p>
      <a href="#projects" class="btn">Explore My Work</a>
    </div>
  </header>

  <section id="about" class="fade-in">
    <h2>About Mohamed Adlani</h2>
    <div class="about-content">
      <div class="profile-img">👨‍💻</div>
      <div class="about-text">
        <p>
          Hello! I'm Mohamed Adlani, a passionate web developer focused on creating distinctive digital experiences. I specialize in building modern user interfaces and efficient web applications using the latest technologies.
        </p>
        <p style="margin-top: 20px;">
          I believe that good development combines attractive design, high performance, and excellent user experience. I'm always eager to learn new technologies and improve my skills to deliver innovative solutions.
        </p>
      </div>
    </div>
  </section>

  <section id="skills" class="fade-in">
    <h2>Technical Skills</h2>
    <div class="skills-grid">
      <div class="skill-card">
        <h3>HTML5</h3>
        <p>Advanced</p>
      </div>
      <div class="skill-card">
        <h3>CSS3</h3>
        <p>Advanced</p>
      </div>
      <div class="skill-card">
        <h3>JavaScript</h3>
        <p>Advanced</p>
      </div>
      <div class="skill-card">
        <h3>React.js</h3>
        <p>Intermediate</p>
      </div>
      <div class="skill-card">
        <h3>Vue.js</h3>
        <p>Intermediate</p>
      </div>
      <div class="skill-card">
        <h3>Bootstrap</h3>
        <p>Advanced</p>
      </div>
      <div class="skill-card">
        <h3>Tailwind</h3>
        <p>Intermediate</p>
      </div>
      <div class="skill-card">
        <h3>Django</h3>
        <p>Basic</p>
      </div>
    </div>
  </section>

  <section id="projects" class="fade-in">
    <h2>My Projects</h2>
    <div class="projects-grid">
      <div class="project-card">
        <div class="project-header">
          <h3>Personal Portfolio Website</h3>
        </div>
        <div class="project-body">
          <p>A professional portfolio website showcasing skills, projects, and contact information with responsive and modern design.</p>
          <div class="project-tags">
            <span class="tag">HTML</span>
            <span class="tag">CSS</span>
            <span class="tag">JavaScript</span>
          </div>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <h3>Task Manager App</h3>
        </div>
        <div class="project-body">
          <p>A web application for managing tasks that allows users to create, update, and delete tasks with an easy-to-use interface.</p>
          <div class="project-tags">
            <span class="tag">React.js</span>
            <span class="tag">Hooks</span>
            <span class="tag">CSS</span>
          </div>
        </div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <h3>Contact Manager</h3>
        </div>
        <div class="project-body">
          <p>A CRUD application for managing contacts built with Vue.js demonstrating mastery of components and API integration.</p>
          <div class="project-tags">
            <span class="tag">Vue.js</span>
            <span class="tag">Components</span>
            <span class="tag">API</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="contact" class="fade-in">
    <h2>Get In Touch</h2>
    <div class="contact-grid">
      <div class="contact-card">
        <div class="contact-icon">📧</div>
        <h3>Email</h3>
        <a href="mailto:Adlani-moh@hotmail.fr">Adlani-moh@hotmail.fr</a>
      </div>
      <div class="contact-card">
        <div class="contact-icon">📱</div>
        <h3>WhatsApp</h3>
        <a href="https://wa.me/212654321110">+212 654 321 110</a>
      </div>
      <div class="contact-card">
        <div class="contact-icon">💼</div>
        <h3>GitHub</h3>
        <a href="#" onclick="return false;">github.com/adlani619</a>
      </div>
    </div>
  </section>

  <footer>
    <p>© 2025 Mohamed Adlani - All Rights Reserved</p>
  </footer>

  <script>
    // Navbar scroll effect
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });

    // Smooth scrolling
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
          });
        }
      });
    });

    // Fade in animation on scroll
    const observerOptions = {
      threshold: 0.1,
      rootMargin: '0px 0px -100px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, observerOptions);

    document.querySelectorAll('.fade-in').forEach(el => {
      observer.observe(el);
    });
  </script>
</body>
</html>
