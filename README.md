<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>IK Technologies - Advanced Site</title>


<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet" />
<style>

  
  /* ========= Base Reset ========= */
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, #141e30, #243b55);
  color: #eee;
  line-height: 1.6;
  scroll-behavior: smooth;
}
a {
  color: #a8c1c6;
  text-decoration: none;
  transition: color 0.3s;
}
a:hover {
  color: #00ffe5;
}

/* ========= Layout Containers ========= */
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px;
}

/* ========= Header ========= */
header {
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  background: rgba(30, 30, 47, 0.85);
  backdrop-filter: saturate(180%) blur(10px);
  transition: box-shadow 0.3s ease;
  z-index: 1000;
}
header.scrolled {
  box-shadow: 0 8px 20px rgba(0, 255, 255, 0.3);
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 0;
}
.logo {
  font-size: 40px;
  font-weight: 700;
  color: #00ffe5;
}
.logo span {
  color: #00d8ff;
}
.nav-links {
  display: flex;
  gap: 35px;
  list-style: none;
}
.nav-links a {
  font-size: 16px;
  font-weight: 600;
}

/* ========= Dropdown Menu ========= */
.dropdown {
  position: absolute;
  top: 110%;
  left: 0;
  background: rgba(30, 30, 47, 0.95);
  border-radius: 8px;
  padding: 10px 20px;
  min-width: 200px;
  opacity: 0;
  visibility: hidden;
  transform: translateY(-10px);
  transition: all 0.3s ease;
  box-shadow: 0 10px 30px rgba(0, 255, 255, 0.4);
  pointer-events: none;
}
.nav-links li:hover .dropdown {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
  pointer-events: auto;
}
.dropdown li {
  margin: 8px 0;
  color: #00d8ff;
  font-weight: 600;
}

/* ========= Hero Section ========= */
.hero {
  padding: 110px 20px 80px;
  background: linear-gradient(40deg, #00d8ff55, #00ffe551);
  text-align: center;
}
.hero h1 {
  font-size: 52px;
  margin-bottom: 15px;
  text-shadow: 0 0 8px #00fff7;
}
.hero p {
  font-size: 22px;
  color: #c0f7ff;
  margin-bottom: 30px;
}
.btn-primary {
  background: #00d8ff;
  color: #111;
  padding: 14px 30px;
  font-size: 18px;
  font-weight: 700;
  border: none;
  border-radius: 50px;
  box-shadow: 0 4px 15px #00d8ffaa;
  cursor: pointer;
  transition: all 0.3s ease;
}
.btn-primary:hover {
  background: #00ffe5;
  box-shadow: 0 6px 25px #00fffbaa;
}

/* ========= Services Section ========= */
#services {
  padding: 80px 0;
}
#services h2 {
  text-align: center;
  font-size: 38px;
  font-weight: 700;
  color: #00d8ff;
  margin-bottom: 50px;
}
.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}
.service-card {
  background: rgba(30, 30, 47, 0.75);
  border-radius: 15px;
  padding: 30px;
  box-shadow: 0 6px 20px #00d8ff44;
  transition: transform 0.3s, box-shadow 0.3s;
  cursor: pointer;
}
.service-card:hover {
  transform: translateY(-15px);
  box-shadow: 0 10px 35px #00fffbaa;
}
.service-card h3 {
  color: #00ffe5;
  font-weight: 700;
  margin-bottom: 15px;
}
.service-card p {
  color: #a4f1ffdd;
  font-weight: 500;
}
.service-dropdown {
  list-style: none;
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease;
  margin-top: 15px;
  padding-left: 18px;
  color: #00fff7dd;
}
.service-dropdown.show {
  max-height: 300px;
}
.service-dropdown li {
  padding: 6px 0;
}

/* ========= About Section ========= */
#about {
  background: rgba(0, 255, 229, 0.1);
  padding: 80px 20px;
  text-align: center;
}
#about h2 {
  font-size: 36px;
  color: #00d8ff;
  margin-bottom: 20px;
}
#about p {
  max-width: 700px;
  margin: auto;
  font-size: 18px;
  color: #c0f7ff;
  line-height: 1.5;
}

