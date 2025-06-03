<!DOCTYPE html>
<html lang="en" >
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Premium OS Landing Page</title>
  <style>
    /* Reset and base */
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #e0f0ff, #c1e3fe);
      color: #1b1b1b;
      overflow-x: hidden;
      scroll-behavior: smooth;
      position: relative;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      background-attachment: fixed;
    }
    a {
      color: #3a4fe8;
      text-decoration: none;
      transition: color 0.3s ease;
      cursor: pointer;
      position: relative;
    }
    a:hover,
    a:focus {
      color: #2a38b5;
      outline: none;
      text-shadow: 0 0 8px #2a38b5cc;
    }
    /* Container */
    .container {
      max-width: 1100px;
      margin: auto;
      padding: 0 1rem;
      position: relative;
      z-index: 1;
    }

    /* Navbar */
    nav.navbar {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(255 255 255 / 0.95);
      backdrop-filter: saturate(180%) blur(15px);
      box-shadow: 0 4px 25px rgba(0,0,0,0.15);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      z-index: 9999;
      transition: background-color 0.3s ease, box-shadow 0.3s ease;
      font-weight: 600;
      letter-spacing: 0.05em;
      font-size: 1rem;
      font-family: 'Poppins', sans-serif;
      user-select: none;
      border-radius: 0 0 16px 16px;
    }
    nav.navbar.scrolled {
      background-color: rgba(240, 243, 255,0.98);
      box-shadow: 0 6px 36px rgba(58,79,232,0.55);
      backdrop-filter: saturate(250%) blur(18px);
    }
    nav .logo {
      font-weight: 900;
      font-size: 1.9rem;
      color: #3a4fe8;
      cursor: pointer;
      transition: transform 0.3s ease, color 0.3s ease;
      letter-spacing: 0.18em;
      font-family: 'Fredoka One', cursive;
      user-select:none;
      text-shadow: 0 0 8px #3a4fe8a1;
    }
    nav .logo:hover {
      transform: scale(1.18) rotate(-4deg);
      color: #2a38b5;
      text-shadow: 0 0 14px #2a38b5cc;
    }
    
    nav ul.nav-menu {
      list-style: none;
      display: flex;
      gap: 2.8rem;
      margin: 0;
      padding: 0;
      align-items: center;
      user-select:none;
    }
    nav ul.nav-menu > li {
      position: relative;
    }
    nav ul.nav-menu > li > a {
      color: #5566ee;
      font-weight: 600;
      padding: 0.45rem 0;
      display: inline-block;
      user-select: none;
      transition: color 0.35s ease, transform 0.25s ease, text-shadow 0.35s ease;
      border-bottom: 2px solid transparent;
      border-radius: 6px;
    }
    nav ul.nav-menu > li > a:hover,
    nav ul.nav-menu > li > a:focus {
      color: #2a38b5;
      border-bottom: 2px solid #2a38b5;
      outline: none;
      transform: translateY(-2px);
      text-shadow: 0 0 10px #2a38b5cc;
    }

    /* Dropdown */
    nav ul.nav-menu > li.dropdown > a::after {
      content: " ▼";
      font-size: 0.75rem;
      color: #2a38b5;
      margin-left: 0.3rem;
      transition: transform 0.3s ease;
      display:inline-block;
      transform-origin: center;
    }
    nav ul.nav-menu > li.dropdown:hover > a::after,
    nav ul.nav-menu > li.dropdown:focus-within > a::after {
      transform: translateY(3px);
      color: #3a4fe8;
      text-shadow: 0 0 14px #3a4fe8cc;
    }
    nav ul.nav-menu > li.dropdown:hover > ul.dropdown-menu,
    nav ul.nav-menu > li.dropdown:focus-within > ul.dropdown-menu {
      opacity: 1;
      visibility: visible;
      transform: translateY(0);
      pointer-events: auto;
    }
    ul.dropdown-menu {
      position: absolute;
      top: 2.8rem;
      left: 0;
      background: #edf0ffdd;
      padding: 0.6rem 0;
      border-radius: 22px;
      box-shadow: 0 14px 40px rgba(58,79,232,0.4);
      list-style: none;
      min-width: 180px;
      opacity: 0;
      visibility: hidden;
      transform: translateY(12px);
      transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
      pointer-events: none;
      z-index: 10000;
      font-weight: 600;
      font-family: 'Poppins', sans-serif;
    }
    ul.dropdown-menu li {
      padding: 0.5rem 2.2rem;
      cursor:pointer;
      user-select:none;
      transition: background-color 0.3s ease;
      border-radius: 14px;
    }
    ul.dropdown-menu li a {
      color: #2a37d8;
      font-weight: 600;
      font-size: 1rem;
      display: block;
      text-decoration: none;
      user-select: none;
      transition: color 0.35s ease;
      border-radius: 14px;
      padding: 0.45rem 0;
      text-shadow: 0 0 5px rgba(58,79,232,0.4);
    }
    ul.dropdown-menu li:hover,
    ul.dropdown-menu li:focus-within {
      background-color: #3a4fe832;
      outline: none;
      box-shadow: 0 0 18px #3a4fe8a8 inset;
    }
    ul.dropdown-menu li a:hover,
    ul.dropdown-menu li a:focus {
      color: #2c3bad;
      outline: none;
      text-shadow: 0 0 12px #2c3badcc;
    }

    /* Hero */
    header.hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 85vh;
      text-align: center;
      padding: 7rem 2rem 4rem 2rem; /* navbar space */
      position: relative;
      z-index: 1;
      color: #4b4b5c;
      user-select:none;
      filter: drop-shadow(0 0 10px rgba(58,79,232,0.9));
      animation: fadeInUp 1.2s ease forwards;
      background: radial-gradient(circle at center, #dae6ff55 0%, transparent 70%);
      border-radius: 30px;
      margin: 0 1.5rem;
    }
    header.hero h1 {
      font-size: 4.6rem;
      margin-bottom: 1rem;
      font-weight: 900;
      letter-spacing: 0.14em;
      font-family: 'Fredoka One', cursive;
      text-shadow: 0 0 20px #7a78ffcc;
      transform: translateY(-12px);
      animation: slideInDown 1s ease forwards;
      color: #3a4fe8;
    }
    header.hero p {
      font-size: 1.55rem;
      max-width: 700px;
      margin: 0 auto 3.8rem;
      font-weight: 600;
      line-height: 1.7;
      color: #4e5a82dd;
      user-select: text;
      letter-spacing: 0.07em;
      filter: drop-shadow(0 0 13px #4a59a0bb);
      animation: fadeIn 2.1s ease forwards;
      opacity: 0;
    }
    header.hero button {
      background: #6f4fff;
      border: none;
      color: #fff;
      font-weight: 800;
      padding: 1.5rem 5rem;
      font-size: 1.38rem;
      border-radius: 60px;
      cursor: pointer;
      box-shadow: 0 10px 35px #6f4fff88;
      transition: transform 0.35s ease, box-shadow 0.35s ease, background-color 0.35s ease;
      user-select: none;
      font-family: 'Poppins', sans-serif;
      letter-spacing: 0.12em;
      text-shadow: 0 0 6px rgba(0,0,0,0.25);
      animation: fadeInUp 2.5s ease forwards;
      opacity: 0;
    }
    header.hero button:hover,
    header.hero button:focus {
      background-color: #593ededb;
      transform: scale(1.18) translateY(-6px);
      box-shadow: 0 14px 58px #593eeeaf;
      outline: none;
    }
    header.hero button:active {
      transform: scale(1.07) translateY(-3px);
      box-shadow: 0 8px 33px #4d3dff65;
    }

    /* OS Intro blocks */
    section.three-os-intro {
      max-width: 900px;
      margin: 4rem auto 6rem;
      user-select:none;
      padding: 0 1rem;
    }
    .os-block {
      display: flex;
      gap: 3rem;
      margin-bottom: 5rem;
      align-items: center;
      opacity: 0;
      transform: translateY(60px);
      transition: opacity 1.1s ease, transform 1.1s cubic-bezier(0.23, 1, 0.32, 1);
      background: #36304d;
      border-radius: 28px;
      box-shadow: 0 20px 50px #8c8bd1dd;
      padding: 34px 42px;
      filter: drop-shadow(0 7px 12px #756ffa77);
      will-change: opacity, transform;
    }
    .os-block.visible {
      opacity: 1;
      transform: translateY(0);
    }
    /* Alternate layout: reverse row on even blocks */
    .os-block:nth-child(odd) {
      flex-direction: row;
    }
    .os-block:nth-child(even) {
      flex-direction: row-reverse;
    }
    .os-block img {
      width: 220px;
      border-radius: 36px;
      box-shadow: 0 16px 52px #8c69f6cc;
      transition: transform 0.7s ease, filter 0.5s ease;
      flex-shrink: 0;
      background: #8c8ad6;
      padding: 18px;
      filter: drop-shadow(0 0 20px #a2a0ffcc);
    }
    .os-block img:hover,
    .os-block img:focus {
      transform: scale(1.16) rotate(5deg);
      filter: drop-shadow(0 0 38px #9d8fffdd);
      outline: none;
      cursor: default;
      box-shadow: 0 20px 85px #a89fffcc;
    }
    .os-content {
      max-width: 620px;
    }
    .os-content h3 {
      font-size: 3.3rem;
      margin-bottom: 0.8rem;
      font-weight: 900;
      color: #b8b0ff;
      user-select:text;
      letter-spacing: 0.07em;
      text-shadow: 0 3px 10px #a59affcc;
      text-transform: uppercase;
      font-family: 'Fredoka One', cursive;
    }
    .os-content p {
      font-size: 1.3rem;
      color: #ced1edcc;
      line-height: 1.75;
      user-select: text;
      letter-spacing: 0.035em;
      text-shadow: 0 2px 5px #302e5111;
      font-weight: 600;
    }

    /* Testimonials */
    section.testimonials {
      padding: 4.5rem 0 8rem 0;
      background: #271e5d;
      color: #cbc6ffdd;
      user-select:none;
      border-radius: 56px 56px 0 0;
      box-shadow: inset 0 0 95px #7a6eff8a;
      margin-top: -3rem;
      font-family: 'Montserrat', sans-serif;
    }
    section.testimonials h2 {
      text-align: center;
      font-size: 4.1rem;
      margin-bottom: 3.8rem;
      font-weight: 900;
      letter-spacing: 0.14em;
      color: #b39effdd;
      user-select:none;
      text-transform: uppercase;
      text-shadow: 1px 1px 10px #a385ffcc;
    }
    .testimonial-cards {
      max-width: 1100px;
      margin: 0 auto;
      display: flex;
      gap: 3.2rem;
      justify-content: center;
      flex-wrap: wrap;
    }
    .testimonial {
      background: #413a7bdd;
      border-radius: 36px;
      padding: 3.2rem 2.8rem;
      max-width: 360px;
      box-shadow: 0 20px 65px #827bffa8;
      color: #dcd7ff;
      transition: box-shadow 0.38s ease, transform 0.35s ease;
      cursor: default;
      user-select:none;
      font-family: 'Montserrat', sans-serif;
      font-style: italic;
      letter-spacing: 0.025em;
    }
    .testimonial:hover,
    .testimonial:focus-within {
      box-shadow: 0 36px 95px #927affee;
      transform: translateY(-13px);
      outline: none;
    }
    .testimonial img {
      width: 88px;
      height: 88px;
      border-radius: 50%;
      object-fit: cover;
      border: 5px solid #bbacff;
      margin-bottom: 1.7rem;
      filter: drop-shadow(0 5px 12px rgba(0,0,0,0.3));
      transition: transform 0.38s ease;
    }
    .testimonial img:hover,
    .testimonial img:focus {
      transform: scale(1.25);
      outline: none;
      box-shadow: 0 0 15px #bdafffdd;
    }
    .testimonial p {
      font-size: 1.22rem;
      line-height: 1.68;
      font-weight: 700;
      color: #e3dfffdd;
      user-select: text;
      margin-bottom: 1.3rem;
      text-shadow: 1px 1px 10px #504f7a55;
    }
    .testimonial h4 {
      font-style: normal;
      margin-top: 1.5rem;
      font-weight: 900;
      font-size: 1.3rem;
      color: #d6c9ffcc;
      user-select: text;
      letter-spacing: 0.07em;
      text-transform: uppercase;
      text-shadow: 0 0 12px #c8b8ffcc;
    }

    /* Pricing */
    section.pricing {
      background: #372f72ee;
      padding: 5.5rem 0 9rem 0;
      color: #dad0fff0;
      user-select:none;
      border-radius: 56px 56px 32px 32px;
      box-shadow: 0 18px 75px #8f76ffd0;
      font-family:'Poppins', sans-serif;
      margin-top: -3.5rem;
      backdrop-filter: saturate(230%) blur(25px);
      border: 1px solid #685ee8cc;
    }
    section.pricing h2 {
      text-align: center;
      font-size: 4.3rem;
      margin-bottom: 4.5rem;
      font-weight: 900;
      color: #c0b2ffcc;
      letter-spacing: 0.11em;
      user-select: none;
      text-shadow: 2px 2px 12px #9b89ffa8;
      text-transform: uppercase;
      font-family:'Fredoka One', cursive;
    }
    .pricing-cards {
      max-width: 1140px;
      margin: auto;
      display: flex;
      gap: 3.6rem;
      justify-content: center;
      flex-wrap: nowrap;
      flex-direction: row;
      padding: 0 1rem;
    }
    .price-card {
      background: #574edeee;
      border-radius: 48px;
      padding: 4.5rem 4rem;
      flex: 1 1 0;
      box-shadow: 0 20px 70px #a69effcc;
      text-align: center;
      position: relative;
      transition: transform 0.48s cubic-bezier(0.4, 0, 0.2, 1), box-shadow 0.48s ease;
      cursor: default;
      user-select: text;
      border: 2px solid transparent;
      font-weight: 600;
      color: #d8ceffff;
      min-width: 320px;
    }
    .price-card:hover,
    .price-card:focus-within {
      transform: translateY(-22px);
      box-shadow: 0 35px 120px #b49effcc;
      outline: none;
      border-color: #b6a8ffbb;
      background: #6c5fee;
      color: #f2ebff;
    }
    .price-card h3 {
      font-weight: 900;
      font-size: 2.5rem;
      margin-bottom: 1.8rem;
      color: #d3c0ffcc;
      letter-spacing: 0.07em;
      user-select: none;
      text-transform: uppercase;
      text-shadow: 0 2px 8px #b7a8ffcc;
    }
    .price-card p.price {
      font-size: 3.8rem;
      font-weight: 900;
      margin-bottom: 2.3rem;
      user-select:none;
      color: #e3deffff;
      letter-spacing: 0.04em;
      text-shadow: 0 3px 12px #cbbcffdd;
    }
    .price-card ul {
      list-style: none;
      padding: 0;
      margin: 2.5rem 0 4rem;
      font-weight: 700;
      user-select:none;
      color: #c9bfffcc;
      letter-spacing: 0.04em;
    }
    .price-card ul li {
      margin-bottom: 1.5rem;
      font-size: 1.25rem;
      position: relative;
      padding-left: 36px;
      text-shadow: 0 2px 6px #3f3b5588;
    }
    .price-card ul li::before {
      content: "✔";
      position: absolute;
      left: 12px;
      color: #d6ceffff;
      font-weight: 900;
      font-size: 1.25rem;
      top: 2px;
      text-shadow: 1px 1px 6px #6f66ffc8;
    }
    .price-card button {
      background: #867aff;
      border: none;
      padding: 1.4rem 4.5rem;
      font-weight: 900;
      font-size: 1.48rem;
      border-radius: 56px;
      cursor: pointer;
      color: #ede9ff;
      box-shadow: 0 12px 45px #9991ffcc;
      transition: background-color 0.4s ease, transform 0.4s ease, box-shadow 0.4s ease;
      user-select: none;
      font-family: 'Poppins', sans-serif;
      letter-spacing: 0.1em;
      text-shadow: 0 0 16px #aaa4ffcc;
    }
    .price-card button:hover,
    .price-card button:focus {
      background-color: #5b3affcc;
      transform: scale(1.17);
      outline: none;
      box-shadow: 0 20px 75px #5b3affcc;
      text-shadow: 0 0 20px #5b3affcc;
    }
    .price-card button:active {
      transform: scale(1.07);
      box-shadow: 0 10px 35px #5b3aff80;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 3rem 1rem;
      font-size: 1.1rem;
      color: #a299ce;
      background: #292552;
      font-family: 'Poppins', sans-serif;
      user-select:none;
      border-top: 2px solid #685ee8cc;
      letter-spacing: 0.05em;
      font-weight: 600;
      text-shadow: 0 0 10px #7a76e7cc;
    }

    /* Responsive */
    @media (max-width: 1150px) {
      .pricing-cards {
        flex-wrap: nowrap;
        overflow-x: auto;
        padding-bottom: 1rem;
        -webkit-overflow-scrolling: touch;
      }
      .pricing-cards::-webkit-scrollbar {
        height: 8px;
      }
      .pricing-cards::-webkit-scrollbar-thumb {
        background-color: rgba(111,79,255,0.5);
        border-radius: 12px;
      }
      .price-card {
        flex: 0 0 320px;
        min-width: 320px;
      }
    }
    @media (max-width: 650px) {
      .pricing-cards {
        flex-direction: column;
        gap: 2.8rem;
        overflow-x: visible;
      }
      .price-card {
        flex-basis: 100%;
        min-width: auto;
      }
    }
    @media (max-width: 900px) {
      nav ul.nav-menu {
        gap: 1.6rem;
      }
      section.three-os-intro {
        margin: 2.5rem auto 4rem;
        max-width: 100%;
        padding: 0 1.5rem;
      }
      .os-block {
        flex-direction: column !important;
        gap: 2rem;
        margin-bottom: 3.5rem;
        padding: 24px 22px;
      }
      .os-block img {
        width: 70vw;
        max-width: 320px;
        margin: 0 auto;
        border-radius: 28px;
      }
      .os-content {
        max-width: 100%;
        text-align: center;
      }
      .testimonial-cards, 
      .pricing-cards {
        flex-direction: column;
        align-items: center;
      }
      .price-card,
      .testimonial {
        max-width: 100%;
      }
    }
    @media (max-width: 480px) {
      header.hero h1 {
        font-size: 2.8rem;
      }
      header.hero p {
        font-size: 1.2rem;
        max-width: 95vw;
      }
      section.testimonials h2,
      section.pricing h2 {
        font-size: 2.6rem;
      }
      .price-card h3 {
        font-size: 1.7rem;
      }
      .os-content h3 {
        font-size: 2.2rem;
      }
    }
    /* Animations */

    @keyframes fadeInUp {
      from {
        opacity: 0; 
        transform: translateY(40px);
      } to {
        opacity: 1; 
        transform: translateY(0);
      }
    }
    @keyframes slideInDown {
      from {
        opacity: 0; 
        transform: translateY(-30px);
      } to {
        opacity: 1; 
        transform: translateY(0);
      }
    }
    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }
  </style>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Montserrat&family=Poppins&display=swap" rel="stylesheet" />
</head>

<body>
  <nav class="navbar" id="navbar" role="navigation" aria-label="Primary Navigation">
    <div class="logo" tabindex="0" aria-label="Scroll to top" role="link" onclick="scrollToTop()" onkeypress="if(event.key==='Enter'){scrollToTop()}">OS WORLD</div>
    <ul class="nav-menu" role="menubar">
      <li role="none"><a href="#hero" role="menuitem" tabindex="0" onclick="scrollToSection('hero')">About</a></li>
      <li class="dropdown" role="none" aria-haspopup="true" aria-expanded="false">
        <a href="#threeos" role="menuitem" tabindex="0" aria-controls="threeOSDropdown" aria-haspopup="true">Three OS</a>
        <ul class="dropdown-menu" role="menu" id="threeOSDropdown" aria-label="Three operating systems submenu">
          <li role="none"><a href="#os-windows" role="menuitem" tabindex="0" onclick="scrollToSection('os-windows')">Windows</a></li>
          <li role="none"><a href="#os-macos" role="menuitem" tabindex="0" onclick="scrollToSection('os-macos')">macOS</a></li>
          <li role="none"><a href="#os-linux" role="menuitem" tabindex="0" onclick="scrollToSection('os-linux')">Linux</a></li>
        </ul>
      </li>
      <li role="none"><a href="#pricing" role="menuitem" tabindex="0" onclick="scrollToSection('pricing')">Pricing</a></li>
      <li role="none"><a href="#testimonials" role="menuitem" tabindex="0" onclick="scrollToSection('testimonials')">Testimonials</a></li>
    </ul>
  </nav>

  <header class="hero" id="hero">
    <h1>Discover the Power of OS</h1>
    <p>Explore the modern operating systems that power your world: Windows, macOS, and Linux. Designed to elevate your productivity and creativity.</p>
    <button onclick="scrollToSection('threeos')" aria-label="Explore more about operating systems">Explore More</button>
  </header>

  <section class="three-os-intro container" id="threeos" aria-label="Introduction to three operating systems">
    <article class="os-block" id="os-windows" tabindex="0" aria-label="Windows operating system introduction">
      <img src="https://upload.wikimedia.org/wikipedia/commons/5/5f/Windows_logo_-_2012.svg" alt="Windows OS Logo" />
      <div class="os-content">
        <h3>Windows</h3>
        <p>Versatile and widely compatible, Windows is the preferred choice for business, gaming, and personal use, delivering a familiar and productive experience for millions.</p>
      </div>
    </article>
    <article class="os-block" id="os-macos" tabindex="0" aria-label="macOS operating system introduction">
      <img src="https://upload.wikimedia.org/wikipedia/commons/f/fa/Apple_logo_black.svg" alt="macOS Logo" />
      <div class="os-content">
        <h3>macOS</h3>
        <p>Elegant and powerful, macOS is designed for seamless creativity and performance, perfectly integrating hardware and software for professionals and artists alike.</p>
      </div>
    </article>
    <article class="os-block" id="os-linux" tabindex="0" aria-label="Linux operating system introduction">
      <img src="https://upload.wikimedia.org/wikipedia/commons/a/af/Tux.png" alt="Linux OS Logo" />
      <div class="os-content">
        <h3>Linux</h3>
        <p>Open-source and customizable, Linux offers unmatched flexibility and security for developers, enthusiasts, and enterprises building innovative solutions.</p>
      </div>
    </article>
  </section>

  <section class="testimonials container" id="testimonials" aria-label="User testimonials">
    <h2>What Our Users Say</h2>
    <div class="testimonial-cards">
      <article class="testimonial" tabindex="0">
        <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Emily R." />
        <p>"Switching to Linux has completely transformed my workflow. I love the flexibility and the community support is amazing!"</p>
        <h4>- Emily R.</h4>
      </article>
      <article class="testimonial" tabindex="0">
        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Michael T." />
        <p>"Windows is my go-to for gaming and everyday tasks. It's intuitive and compatible with everything I need."</p>
        <h4>- Michael T.</h4>
      </article>
      <article class="testimonial" tabindex="0">
        <img src="https://randomuser.me/api/portraits/women/80.jpg" alt="Sophia L." />
        <p>"I absolutely adore macOS for my creative projects. The design and ease of use are simply unmatched."</p>
        <h4>- Sophia L.</h4>
      </article>
    </div>
  </section>

  <section class="pricing container" id="pricing" aria-label="Pricing plans">
    <h2>Choose the Plan That's Right for You</h2>
    <div class="pricing-cards">
      <article class="price-card" tabindex="0" aria-label="Basic pricing plan">
        <h3>Basic</h3>
        <p class="price">$0 <span style="font-size: 1.1rem; font-weight: 400;">/ month</span></p>
        <ul>
          <li>Access to Windows OS</li>
          <li>Community Support</li>
          <li>Basic Security</li>
        </ul>
        <button>Get Started</button>
      </article>
      <article class="price-card" tabindex="0" aria-label="Pro pricing plan">
        <h3>Pro</h3>
        <p class="price">$29 <span style="font-size: 1.1rem; font-weight: 400;">/ month</span></p>
        <ul>
          <li>Access to Windows & macOS</li>
          <li>Priority Support</li>
          <li>Advanced Security</li>
          <li>Cloud Backup</li>
        </ul>
        <button>Upgrade Now</button>
      </article>
      <article class="price-card" tabindex="0" aria-label="Enterprise pricing plan">
        <h3>Enterprise</h3>
        <p class="price">$99 <span style="font-size: 1.1rem; font-weight: 400;">/ month</span></p>
        <ul>
          <li>Access to Windows, macOS & Linux</li>
          <li>Dedicated Support</li>
          <li>Full Security Suite</li>
          <li>Custom Integrations</li>
        </ul>
        <button>Contact Sales</button>
      </article>
    </div>
  </section>

  <footer>
    &copy; 2024 OS World. All rights reserved.
  </footer>

  <script>
    // Scroll to section helper
    function scrollToSection(id) {
      const section = document.getElementById(id);
      if(section) {
        section.scrollIntoView({behavior: 'smooth'});
      }
    }
    function scrollToTop() {
      window.scrollTo({top:0, behavior:'smooth'});
    }

    // Navbar scroll effect
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
      if(window.scrollY > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });

    // Dropdown accessible keyboard support
    const dropdowns = document.querySelectorAll('li.dropdown');
    dropdowns.forEach(dropdown => {
      const link = dropdown.querySelector('a');
      const menu = dropdown.querySelector('.dropdown-menu');
      link.addEventListener('keydown', e => {
        const isExpanded = dropdown.classList.contains('open');
        if(e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          if(isExpanded) {
            dropdown.classList.remove('open');
            link.setAttribute('aria-expanded', 'false');
            menu.style.opacity = '0';
            menu.style.visibility = 'hidden';
            menu.style.transform = 'translateY(10px)';
          } else {
            dropdown.classList.add('open');
            link.setAttribute('aria-expanded', 'true');
            menu.style.opacity = '1';
            menu.style.visibility = 'visible';
            menu.style.transform = 'translateY(0)';
          }
        }
        if(e.key === 'Escape') {
          dropdown.classList.remove('open');
          link.setAttribute('aria-expanded', 'false');
          menu.style.opacity = '0';
          menu.style.visibility = 'hidden';
          menu.style.transform = 'translateY(10px)';
          link.focus();
        }
      });
      // Close if click outside
      document.addEventListener('click', (e) => {
        if(!dropdown.contains(e.target)) {
          dropdown.classList.remove('open');
          link.setAttribute('aria-expanded', 'false');
          menu.style.opacity = '0';
          menu.style.visibility = 'hidden';
          menu.style.transform = 'translateY(10px)';
        }
      });
    });

    // Scroll fade-in animation for OS blocks
    const osBlocks = document.querySelectorAll('.os-block');
    function checkFadeIn(){
      const triggerBottom = window.innerHeight * 0.85;
      osBlocks.forEach(block => {
        const top = block.getBoundingClientRect().top;
        if(top < triggerBottom){
          block.classList.add('visible');
        }
      });
    }
    window.addEventListener('scroll', checkFadeIn);
    window.addEventListener('load', () => {
      checkFadeIn();
    });
  </script>
</body>
</html>

