<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>ARXH Graphics</title>
  <meta
    name="description"
    content="Independent graphic designer crafting identities, campaigns, digital experiences and visual systems."
  />

  <style>
    @import url('https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Manrope:wght@400;500;600;700;800&family=Space+Grotesk:wght@400;500;600;700&display=swap');

    :root {
      --black: #0b0b0b;
      --white: #f5f3ed;
      --lime: #c8ff00;
      --gray: #a3a39d;
      --line: rgba(245, 243, 237, 0.18);
      --card: #151515;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: var(--black);
      color: var(--white);
      font-family: "Manrope", sans-serif;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      width: 100%;
      display: block;
    }

    /* ---------------- NAV ---------------- */

    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 24px 5vw;
      display: flex;
      justify-content: space-between;
      align-items: center;
      z-index: 100;
      mix-blend-mode: difference;
      color: white;
    }

    .logo {
      font-family: "Space Grotesk", sans-serif;
      font-weight: 700;
      font-size: 20px;
      letter-spacing: -1px;
    }

    .nav-links {
      display: flex;
      gap: 30px;
      font-family: "DM Mono", monospace;
      font-size: 11px;
      text-transform: uppercase;
    }

    .nav-links a {
      position: relative;
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -5px;
      width: 0;
      height: 1px;
      background: var(--lime);
      transition: width 0.3s ease;
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    /* ---------------- HERO ---------------- */

    .hero {
      min-height: 100vh;
      padding: 150px 5vw 50px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      position: relative;
      overflow: hidden;
    }

    .hero-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      font-family: "DM Mono", monospace;
      font-size: 11px;
      color: var(--gray);
      text-transform: uppercase;
    }

    .status {
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      background: var(--lime);
      border-radius: 50%;
      box-shadow: 0 0 15px var(--lime);
    }

    .hero-title {
      position: relative;
      z-index: 2;
      margin-top: auto;
    }

    .hero-title h1 {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(70px, 13vw, 190px);
      line-height: 0.82;
      letter-spacing: -0.08em;
      text-transform: uppercase;
      font-weight: 700;
    }

    .hero-title h1 span {
      color: var(--lime);
    }

    .hero-bottom {
      margin-top: 50px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
      align-items: end;
    }

    .hero-description {
      max-width: 500px;
      font-size: 18px;
      line-height: 1.5;
      color: #d0d0ca;
    }

    .scroll-text {
      justify-self: end;
      font-family: "DM Mono", monospace;
      font-size: 11px;
      color: var(--gray);
      text-transform: uppercase;
    }

    /* ---------------- DECORATION ---------------- */

    .orb {
      position: absolute;
      width: 400px;
      height: 400px;
      border-radius: 50%;
      right: 5%;
      top: 25%;
      background:
        radial-gradient(circle at 30% 30%, #eaff91, var(--lime) 25%, #789900 55%, #111 72%);
      filter: blur(0.5px);
      opacity: 0.75;
      animation: float 7s ease-in-out infinite;
    }

    .orb::after {
      content: "";
      position: absolute;
      inset: 10%;
      border: 1px solid rgba(255,255,255,.3);
      border-radius: 50%;
      transform: rotate(45deg);
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0) rotate(0deg);
      }
      50% {
        transform: translateY(-25px) rotate(8deg);
      }
    }

    /* ---------------- MARQUEE ---------------- */

    .marquee {
      overflow: hidden;
      border-top: 1px solid var(--line);
      border-bottom: 1px solid var(--line);
      padding: 18px 0;
      white-space: nowrap;
      background: var(--lime);
      color: var(--black);
    }

    .marquee-track {
      display: inline-block;
      animation: marquee 18s linear infinite;
      font-family: "Space Grotesk", sans-serif;
      font-weight: 700;
      font-size: 24px;
      text-transform: uppercase;
    }

    .marquee-track span {
      margin: 0 25px;
    }

    @keyframes marquee {
      from {
        transform: translateX(0);
      }
      to {
        transform: translateX(-50%);
      }
    }

    /* ---------------- SECTION ---------------- */

    section {
      padding: 140px 5vw;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 70px;
    }

    .section-number {
      font-family: "DM Mono", monospace;
      font-size: 11px;
      color: var(--lime);
    }

    .section-title {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(45px, 7vw, 90px);
      line-height: 0.9;
      letter-spacing: -0.06em;
      text-transform: uppercase;
      max-width: 800px;
    }

    /* ---------------- WORK ---------------- */

    .projects {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 25px;
    }

    .project {
      position: relative;
      overflow: hidden;
      background: var(--card);
      cursor: pointer;
    }

    .project:nth-child(1) {
      grid-column: span 7;
    }

    .project:nth-child(2) {
      grid-column: span 5;
      margin-top: 100px;
    }

    .project:nth-child(3) {
      grid-column: span 5;
      margin-top: 30px;
    }

    .project:nth-child(4) {
      grid-column: span 7;
    }

    .project-image {
      height: 560px;
      overflow: hidden;
    }

    .project:nth-child(2) .project-image,
    .project:nth-child(3) .project-image {
      height: 450px;
    }

    .project-image img {
      height: 100%;
      object-fit: cover;
      transition: transform 0.7s cubic-bezier(.2,.8,.2,1);
      filter: grayscale(20%);
    }

    .project:hover img {
      transform: scale(1.06);
    }

    .project-info {
      padding: 20px 0 5px;
      display: flex;
      justify-content: space-between;
      border-top: 1px solid var(--line);
      margin-top: 12px;
    }

    .project-name {
      font-family: "Space Grotesk", sans-serif;
      font-size: 20px;
      text-transform: uppercase;
    }

    .project-type {
      font-family: "DM Mono", monospace;
      font-size: 10px;
      color: var(--gray);
      text-transform: uppercase;
    }

    /* ---------------- ABOUT ---------------- */

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10vw;
      align-items: center;
    }

    .about-image {
      position: relative;
    }

    .about-image img {
      aspect-ratio: 4 / 5;
      object-fit: cover;
      filter: grayscale(100%);
    }

    .about-image::before {
      content: "";
      position: absolute;
      width: 80%;
      height: 80%;
      background: var(--lime);
      top: -20px;
      left: -20px;
      z-index: -1;
    }

    .about-text h3 {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(30px, 4vw, 55px);
      line-height: 1;
      letter-spacing: -0.05em;
      margin-bottom: 35px;
    }

    .about-text p {
      color: #aaa9a3;
      font-size: 17px;
      line-height: 1.7;
      margin-bottom: 25px;
    }

    .skills {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 35px;
    }

    .skill {
      border: 1px solid var(--line);
      padding: 10px 15px;
      font-family: "DM Mono", monospace;
      font-size: 10px;
      text-transform: uppercase;
    }

    /* ---------------- SERVICES ---------------- */

    .services {
      border-top: 1px solid var(--line);
    }

    .service {
      display: grid;
      grid-template-columns: 80px 1fr 100px;
      gap: 30px;
      padding: 35px 0;
      border-bottom: 1px solid var(--line);
      align-items: center;
      transition: all 0.3s ease;
    }

    .service:hover {
      padding-left: 20px;
      background: rgba(200,255,0,0.03);
    }

    .service-number {
      color: var(--lime);
      font-family: "DM Mono", monospace;
    }

    .service-name {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(25px, 4vw, 50px);
      text-transform: uppercase;
      letter-spacing: -0.04em;
    }

    .service-arrow {
      text-align: right;
      font-size: 25px;
      color: var(--lime);
    }

    /* ---------------- CONTACT ---------------- */

    .contact {
      min-height: 80vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .contact h2 {
      font-family: "Space Grotesk", sans-serif;
      font-size: clamp(55px, 11vw, 150px);
      line-height: 0.82;
      letter-spacing: -0.08em;
      text-transform: uppercase;
      margin-bottom: 60px;
    }

    .contact h2 span {
      color: var(--lime);
    }

    .contact-link {
      display: inline-block;
      width: fit-content;
      font-family: "DM Mono", monospace;
      font-size: 13px;
      text-transform: uppercase;
      border-bottom: 1px solid var(--lime);
      padding-bottom: 8px;
      color: var(--white);
      transition: color .3s;
    }

    .contact-link:hover {
      color: var(--lime);
    }

    /* ---------------- FOOTER ---------------- */

    footer {
      border-top: 1px solid var(--line);
      padding: 25px 5vw;
      display: flex;
      justify-content: space-between;
      font-family: "DM Mono", monospace;
      font-size: 10px;
      text-transform: uppercase;
      color: var(--gray);
    }

    /* ---------------- RESPONSIVE ---------------- */

    @media (max-width: 800px) {

      nav {
        padding: 20px;
      }

      .nav-links {
        gap: 12px;
        font-size: 9px;
      }

      .hero {
        padding: 120px 20px 35px;
      }

      .hero-top {
        font-size: 9px;
      }

      .orb {
        width: 220px;
        height: 220px;
        right: -30px;
        top: 28%;
        opacity: .5;
      }

      .hero-title h1 {
        font-size: 19vw;
      }

      .hero-bottom {
        grid-template-columns: 1fr;
      }

      .scroll-text {
        justify-self: start;
      }

      section {
        padding: 90px 20px;
      }

      .section-header {
        margin-bottom: 45px;
      }

      .projects {
        display: block;
      }

      .project {
        margin: 0 0 60px !important;
      }

      .project-image,
      .project:nth-child(2) .project-image,
      .project:nth-child(3) .project-image {
        height: 400px;
      }

      .about-grid {
        grid-template-columns: 1fr;
        gap: 60px;
      }

      .service {
        grid-template-columns: 35px 1fr 30px;
        gap: 10px;
      }

      .service-number {
        font-size: 10px;
      }

      footer {
        padding: 20px;
        gap: 15px;
        flex-direction: column;
      }
    }
  </style>
</head>

<body>

  <!-- NAVIGATION -->
  <nav>
    <a href="#" class="logo">ARLO®</a>

    <div class="nav-links">
      <a href="#work">Work</a>
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <a href="#contact">Contact</a>
    </div>
  </nav>

  <!-- HERO -->
  <header class="hero">

    <div class="hero-top">
      <div>Independent<br>Graphic Designer</div>

      <div class="status">
        <span class="status-dot"></span>
        Available for projects
      </div>
    </div>

    <div class="orb"></div>

    <div class="hero-title">
      <h1>
        Visual<br>
        <span>Noise.</span>
      </h1>
    </div>

    <div class="hero-bottom">
      <p class="hero-description">
        I create visual identities, campaigns and digital experiences
        for brands that refuse to look ordinary.
      </p>

      <div class="scroll-text">
        ↓ Scroll to explore
      </div>
    </div>

  </header>

  <!-- MARQUEE -->
  <div class="marquee">
    <div class="marquee-track">
      <span>Brand Identity</span> ✦
      <span>Art Direction</span> ✦
      <span>Digital Design</span> ✦
      <span>Creative Direction</span> ✦
      <span>Brand Identity</span> ✦
      <span>Art Direction</span> ✦
      <span>Digital Design</span> ✦
      <span>Creative Direction</span> ✦
    </div>
  </div>

  <!-- WORK -->
  <section id="work">

    <div class="section-header">
      <span class="section-number">01 / Selected Work</span>

      <h2 class="section-title">
        Things<br>I've made.
      </h2>
    </div>

    <div class="projects">

      <article class="project">
        <div class="project-image">
          <img
            src="https://images.unsplash.com/photo-1561070791-2526d30994b5?auto=format&fit=crop&w=1600&q=85"
            alt="Brand identity project"
          >
        </div>

        <div class="project-info">
          <span class="project-name">Noir Objects</span>
          <span class="project-type">Identity / 2026</span>
        </div>
      </article>

      <article class="project">
        <div class="project-image">
          <img
            src="https://images.unsplash.com/photo-1558655146-9f40138edfeb?auto=format&fit=crop&w=1200&q=85"
            alt="Editorial design project"
          >
        </div>

        <div class="project-info">
          <span class="project-name">Forma</span>
          <span class="project-type">Editorial / 2026</span>
        </div>
      </article>

      <article class="project">
        <div class="project-image">
          <img
            src="https://images.unsplash.com/photo-1545235617-9465d2a55698?auto=format&fit=crop&w=1200&q=85"
            alt="Creative campaign project"
          >
        </div>

        <div class="project-info">
          <span class="project-name">After Dark</span>
          <span class="project-type">Campaign / 2025</span>
        </div>
      </article>

      <article class="project">
        <div class="project-image">
          <img
            src="https://images.unsplash.com/photo-1561214115-f2f134cc4912?auto=format&fit=crop&w=1600&q=85"
            alt="Art direction project"
          >
        </div>

        <div class="project-info">
          <span class="project-name">Mono Studio</span>
          <span class="project-type">Art Direction / 2025</span>
        </div>
      </article>

    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">

    <div class="section-header">
      <span class="section-number">02 / About</span>
    </div>

    <div class="about-grid">

      <div class="about-image">
        <img
          src="https://images.unsplash.com/photo-1551836022-d5d88e9218df?auto=format&fit=crop&w=1000&q=85"
          alt="Designer workspace"
        >
      </div>

      <div class="about-text">

        <h3>
          Design should make
          people stop scrolling.
        </h3>

        <p>
          I'm Arlo, an independent graphic designer and visual
          art director working across branding, digital design,
          campaigns and culture.
        </p>

        <p>
          My approach is simple: combine strong ideas with
          obsessive attention to typography, composition,
          color and detail.
        </p>

        <div class="skills">
          <span class="skill">Branding</span>
          <span class="skill">Typography</span>
          <span class="skill">Art Direction</span>
          <span class="skill">UI / UX</span>
          <span class="skill">Campaigns</span>
          <span class="skill">Motion</span>
        </div>

      </div>

    </div>
  </section>

  <!-- SERVICES -->
  <section id="services">

    <div class="section-header">
      <span class="section-number">03 / Services</span>

      <h2 class="section-title">
        What I<br>do.
      </h2>
    </div>

    <div class="services">

      <div class="service">
        <span class="service-number">01</span>
        <span class="service-name">Brand Identity</span>
        <span class="service-arrow">↗</span>
      </div>

      <div class="service">
        <span class="service-number">02</span>
        <span class="service-name">Art Direction</span>
        <span class="service-arrow">↗</span>
      </div>

      <div class="service">
        <span class="service-number">03</span>
        <span class="service-name">Digital Design</span>
        <span class="service-arrow">↗</span>
      </div>

      <div class="service">
        <span class="service-number">04</span>
        <span class="service-name">Campaign Design</span>
        <span class="service-arrow">↗</span>
      </div>

      <div class="service">
        <span class="service-number">05</span>
        <span class="service-name">Creative Direction</span>
        <span class="service-arrow">↗</span>
      </div>

    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="contact">

    <div class="section-number">04 / Let's work together</div>

    <h2>
      Have an<br>
      <span>idea?</span>
    </h2>

    <a
      class="contact-link"
      href="mailto:hello@yourname.com"
    >
      hello@yourname.com ↗
    </a>

  </section>

  <!-- FOOTER -->
  <footer>
    <span>© 2026 Arlo Studio</span>
    <span>Designed with intention.</span>
    <span>India / Worldwide</span>
  </footer>

  <!-- SMALL INTERACTION -->
  <script>

    // Change navigation color while scrolling
    const nav = document.querySelector("nav");

    window.addEventListener("scroll", () => {
      if (window.scrollY > 80) {
        nav.style.opacity = "0.85";
      } else {
        nav.style.opacity = "1";
      }
    });

    // Project hover cursor effect
    document.querySelectorAll(".project").forEach(project => {

      project.addEventListener("mouseenter", () => {
        project.style.transform = "translateY(-5px)";
        project.style.transition = "transform .4s ease";
      });

      project.addEventListener("mouseleave", () => {
        project.style.transform = "translateY(0)";
      });

    });

  </script>

</body>
</html>