/* ========= Contact Section ========= */
#contact {
  padding: 80px 20px;
}
#contact h2 {
  font-size: 36px;
  color: #00d8ff;
  text-align: center;
  margin-bottom: 40px;
}
form {
  max-width: 500px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
input,
textarea {
  padding: 15px;
  font-size: 16px;
  background: rgba(30, 30, 47, 0.8);
  border: none;
  border-radius: 10px;
  color: #c0f7ff;
  transition: background 0.3s ease;
}
input:focus,
textarea:focus {
  background: rgba(0, 255, 229, 0.15);
  outline: none;
}
button[type="submit"] {
  background: #00d8ff;
  color: #111;
  padding: 16px;
  font-size: 18px;
  font-weight: 700;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  box-shadow: 0 4px 15px #00d8ffaa;
  transition: background 0.3s ease;
}
button[type="submit"]:hover {
  background: #00ffe5;
  box-shadow: 0 6px 25px #00fffbaa;
}
.error {
  border: 2px solid #ff3860;
}

/* ========= Popup ========= */
.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.75);
  display: none;
  justify-content: center;
  align-items: center;
  z-index: 2000;
}
.popup.active {
  display: flex;
}
.popup-content {
  background: #141e30;
  padding: 30px 40px;
  border-radius: 12px;
  text-align: center;
  color: #00ffe5;
  font-weight: 700;
  font-size: 22px;
  box-shadow: 0 0 30px #00d8ffbb;
}
.popup-content button {
  margin-top: 25px;
  background: #00d8ff;
  color: #111;
  padding: 12px 28px;
  border: none;
  border-radius: 50px;
  font-weight: 800;
  cursor: pointer;
  box-shadow: 0 4px 15px #00d8ffbb;
  transition: all 0.3s ease;
}
.popup-content button:hover {
  background: #00ffe5;
  box-shadow: 0 6px 25px #00fffbaa;
}

/* ========= Back to Top Button ========= */
#backToTop {
  position: fixed;
  bottom: 40px;
  right: 40px;
  background: #00d8ff;
  color: #111;
  padding: 14px 18px;
  font-size: 22px;
  border-radius: 50%;
  cursor: pointer;
  display: none;
  box-shadow: 0 4px 15px #00d8ffbb;
  transition: background 0.3s ease;
}
#backToTop:hover {
  background: #00ffe5;
}

/* ========= Footer ========= */
.main-footer {
  background-color: #1e1e2f;
  color: white;
  text-align: center;
  padding: 20px 0;
  margin-top: 50px;
}

/* ========= Contact Links ========= */
.contact-container {
  max-width: 600px;
  margin: 40px auto;
  padding: 30px;
  background-color: #00d9ff13;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}
.contact-container h2 {
  color: #0b2137;
  margin-bottom: 20px;
}
.contact-links {
  display: flex;
  flex-direction: column;
  gap: 15px;
  margin-top: 30px;
}
.contact-container a {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 18px;
  background: #141e30;
  color: #c7d0d9;
  padding: 12px 20px;
  border-radius: 10px;
  transition: all 0.3s;
}
.contact-container a:hover {
  box-shadow: 0 0 30px #00d8ffcc;
  transform: scale(1.03);
}
.contact-icon {
  font-size: 22px;
}

/* ========= Responsive ========= */
@media (max-width: 700px) {
  .nav-links {
    display: none;
  }
  nav.active .nav-links {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 65px;
    right: 20px;
    background: rgba(30, 30, 47, 0.95);
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 0 30px #00d8ffcc;
    z-index: 10000;
  }
}


  
</style>
</head>
<body>

<header id="header">
  <nav class="container">
<a href="#hero" class="logo">IK<span>Tech</span></a>
    <ul class="nav-links">
      <li><a href="#hero">Home</a></li>
      <li>
        <a href="#services">Services ▼</a>
        <ul class="dropdown" id="servicesDropdown">
          <li><a href="web desining.html"><span class="count-number" data-target="1">1</span>. Web Desining</a></li>
          <li><a href="web-development.html"><span class="count-number" data-target="2">2</span>. Web Development</a></li>
          <li><a href="markiting.html"><span class="count-number" data-target="3">3</span>. Seo and Markiting</a></li>
        </ul>
      </li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
      <li><a href="#trainings">Trainings</a></li>
    </ul>
  </nav>
</header>

<section class="hero" id="hero">
  <div class="container">
    <h1>IK Technologies</h1>
    <p>Building powerful, beautiful websites for your business</p>
    <a href="#contact" class="btn-primary">Contact Us</a>
  </div>
</section>

<section id="services" class="container">
  <h2>Our Services</h2>
  <div class="services-grid">
    <div class="service-card" tabindex="0" aria-label="Web Design Service">
      <h3>Web Design</h3>
      <p>Modern responsive designs that engage your users.</p>
      
      <li><a href="web desining.html"><span class="count-number" data-target="1">1</span>. Web Desining</a></li>
    </div>
    <div class="service-card" tabindex="0" aria-label="Web Development Service">
      <h3>Web Development</h3>
      <p>Robust and scalable full-stack applications.</p>
      <li><a href="web-development.html"><span class="count-number" data-target="2">2</span>. Web Development</a></li>
    </div>
    <div class="service-card" tabindex="0" aria-label="SEO and Marketing Service">
      <h3>SEO & Marketing</h3>
      <p>Improve your site's visibility and grow your audience.</p>
      <li><a href="markiting.html"><span class="count-number" data-target="3">3</span>. Markiting</a></li>
    </div>
  </div>
</section>

<section id="trainings" class="container" style="padding: 80px 0;">
  <h2 style="text-align: center; margin-bottom: 50px; font-size: 38px; font-weight: 700; color: #00d8ff;">
    Our IT Trainings
  </h2>
  <div class="services-grid">
   <div class="service-card" tabindex="0" aria-label="Angular Training">
  <a href="https://angular.io" target="_blank">
    <div style="text-align: center;">
      <img src="https://angular.io/assets/images/logos/angular/angular.svg" alt="Angular Logo" width="100">
    </div>
  </a>
  <h3>Angular</h3>
  <p>Master modern front-end development with powerful SPA architecture using Angular.</p>
  <ul class="service-dropdown show">
    <li><a href="Angular.html"><span class="count-number" data-target="1">1</span>. Angular</a></li>
  </ul>
</div>
    <div class="service-card" tabindex="0" aria-label="PHP Training">
      <div style="text-align: center;">
  <img src="https://www.php.net/images/logos/php-logo.svg" alt="PHP Logo" width="100">
</div>
      <h3>PHP</h3>
      <p>Learn dynamic web development and backend scripting with real-world PHP projects.</p>
      <ul class="service-dropdown show">
        <li><a href="PHP.html"><span class="count-number" data-target="2">2</span>. PHP(Hypertext Preprocessor)</a></li>
      </ul>
    </div>
    <div class="service-card" tabindex="0" aria-label="TypeScript Training">
      <div style="text-align: center; margin-top: 20px;">
  <img src="https://raw.githubusercontent.com/remojansen/logo.ts/master/ts.png" alt="TypeScript Logo" width="100">
</div>
      <h3>TypeScript</h3>
      <p>Go beyond JavaScript—write robust, scalable, and type-safe applications with TypeScript.</p>
      <ul class="service-dropdown show">
        <li><a href="Typescript.html"><span class="count-number" data-target="3">3</span>. TypeScript</a></li>
      </ul>
    </div>
    <div class="service-card" tabindex="0" aria-label="java script">
      <div style="text-align: center; margin-top: 20px;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" alt="JavaScript Logo" width="100">
</div>
      <h3>JavaScript</h3>
      <p>Learn dynamic web development and backend scripting with real-world JavaScript projects.</p>
      <ul class="service-dropdown show">
        <li><a href="Javascript.html"><span class="count-number" data-target="4">4</span>. JavaScript</a></li>
      </ul>
    </div>
      <div class="service-card" tabindex="0" aria-label="html and css">
        <div style="text-align: center; margin-top: 20px;">
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/61/HTML5_logo_and_wordmark.svg" alt="HTML5 Logo" width="100">
</div>
      <h3>Html and css</h3>
      <p>Learn dynamic web development  with real-world HTML AND CSS projects.</p>
      <ul class="service-dropdown show">
        <li><a href="Html.html"><span class="count-number" data-target="5">5</span>. Html and Css</a></li>
      </ul>
    </div>
      <div class="service-card" tabindex="0" aria-label="My SQL">
        <div style="text-align: center; margin-top: 20px;">
  <img src="https://upload.wikimedia.org/wikipedia/en/d/dd/MySQL_logo.svg" alt="MySQL Logo" width="120">
</div>
      <h3>My SQL</h3>
      <p>Learn dynamic  backend scripting with real-world projects.</p>
      <ul class="service-dropdown show">
        <li><a href="Sql.html"><span class="count-number" data-target="6">6</span>. MySQL</a></li>
      </ul>
    </div>
  </div>
</section>


<section id="about" class="container" style="margin-bottom: 60px;">
  <h2>About Us</h2>
  <p>At IK Technologies, we don’t just build digital products — we engineer experiences that drive growth and spark innovation.
    Our elite team of developers and designers transforms bold ideas into powerful, high-performance solutions.
    From sleek websites to complex platforms, every project is a blend of strategy, creativity, and precision.
    We thrive on challenges, push boundaries, and deliver with unmatched speed and quality.
    Our mission is simple: to empower businesses through technology that captivates and converts.
    Partner with IK Technologies — where vision meets execution, and excellence is non-negotiable.</p>
</section>




<!-- Footer Section -->
<footer style="background-color: #0b2137; color: #ffffff; padding: 50px 20px 30px 20px; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
  <div class="container" style="max-width: 1200px; margin: auto; display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 30px;">


    <button id="backToTop" aria-label="Back to top" 
  style="position: fixed; bottom: 25px; right: 30px; box-shadow: 0 4px 15px #00d8ffaa;color: rgb(0, 0, 0); border: none; border-radius: 80%; width: 45px; height: 40px; font-size: 20px; cursor: pointer;  z-index: 2000;">
  &#8679;
</button>
    <!-- About -->
    <div>
      <a href="#hero" class="logo">IK<span>Tech</span></a>
      <h3 style="margin-bottom: 15px;">About IK Technologies</h3>
      <p style="font-size: 15px; color: #ccc; line-height: 1.6;">
        IK Technologies is a team of passionate web developers and IT professionals delivering modern, secure, and responsive websites and software solutions. We turn your vision into powerful digital experiences.
      </p>
    </div>

    <!-- Services -->
    <div>
      <h3 style="margin-bottom: 15px;">Services</h3>
      <ul style="list-style: none; padding: 0; line-height: 1.8; font-size: 15px;">
        <li><a href="web-development.html" style="color: #ccc; text-decoration: none;">Web Development</a></li>
        <li><a href="markiting.html" style="color: #ccc; text-decoration: none;">SEO & Digital Marketing</a></li>
        <li><a href="web-development.html" style="color: #ccc; text-decoration: none;">E-commerce Solutions</a></li>
        <li><a href="web desining.html" style="color: #ccc; text-decoration: none;">Web Desining</a></li>
      </ul>
    </div>

    <!-- Technologies -->
    <div>
      <h3 style="margin-bottom: 15px;">Technologies</h3>
      <ul style="list-style: none; padding: 0; line-height: 1.8; font-size: 15px;">
        <li>HTML, CSS, JavaScript</li>
        <li>Angular, React, Vue</li>
        <li>Node.js, PHP, Laravel</li>
        <li>MySQL, Firebase, MongoDB</li>
      </ul>
    </div>

    <!-- Contact -->
    <div>
      <h3 id="contact" style="margin: -60px; font-size: 25px;">Contact Us</h3>
    <p style="margin: 5px; font-size: 15px;">📞+92 327 0588057</p>
      <p style="margin: 0; font-size: 15px;">✉️ khizerirfan11@gmail.com </p>
      <p style="margin: 0; font-size: 15px;">📍 Lahore, Pakistan</p>
      
      <!-- Social Icons -->
      <div style="margin-top: 15px; display: flex; gap: 15px;">
        <a href="https://wa.me/03270588057" target="_blank" style="color: #25D366; font-size: 20px;" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
        <a href="https://www.linkedin.com/in/m-khizer-irfan-8a921033b/" target="_blank" style="color: #0A66C2; font-size: 20px;" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
        <a href="https://www.facebook.com/share/1AmK3g389N/?mibextid=wwXIfr"  target="_blank" style="color: #1877F2; font-size: 20px;" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
        <a href="khizerirfan11@gmail.com" style="color: #ffffff; font-size: 20px;" aria-label="Email"><i class="fas fa-envelope"></i></a>
      </div>
    </div>
  </div>

  <!-- Bottom Line -->
  <div style="text-align: center; border-top: 1px solid #eae4e4; margin-top: 30px; padding-top: 20px; font-size: 14px; color: #f5efef;">
    &copy; 2025 IK Technologies. All Rights Reserved. Built with ❤️ by IK Team.
  </div>
</footer>

<script>
  // Sticky header shadow on scroll
  const header = document.getElementById('header');
  window.addEventListener('scroll', () => {
    if(window.scrollY > 40) {
      header.classList.add('scrolled');
    } else {
      header.classList.remove('scrolled');
    }
  });

  // Dropdown counting animation
  const dropdown = document.getElementById('servicesDropdown');
  const countNumbers = dropdown.querySelectorAll('.count-number');

  function animateCount(el, target) {
    let count = 0;
    const speed = 40;
    const step = () => {
      if(count < target) {
        count++;
        el.textContent = count;
        setTimeout(step, speed);
      } else {
        el.textContent = target;
      }
    };
    step();
  }

  // Animate counts when dropdown is shown (on hover)
  let dropdownVisible = false;
  document.querySelector('nav').addEventListener('mouseenter', e => {
    if(e.target.closest('li')?.querySelector('.dropdown')) {
      if(!dropdownVisible) {
        countNumbers.forEach(el => {
          animateCount(el, parseInt(el.getAttribute('data-target')));
        });
        dropdownVisible = true;
      }
    }
  });

  // Back to top button logic
  const backToTop = document.getElementById('backToTop');
  window.addEventListener('scroll', () => {
    if(window.scrollY > 300) {
      backToTop.style.display = 'block';
    } else {
      backToTop.style.display = 'none';
    }
  });
  backToTop.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });

  // Form validation and popup logic
  const form = document.getElementById('contactForm');
  const popup = document.getElementById('popup');
  const closePopupBtn = document.getElementById('closePopup');

  form.addEventListener('submit', e => {
    e.preventDefault();

    // Simple validation
    let valid = true;
    ['name', 'email', 'message'].forEach(id => {
      const field = document.getElementById(id);
      if(!field.value.trim()) {
        field.classList.add('error');
        valid = false;
      } else {
        field.classList.remove('error');
      }
    });

    // Email regex
    const emailField = document.getElementById('email');
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if(!emailRegex.test(emailField.value.trim())) {
      emailField.classList.add('error');
      valid = false;
    } else {
      emailField.classList.remove('error');
    }

    if(valid) {
      popup.classList.add('active');
      form.reset();
    }
  });

  closePopupBtn.addEventListener('click', () => {
    popup.classList.remove('active');
  });

  // Contact Us button scroll to form
  document.getElementById('contactBtn').addEventListener('click', () => {
    document.getElementById('contact').scrollIntoView({behavior: 'smooth'});
  });
</script>

</body>
</html>
