from pathlib import Path
import zipfile, textwrap, os

root = Path("/mnt/data/peshawar-elevators-website")
assets = root / "assets"
assets.mkdir(parents=True, exist_ok=True)

files = {}

files["index.html"] = r'''<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#0b4f9c">
  <meta name="description" content="Peshawar Elevators provides elevator installation, maintenance, repair, troubleshooting and modernization services in Peshawar and across Khyber Pakhtunkhwa, Pakistan.">
  <title>Peshawar Elevators | Installation, Maintenance & Modernization</title>
  <link rel="icon" type="image/svg+xml" href="assets/logo.svg">
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="topbar">
    <div class="container topbar-inner">
      <span>Reliable elevator solutions in Peshawar &amp; Khyber Pakhtunkhwa</span>
      <a href="tel:+923350949648">Call us: 0335 0949648</a>
    </div>
  </div>

  <header class="site-header">
    <div class="container nav-wrap">
      <a class="brand" href="#home" aria-label="Peshawar Elevators home">
        <img src="assets/logo.svg" alt="" width="46" height="46">
        <span><strong>PESHAWAR</strong><small>ELEVATORS</small></span>
      </a>
      <button class="menu-toggle" id="menuToggle" aria-label="Open navigation menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
      <nav class="nav" id="mainNav" aria-label="Main navigation">
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#about">About Us</a>
        <a href="#why-us">Why Choose Us</a>
        <a href="#contact" class="nav-cta">Get a Quote <span aria-hidden="true">↗</span></a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero" id="home">
      <div class="hero-grid" aria-hidden="true"></div>
      <div class="container hero-layout">
        <div class="hero-copy">
          <div class="eyebrow"><span class="eyebrow-dot"></span> ELEVATOR SOLUTIONS YOU CAN RELY ON</div>
          <h1>Moving people.<br><span>Building confidence.</span></h1>
          <p class="hero-text">Installation, maintenance, repair and modernization for residential, commercial and industrial elevators.</p>
          <div class="hero-actions">
            <a class="button button-light" href="#contact">Request a quotation <span aria-hidden="true">→</span></a>
            <a class="button button-outline" href="#services">Explore our services</a>
          </div>
          <div class="hero-trust">
            <div class="trust-icon" aria-hidden="true">✓</div>
            <p><strong>Safety-focused service</strong><span>Quality workmanship. Clear communication.</span></p>
          </div>
        </div>
        <div class="hero-visual">
          <div class="visual-glow"></div>
          <div class="hero-card card-label label-top"><span class="label-symbol">↗</span><span><strong>Modern solutions</strong><small>For every building</small></span></div>
          <div class="lift-illustration" role="img" aria-label="Illustration of a modern elevator inside a blue building">
            <div class="building-back"></div>
            <div class="lift-frame">
              <div class="lift-topline"></div>
              <div class="lift-door left-door"></div>
              <div class="lift-door right-door"></div>
              <div class="lift-floor"></div>
              <div class="lift-control"><span></span><i></i></div>
            </div>
            <div class="floor-lines"></div>
            <div class="visual-orbit orbit-one"></div><div class="visual-orbit orbit-two"></div>
          </div>
          <div class="hero-card card-label label-bottom"><span class="label-check">✓</span><span><strong>Service &amp; support</strong><small>When you need it</small></span></div>
        </div>
      </div>
      <div class="hero-bottom-line"></div>
    </section>

    <section class="service-strip" aria-label="Our key services">
      <div class="container strip-grid">
        <div><span class="strip-icon">01</span><span><strong>New Installation</strong><small>Planned for your building</small></span></div>
        <div><span class="strip-icon">02</span><span><strong>Maintenance &amp; Repair</strong><small>Care that keeps you moving</small></span></div>
        <div><span class="strip-icon">03</span><span><strong>Modernization</strong><small>Upgrade existing systems</small></span></div>
      </div>
    </section>

    <section class="section services-section" id="services">
      <div class="container">
        <div class="section-heading">
          <div>
            <div class="eyebrow eyebrow-blue">WHAT WE DO</div>
            <h2>Complete elevator services,<br><span>from start to support.</span></h2>
          </div>
          <p>Practical solutions for new projects and existing lifts, with attention to performance, reliability and safety.</p>
        </div>
        <div class="service-cards">
          <article class="service-card">
            <div class="service-card-top"><div class="service-icon"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M5 21V3h14v18M9 7h6M9 11h6M9 15h6M9 19h6"/></svg></div><span class="card-number">01</span></div>
            <h3>New Elevator Installation</h3>
            <p>Installation support for residential, commercial and industrial buildings, including imported and semi-imported elevator systems.</p>
            <a href="#contact" class="text-link">Discuss your project <span>→</span></a>
          </article>
          <article class="service-card featured-card">
            <div class="service-card-top"><div class="service-icon"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 3 4.5 6v5.5c0 4.7 3.2 7.7 7.5 9.5 4.3-1.8 7.5-4.8 7.5-9.5V6L12 3Z"/><path d="m8.5 12 2.2 2.2 4.8-5"/></svg></div><span class="card-number">02</span></div>
            <h3>Maintenance &amp; Repair</h3>
            <p>Routine servicing, fault diagnosis, troubleshooting and repair to help keep elevator equipment working reliably.</p>
            <a href="#contact" class="text-link">Book a service <span>→</span></a>
          </article>
          <article class="service-card">
            <div class="service-card-top"><div class="service-icon"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M4 20V9l8-5 8 5v11M8 20v-6h8v6M8 9h.01M12 9h.01M16 9h.01"/><path d="M2 4h5M4.5 1.5v5"/></svg></div><span class="card-number">03</span></div>
            <h3>Modernization</h3>
            <p>Upgrade and replacement options for selected components to improve operation, usability and system performance.</p>
            <a href="#contact" class="text-link">Explore upgrades <span>→</span></a>
          </article>
          <article class="service-card">
            <div class="service-card-top"><div class="service-icon"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M4 19V5M4 19h16M7 15l4-4 3 2 5-6"/><circle cx="19" cy="7" r="1.5"/></svg></div><span class="card-number">04</span></div>
            <h3>Inspection &amp; Troubleshooting</h3>
            <p>System checks and fault-finding support for elevator controls, door systems, drives and related components.</p>
            <a href="#contact" class="text-link">Tell us the issue <span>→</span></a>
          </article>
          <article class="service-card">
            <div class="service-card-top"><div class="service-icon"><svg viewBox="0 0 24 24" aria-hidden="true"><path d="M3 21h18M5 21V7l7-4 7 4v14M9 10h6M9 14h6M9 18h6"/></svg></div><span class="card-number">05</span></div>
            <h3>Elevator Parts &amp; Components</h3>
            <p>Support with sourcing and replacing suitable elevator parts, subject to system specifications and availability.</p>
            <a href="#contact" class="text-link">Ask about parts <span>→</span></a>
          </article>
          <article class="service-card service-card-cta">
            <div class="cta-orb"></div>
            <div class="eyebrow">HAVE A PROJECT IN MIND?</div>
            <h3>Let's find the right solution.</h3>
            <p>Share your building details or service requirements with our team.</p>
            <a href="#contact" class="button button-blue">Contact us <span>→</span></a>
          </article>
        </div>
      </div>
    </section>

    <section class="about-section section" id="about">
      <div class="container about-layout">
        <div class="about-visual">
          <div class="about-photo-frame">
            <div class="about-architecture">
              <div class="arch-building building-one"><span></span><span></span><span></span><span></span></div>
              <div class="arch-building building-two"><span></span><span></span><span></span><span></span></div>
              <div class="arch-lift"><div class="arch-door"></div><div class="arch-door"></div></div>
              <div class="arch-ground"></div>
            </div>
            <div class="about-stamp"><span>PE</span><small>ENGINEERING<br>SOLUTIONS</small></div>
          </div>
          <div class="about-caption"><span class="caption-line"></span><span>Supporting buildings across Peshawar and KP</span></div>
        </div>
        <div class="about-copy">
          <div class="eyebrow eyebrow-blue">ABOUT PESHAWAR ELEVATORS</div>
          <h2>Keeping your building<br><span>moving with confidence.</span></h2>
          <p>Peshawar Elevators provides elevator installation, maintenance, repair and modernization services in Peshawar and across Khyber Pakhtunkhwa, Pakistan.</p>
          <p>We work to understand each building's requirements and recommend practical solutions based on the equipment, site conditions and customer needs.</p>
          <ul class="check-list">
            <li><span>✓</span> Residential, commercial and industrial applications</li>
            <li><span>✓</span> Maintenance, fault diagnosis and repair</li>
            <li><span>✓</span> Focus on quality standards and safe working practices</li>
          </ul>
          <a class="button button-blue" href="#contact">Talk to our team <span>→</span></a>
        </div>
      </div>
    </section>

    <section class="why-section section" id="why-us">
      <div class="container">
        <div class="center-heading">
          <div class="eyebrow eyebrow-light">WHY PESHAWAR ELEVATORS</div>
          <h2>A dependable partner<br>for your elevator needs.</h2>
          <p>We aim to make every service interaction clear, practical and focused on the needs of your building.</p>
        </div>
        <div class="why-grid">
          <div class="why-item"><div class="why-icon">◎</div><h3>Safety-minded work</h3><p>We place emphasis on safe working practices and appropriate system checks.</p></div>
          <div class="why-item"><div class="why-icon">⌁</div><h3>Technical approach</h3><p>We investigate symptoms and equipment conditions to help identify the issue.</p></div>
          <div class="why-item"><div class="why-icon">↗</div><h3>Practical solutions</h3><p>Recommendations are guided by your elevator type, site and service requirements.</p></div>
          <div class="why-item"><div class="why-icon">◷</div><h3>Clear communication</h3><p>We aim to explain the work required, parts considerations and next steps.</p></div>
        </div>
      </div>
    </section>

    <section class="section process-section">
      <div class="container">
        <div class="section-heading">
          <div><div class="eyebrow eyebrow-blue">HOW WE WORK</div><h2>A simple process<br><span>from enquiry to service.</span></h2></div>
          <p>Tell us what you need. We will discuss the details and help you understand the next step.</p>
        </div>
        <div class="process-grid">
          <div class="process-step"><span class="step-no">01</span><div class="step-line"></div><h3>Contact us</h3><p>Call or WhatsApp with your location and elevator requirements.</p></div>
          <div class="process-step"><span class="step-no">02</span><div class="step-line"></div><h3>Share details</h3><p>Tell us the elevator type, building use and issue or project scope.</p></div>
          <div class="process-step"><span class="step-no">03</span><div class="step-line"></div><h3>Discuss solution</h3><p>We discuss the next steps, inspection needs and quotation details.</p></div>
          <div class="process-step"><span class="step-no">04</span><div class="step-line"></div><h3>Plan the work</h3><p>Agree on the scope and schedule before work proceeds.</p></div>
        </div>
      </div>
    </section>

    <section class="contact-section section" id="contact">
      <div class="container contact-layout">
        <div class="contact-copy">
          <div class="eyebrow eyebrow-light">LET'S TALK</div>
          <h2>Need elevator service<br>or a project quotation?</h2>
          <p>Get in touch with Peshawar Elevators. Tell us about your building, installation project or elevator issue.</p>
          <div class="contact-details">
            <a href="tel:+923350949648" class="contact-detail"><span class="detail-icon">☎</span><span><small>Call us</small><strong>0335 0949648</strong></span></a>
            <div class="contact-detail"><span class="detail-icon">⌖</span><span><small>Service area</small><strong>Peshawar, Pakistan</strong><em>Serving Peshawar and Khyber Pakhtunkhwa</em></span></div>
          </div>
        </div>
        <form class="contact-form" id="quoteForm">
          <h3>Request a quotation</h3>
          <p>Complete the form and continue to WhatsApp to send your enquiry.</p>
          <label for="name">Your name</label>
          <input id="name" name="name" type="text" placeholder="Enter your name" required>
          <label for="phone">Phone number</label>
          <input id="phone" name="phone" type="tel" placeholder="Your contact number" required>
          <label for="service">Service required</label>
          <select id="service" name="service" required>
            <option value="">Select a service</option>
            <option>New elevator installation</option>
            <option>Maintenance and repair</option>
            <option>Elevator troubleshooting</option>
            <option>Modernization</option>
            <option>Elevator parts</option>
            <option>Other enquiry</option>
          </select>
          <label for="message">Project or issue details</label>
          <textarea id="message" name="message" rows="3" placeholder="Building location, elevator type, or issue"></textarea>
          <button type="submit" class="button button-blue form-button">Continue to WhatsApp <span>↗</span></button>
          <small class="form-note">Your message opens in WhatsApp. It is not stored on this website.</small>
        </form>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container footer-main">
      <a class="brand footer-brand" href="#home">
        <img src="assets/logo.svg" alt="" width="42" height="42">
        <span><strong>PESHAWAR</strong><small>ELEVATORS</small></span>
      </a>
      <p>Elevator installation, maintenance, repair and modernization.</p>
      <a class="footer-whatsapp" href="https://wa.me/923350949648" target="_blank" rel="noopener noreferrer">WhatsApp us <span>↗</span></a>
    </div>
    <div class="container footer-bottom">
      <span>© <span id="year"></span> Peshawar Elevators. All rights reserved.</span>
      <span>Quality standards and safety come first.</span>
    </div>
  </footer>

  <a class="floating-whatsapp" href="https://wa.me/923350949648?text=Assalam-o-Alaikum%2C%20I%20need%20information%20about%20your%20elevator%20services." target="_blank" rel="noopener noreferrer" aria-label="Chat with Peshawar Elevators on WhatsApp">
    <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M20.5 3.5A11.8 11.8 0 0 0 12.1 0C5.6 0 .3 5.3.3 11.8c0 2.1.6 4.1 1.6 5.9L0 24l6.5-1.7a11.8 11.8 0 0 0 5.6 1.4h.1C18.7 23.7 24 18.4 24 11.9c0-3.2-1.2-6.2-3.5-8.4ZM12.1 21.7a9.8 9.8 0 0 1-5-1.4l-.4-.2-3.9 1 1-3.8-.3-.4a9.8 9.8 0 0 1-1.5-5.2c0-5.5 4.5-10 10-10a9.9 9.9 0 0 1 10 10c0 5.5-4.5 10-9.9 10Zm5.5-7.5c-.3-.2-1.8-.9-2.1-1-.3-.1-.5-.2-.7.2-.2.3-.8 1-1 1.2-.2.2-.4.2-.7.1-.3-.2-1.3-.5-2.4-1.5-.9-.8-1.5-1.8-1.7-2.1-.2-.3 0-.5.1-.6l.5-.6c.2-.2.2-.3.3-.5.1-.2 0-.4 0-.6-.1-.2-.7-1.7-1-2.3-.2-.6-.5-.5-.7-.5h-.6c-.2 0-.6.1-.9.4-.3.3-1.2 1.1-1.2 2.7s1.2 3.1 1.4 3.3c.2.2 2.3 3.5 5.6 4.9.8.3 1.4.5 1.9.6.8.3 1.5.2 2 .1.6-.1 1.8-.7 2-1.4.2-.7.2-1.3.1-1.4-.1-.1-.3-.2-.6-.4Z"/></svg>
  </a>

  <script src="script.js"></script>
</body>
</html>
'''

files["styles.css"] = r''':root {
  --blue: #0b4f9c;
  --blue-dark: #082e5b;
  --blue-deep: #061f3d;
  --blue-bright: #1c74cf;
  --blue-pale: #eaf4ff;
  --ink: #10243b;
  --muted: #5d6c7d;
  --line: #dfe8f1;
  --white: #fff;
  --radius: 18px;
  --shadow: 0 18px 55px rgba(7, 42, 79, .10);
}
* { box-sizing: border-box; }
html { scroll-behavior: smooth; scroll-padding-top: 90px; }
body { margin: 0; font-family: Inter, "Segoe UI", Arial, sans-serif; color: var(--ink); background: #fff; line-height: 1.6; }
a { color: inherit; text-decoration: none; }
button, input, select, textarea { font: inherit; }
.container { width: min(1160px, calc(100% - 44px)); margin-inline: auto; }
.topbar { background: #06284d; color: #dcecff; font-size: 12px; letter-spacing: .025em; }
.topbar-inner { min-height: 36px; display: flex; justify-content: space-between; align-items: center; gap: 18px; }
.topbar a { color: #fff; font-weight: 700; }
.site-header { position: sticky; z-index: 20; top: 0; background: rgba(255,255,255,.96); backdrop-filter: blur(12px); border-bottom: 1px solid rgba(221,232,243,.8); }
.nav-wrap { display: flex; align-items: center; justify-content: space-between; min-height: 82px; gap: 28px; }
.brand { display: inline-flex; align-items: center; gap: 11px; flex-shrink: 0; color: var(--blue-dark); }
.brand img { display: block; }
.brand span { display: flex; flex-direction: column; line-height: 1.05; letter-spacing: .07em; }
.brand strong { font-size: 16px; font-weight: 900; }
.brand small { margin-top: 5px; font-size: 11px; font-weight: 700; letter-spacing: .31em; color: var(--blue); }
.nav { display: flex; align-items: center; gap: 30px; font-size: 13px; font-weight: 700; color: #31445b; }
.nav > a:not(.nav-cta):hover { color: var(--blue-bright); }
.nav-cta { display: inline-flex; align-items: center; gap: 12px; padding: 12px 17px; border-radius: 8px; background: var(--blue); color: #fff; box-shadow: 0 7px 18px rgba(11,79,156,.18); }
.nav-cta:hover, .button-blue:hover { background: #073d79; transform: translateY(-1px); }
.menu-toggle { display: none; border: 0; background: transparent; padding: 8px; cursor: pointer; }
.menu-toggle span { display: block; width: 24px; height: 2px; margin: 5px; background: var(--blue-dark); }
.hero { position: relative; overflow: hidden; color: #fff; background: linear-gradient(116deg, #082c56 0%, #0b4f9c 56%, #1267b8 100%); }
.hero-grid { position: absolute; inset: 0; opacity: .14; background-image: linear-gradient(rgba(255,255,255,.22) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.22) 1px, transparent 1px); background-size: 48px 48px; mask-image: linear-gradient(90deg, #000, transparent 95%); }
.hero-layout { position: relative; z-index: 1; display: grid; grid-template-columns: 1.04fr .96fr; gap: 42px; align-items: center; min-height: 590px; padding-top: 48px; padding-bottom: 62px; }
.hero-copy { max-width: 590px; padding: 12px 0 25px; }
.eyebrow { display: flex; align-items: center; gap: 10px; font-size: 10px; line-height: 1.4; letter-spacing: .19em; font-weight: 800; color: #c6e1ff; }
.eyebrow-dot { width: 7px; height: 7px; border-radius: 50%; background: #79c6ff; box-shadow: 0 0 0 5px rgba(121,198,255,.15); }
.eyebrow-blue { color: var(--blue); }
.eyebrow-light { color: #a9d4ff; }
h1, h2, h3, p { margin-top: 0; }
.hero h1 { margin: 25px 0 18px; font-size: clamp(42px, 5vw, 65px); line-height: 1.08; letter-spacing: -.045em; font-weight: 800; }
.hero h1 span { color: #9fd5ff; }
.hero-text { max-width: 490px; color: #d5e8fb; font-size: 16px; line-height: 1.8; margin-bottom: 28px; }
.hero-actions { display: flex; flex-wrap: wrap; gap: 12px; }
.button { display: inline-flex; align-items: center; justify-content: center; gap: 17px; min-height: 48px; padding: 13px 18px; border: 1px solid transparent; border-radius: 8px; font-size: 13px; font-weight: 800; transition: .2s ease; cursor: pointer; }
.button-light { color: var(--blue-dark); background: #fff; }
.button-light:hover { background: #e9f4ff; transform: translateY(-1px); }
.button-outline { color: #fff; border-color: rgba(255,255,255,.42); background: rgba(255,255,255,.04); }
.button-outline:hover { background: rgba(255,255,255,.12); }
.button-blue { color: #fff; background: var(--blue); }
.hero-trust { display: flex; align-items: center; gap: 12px; margin-top: 35px; }
.trust-icon { width: 29px; height: 29px; display: grid; place-items: center; border: 1px solid rgba(185,226,255,.65); border-radius: 50%; color: #b9e2ff; font-weight: 800; }
.hero-trust p { display: flex; flex-direction: column; margin: 0; gap: 1px; }
.hero-trust strong { font-size: 12px; }
.hero-trust span { font-size: 11px; color: #c4dcf5; }
.hero-visual { position: relative; min-height: 435px; display: grid; place-items: center; }
.visual-glow { position: absolute; width: 360px; height: 360px; border-radius: 50%; background: rgba(111,191,255,.17); filter: blur(10px); }
.lift-illustration { position: relative; width: min(100%, 430px); height: 420px; }
.building-back { position: absolute; width: 65%; height: 90%; left: 19%; top: 5%; background: linear-gradient(110deg, rgba(255,255,255,.22), rgba(255,255,255,.04)); clip-path: polygon(18% 0,100% 0,100% 100%,0 100%,0 18%); border: 1px solid rgba(255,255,255,.25); }
.lift-frame { position: absolute; width: 48%; height: 76%; left: 28%; top: 14%; border: 7px solid #b7ddff; border-bottom: 0; border-radius: 3px 3px 0 0; background: rgba(2,23,49,.38); box-shadow: 0 18px 50px rgba(0,0,0,.2); }
.lift-topline { height: 10px; background: #d6ecff; margin: 0 -7px; }
.lift-door { position: absolute; top: 18px; bottom: 0; width: 50%; background: linear-gradient(100deg, #f4f9ff, #bddbf5); border: 1px solid #87b6e5; }
.left-door { left: 0; transform-origin: left; }
.right-door { right: 0; background: linear-gradient(260deg, #edf7ff, #b4d4f0); }
.lift-door::after { content: ""; position: absolute; top: 0; bottom: 0; left: 50%; width: 1px; background: rgba(49,103,155,.22); }
.lift-floor { position: absolute; z-index: 2; height: 12px; left: -20px; right: -20px; bottom: -1px; background: #d3e9fc; box-shadow: 0 12px 0 rgba(2,21,44,.2); }
.lift-control { position: absolute; z-index: 3; right: -29px; top: 45%; width: 14px; height: 38px; border-radius: 3px; background: #d6ebff; display: flex; align-items: center; flex-direction: column; gap: 5px; padding-top: 6px; }
.lift-control span, .lift-control i { width: 4px; height: 4px; border-radius: 50%; background: var(--blue); }
.floor-lines { position: absolute; bottom: 10%; left: 3%; right: 3%; height: 1px; background: rgba(255,255,255,.35); box-shadow: 0 -55px rgba(255,255,255,.12), 0 -110px rgba(255,255,255,.12); }
.visual-orbit { position: absolute; border: 1px solid rgba(183,221,255,.28); border-radius: 50%; }
.orbit-one { width: 360px; height: 360px; top: 7%; left: 8%; }
.orbit-two { width: 280px; height: 280px; top: 16%; left: 17%; }
.hero-card { position: absolute; z-index: 4; display: flex; align-items: center; gap: 10px; padding: 12px 15px; color: var(--ink); background: #fff; border-radius: 10px; box-shadow: 0 15px 40px rgba(1,20,43,.2); }
.card-label strong, .card-label small { display: block; }
.card-label strong { font-size: 11px; }
.card-label small { color: var(--muted); font-size: 10px; margin-top: 2px; }
.label-top { top: 14%; right: -1%; }
.label-bottom { bottom: 12%; left: 0; }
.label-symbol, .label-check { display: grid; place-items: center; width: 33px; height: 33px; border-radius: 8px; background: var(--blue-pale); color: var(--blue); font-size: 18px; font-weight: 800; }
.label-check { background: #e5f8f0; color: #12835a; }
.hero-bottom-line { position: absolute; bottom: 0; left: 0; right: 0; height: 5px; background: linear-gradient(90deg, #8fd0ff, #fff 45%, #8fd0ff); opacity: .65; }
.service-strip { background: #f6faff; border-bottom: 1px solid #e4eef8; }
.strip-grid { display: grid; grid-template-columns: repeat(3, 1fr); }
.strip-grid > div { display: flex; align-items: center; gap: 14px; padding: 24px 20px; border-right: 1px solid #e0eaf4; }
.strip-grid > div:first-child { padding-left: 0; }
.strip-grid > div:last-child { border-right: 0; }
.strip-icon { color: var(--blue); font-size: 12px; font-weight: 900; letter-spacing: .08em; padding-right: 14px; border-right: 1px solid #bfd8ef; }
.strip-grid strong, .strip-grid small { display: block; }
.strip-grid strong { font-size: 12px; }
.strip-grid small { color: var(--muted); font-size: 11px; margin-top: 2px; }
.section { padding: 100px 0; }
.section-heading { display: flex; align-items: end; justify-content: space-between; gap: 40px; margin-bottom: 42px; }
.section-heading h2, .about-copy h2, .center-heading h2, .contact-copy h2 { margin: 15px 0 0; font-size: clamp(30px, 3.3vw, 43px); line-height: 1.18; letter-spacing: -.04em; color: var(--ink); }
.section-heading h2 span, .about-copy h2 span { color: var(--blue); }
.section-heading > p { max-width: 360px; margin: 0 0 3px; color: var(--muted); font-size: 14px; line-height: 1.8; }
.service-cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; }
.service-card { min-height: 270px; display: flex; flex-direction: column; padding: 25px; border: 1px solid var(--line); border-radius: var(--radius); background: #fff; transition: .22s ease; }
.service-card:hover { transform: translateY(-4px); border-color: #b6d5f3; box-shadow: var(--shadow); }
.service-card-top { display: flex; align-items: start; justify-content: space-between; margin-bottom: 22px; }
.service-icon { width: 49px; height: 49px; display: grid; place-items: center; border-radius: 12px; background: var(--blue-pale); color: var(--blue); }
.service-icon svg { width: 25px; height: 25px; fill: none; stroke: currentColor; stroke-width: 1.6; stroke-linecap: round; stroke-linejoin: round; }
.card-number { color: #8fa0b2; font-size: 11px; font-weight: 800; }
.service-card h3 { margin-bottom: 10px; font-size: 17px; letter-spacing: -.02em; }
.service-card p { color: var(--muted); font-size: 12px; line-height: 1.8; margin-bottom: 20px; }
.text-link { display: inline-flex; align-items: center; gap: 10px; margin-top: auto; color: var(--blue); font-size: 12px; font-weight: 800; }
.text-link span { transition: transform .2s; }
.text-link:hover span { transform: translateX(4px); }
.featured-card { border-color: #b7d9f7; background: linear-gradient(145deg, #f4faff, #fff); }
.service-card-cta { position: relative; overflow: hidden; color: #fff; border: 0; background: linear-gradient(145deg, #0b4f9c, #082c56); }
.service-card-cta .eyebrow { position: relative; z-index: 1; font-size: 9px; }
.service-card-cta h3 { position: relative; z-index: 1; margin-top: 22px; font-size: 23px; line-height: 1.2; }
.service-card-cta p { position: relative; z-index: 1; color: #d0e4f8; }
.service-card-cta .button { align-self: flex-start; position: relative; z-index: 1; }
.cta-orb { position: absolute; width: 190px; height: 190px; right: -80px; top: -80px; border: 1px solid rgba(255,255,255,.2); border-radius: 50%; box-shadow: 0 0 0 25px rgba(255,255,255,.04), 0 0 0 50px rgba(255,255,255,.025); }
.about-section { background: #f5f9fd; }
.about-layout { display: grid; grid-template-columns: .92fr 1.08fr; align-items: center; gap: 78px; }
.about-visual { min-width: 0; }
.about-photo-frame { position: relative; min-height: 430px; overflow: hidden; border-radius: 18px; background: linear-gradient(145deg, #dceeff, #b6d9f6); box-shadow: 0 20px 45px rgba(18,70,119,.12); }
.about-architecture { position: absolute; inset: 0; background: linear-gradient(135deg, rgba(255,255,255,.22), transparent 65%); }
.arch-building { position: absolute; bottom: 0; display: grid; grid-template-columns: repeat(2, 1fr); gap: 13px; padding: 24px 17px; background: #5b8dbd; border: 5px solid #4779aa; }
.arch-building span { width: 25px; height: 32px; background: #d9edff; opacity: .9; }
.building-one { left: 4%; height: 69%; width: 27%; }
.building-two { right: 4%; height: 82%; width: 30%; background: #7eadd7; }
.arch-lift { position: absolute; z-index: 2; bottom: 0; left: 28%; width: 44%; height: 78%; padding: 13px 11px 0; background: #245a91; border: 4px solid #dff0ff; border-bottom: 0; box-shadow: 0 0 0 7px rgba(255,255,255,.17); }
.arch-door { display: inline-block; width: 50%; height: 100%; background: linear-gradient(100deg, #f8fcff, #a7cbe9); border: 1px solid #80acd4; }
.arch-ground { position: absolute; bottom: 0; width: 100%; height: 10px; background: #17416c; }
.about-stamp { position: absolute; z-index: 3; right: 20px; top: 20px; display: flex; align-items: center; gap: 9px; padding: 11px 13px; border-radius: 10px; background: #fff; color: var(--blue); box-shadow: 0 10px 30px rgba(12,57,101,.15); }
.about-stamp span { font-weight: 900; font-size: 23px; letter-spacing: -.07em; }
.about-stamp small { color: var(--ink); font-size: 8px; line-height: 1.3; font-weight: 800; letter-spacing: .1em; }
.about-caption { display: flex; align-items: center; gap: 11px; margin-top: 16px; color: var(--muted); font-size: 11px; }
.caption-line { width: 31px; height: 2px; background: var(--blue); }
.about-copy h2 { margin-bottom: 20px; }
.about-copy > p { color: var(--muted); font-size: 13px; line-height: 1.9; margin-bottom: 13px; }
.check-list { display: grid; gap: 12px; list-style: none; padding: 0; margin: 25px 0 28px; }
.check-list li { display: flex; align-items: start; gap: 10px; font-size: 12px; font-weight: 700; color: #30465c; }
.check-list li span { display: grid; place-items: center; flex-shrink: 0; width: 19px; height: 19px; border-radius: 50%; background: #dceeff; color: var(--blue); font-size: 11px; }
.why-section { color: #fff; background: linear-gradient(115deg, #061f3d, #0b4f9c); }
.center-heading { max-width: 650px; margin: 0 auto 48px; text-align: center; }
.center-heading .eyebrow { justify-content: center; }
.center-heading h2 { color: #fff; margin-top: 15px; }
.center-heading p { max-width: 530px; margin: 17px auto 0; color: #c5dcf4; font-size: 13px; line-height: 1.8; }
.why-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 0; }
.why-item { padding: 8px 24px 8px; border-right: 1px solid rgba(255,255,255,.18); }
.why-item:first-child { padding-left: 0; }
.why-item:last-child { border-right: 0; padding-right: 0; }
.why-icon { width: 44px; height: 44px; display: grid; place-items: center; border: 1px solid rgba(176,218,255,.5); border-radius: 12px; color: #a9d9ff; font-size: 25px; }
.why-item h3 { margin: 20px 0 8px; font-size: 15px; }
.why-item p { margin: 0; color: #c1d7ed; font-size: 12px; line-height: 1.8; }
.process-section { background: #fff; }
.process-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 25px; }
.process-step { position: relative; }
.step-no { color: var(--blue); font-size: 12px; font-weight: 900; letter-spacing: .08em; }
.step-line { height: 1px; margin: 17px 0 19px; background: #cdddeb; position: relative; }
.step-line::before { content: ""; position: absolute; top: -4px; left: 0; width: 9px; height: 9px; border-radius: 50%; background: var(--blue); box-shadow: 0 0 0 4px #e5f2ff; }
.process-step h3 { margin-bottom: 8px; font-size: 16px; }
.process-step p { max-width: 230px; color: var(--muted); font-size: 12px; line-height: 1.8; }
.contact-section { color: #fff; background: linear-gradient(115deg, #08294f, #0b4f9c); }
.contact-layout { display: grid; grid-template-columns: 1fr .82fr; gap: 90px; align-items: start; }
.contact-copy { padding-top: 24px; }
.contact-copy h2 { color: #fff; margin-bottom: 18px; }
.contact-copy > p { max-width: 450px; color: #c7def4; font-size: 14px; line-height: 1.8; }
.contact-details { display: grid; gap: 20px; margin-top: 35px; }
.contact-detail { display: flex; align-items: center; gap: 13px; }
.detail-icon { display: grid; place-items: center; width: 43px; height: 43px; border: 1px solid rgba(185,220,255,.35); border-radius: 12px; color: #bfe2ff; font-size: 21px; }
.contact-detail small, .contact-detail strong, .contact-detail em { display: block; }
.contact-detail small { color: #b5d2ee; font-size: 10px; }
.contact-detail strong { font-size: 14px; margin-top: 2px; }
.contact-detail em { color: #c7def4; font-style: normal; font-size: 11px; margin-top: 2px; }
.contact-form { padding: 30px; border-radius: 16px; background: #fff; color: var(--ink); box-shadow: 0 22px 55px rgba(0,0,0,.15); }
.contact-form h3 { font-size: 22px; letter-spacing: -.03em; margin-bottom: 5px; }
.contact-form > p { color: var(--muted); font-size: 12px; margin-bottom: 22px; }
.contact-form label { display: block; margin: 13px 0 6px; font-size: 11px; font-weight: 800; color: #30465c; }
.contact-form input, .contact-form select, .contact-form textarea { display: block; width: 100%; border: 1px solid #dce6f0; border-radius: 7px; padding: 11px 12px; color: var(--ink); background: #fbfdff; outline: none; font-size: 12px; }
.contact-form input:focus, .contact-form select:focus, .contact-form textarea:focus { border-color: #6eace9; box-shadow: 0 0 0 3px rgba(28,116,207,.1); }
.contact-form textarea { resize: vertical; }
.form-button { width: 100%; margin-top: 19px; border: 0; }
.form-note { display: block; margin-top: 11px; text-align: center; color: #7b8998; font-size: 10px; }
.site-footer { background: #041b34; color: #fff; }
.footer-main { display: flex; align-items: center; gap: 30px; padding-top: 28px; padding-bottom: 28px; }
.footer-brand { color: #fff; }
.footer-brand small { color: #93caff; }
.footer-main > p { margin: 0 auto 0 0; color: #b7cce1; font-size: 11px; }
.footer-whatsapp { display: inline-flex; align-items: center; gap: 10px; padding: 10px 14px; border: 1px solid rgba(185,220,255,.3); border-radius: 7px; font-size: 11px; font-weight: 800; }
.footer-bottom { display: flex; justify-content: space-between; gap: 20px; padding-top: 17px; padding-bottom: 20px; border-top: 1px solid rgba(255,255,255,.12); color: #91a8bf; font-size: 10px; }
.floating-whatsapp { position: fixed; z-index: 30; right: 20px; bottom: 20px; display: grid; place-items: center; width: 54px; height: 54px; border-radius: 50%; background: #18a968; box-shadow: 0 8px 25px rgba(0,0,0,.2); transition: .2s; }
.floating-whatsapp:hover { transform: translateY(-3px); }
.floating-whatsapp svg { width: 26px; height: 26px; fill: #fff; }
@media (max-width: 950px) {
  .nav { gap: 18px; }
  .hero-layout { gap: 15px; min-height: 540px; }
  .hero-visual { transform: scale(.92); transform-origin: center; }
  .about-layout { gap: 42px; }
  .contact-layout { gap: 42px; }
  .service-card { padding: 21px; }
}
@media (max-width: 760px) {
  .container { width: min(100% - 32px, 560px); }
  .topbar-inner { min-height: 34px; font-size: 10px; }
  .topbar-inner span { max-width: 62%; }
  .topbar-inner a { white-space: nowrap; }
  .nav-wrap { min-height: 70px; }
  .brand img { width: 41px; height: 41px; }
  .brand strong { font-size: 14px; }
  .brand small { font-size: 9px; }
  .menu-toggle { display: block; }
  .nav { display: none; position: absolute; top: 70px; left: 0; right: 0; padding: 18px 22px 22px; background: #fff; border-bottom: 1px solid var(--line); box-shadow: 0 16px 25px rgba(7,42,79,.08); flex-direction: column; align-items: stretch; gap: 0; }
  .nav.open { display: flex; }
  .nav > a:not(.nav-cta) { padding: 12px 0; border-bottom: 1px solid #edf2f7; }
  .nav-cta { justify-content: center; margin-top: 14px; }
  .hero-layout { grid-template-columns: 1fr; gap: 0; padding-top: 58px; padding-bottom: 28px; }
  .hero-copy { padding-bottom: 0; }
  .hero h1 { font-size: clamp(40px, 10vw, 57px); margin-top: 21px; }
  .hero-text { font-size: 14px; max-width: 440px; }
  .hero-visual { min-height: 350px; transform: none; margin-top: 7px; }
  .lift-illustration { width: 340px; max-width: 100%; height: 340px; }
  .building-back { height: 88%; }
  .lift-frame { height: 75%; }
  .visual-glow { width: 290px; height: 290px; }
  .orbit-one { width: 290px; height: 290px; left: 7%; }
  .orbit-two { width: 225px; height: 225px; left: 17%; }
  .label-top { top: 8%; right: 0; }
  .label-bottom { bottom: 5%; left: -1%; }
  .service-strip .strip-grid { grid-template-columns: 1fr; padding-top: 7px; padding-bottom: 7px; }
  .strip-grid > div, .strip-grid > div:first-child { padding: 13px 0; border-right: 0; border-bottom: 1px solid #e0eaf4; }
  .strip-grid > div:last-child { border-bottom: 0; }
  .section { padding: 70px 0; }
  .section-heading { display: block; margin-bottom: 30px; }
  .section-heading h2, .about-copy h2, .center-heading h2, .contact-copy h2 { font-size: 33px; }
  .section-heading > p { margin-top: 16px; font-size: 13px; }
  .service-cards { grid-template-columns: 1fr; gap: 13px; }
  .service-card { min-height: 0; padding: 23px; }
  .service-card p { max-width: 430px; }
  .about-layout { grid-template-columns: 1fr; gap: 38px; }
  .about-photo-frame { min-height: 340px; }
  .about-copy { order: -1; }
  .why-grid { grid-template-columns: repeat(2, 1fr); gap: 28px 20px; }
  .why-item, .why-item:first-child, .why-item:last-child { padding: 0; border: 0; }
  .why-item h3 { margin-top: 14px; }
  .process-grid { grid-template-columns: repeat(2, 1fr); gap: 15px 22px; }
  .process-step p { font-size: 11px; }
  .contact-layout { grid-template-columns: 1fr; gap: 34px; }
  .contact-copy { padding-top: 0; }
  .contact-form { padding: 24px 20px; }
  .footer-main { flex-wrap: wrap; gap: 17px; }
  .footer-main > p { order: 3; width: 100%; }
  .footer-whatsapp { margin-left: auto; }
  .footer-bottom { flex-direction: column; gap: 7px; }
}
@media (max-width: 390px) {
  .topbar-inner { font-size: 9px; }
  .hero-actions { flex-direction: column; align-items: stretch; }
  .hero-actions .button { width: 100%; }
  .hero-trust span { font-size: 10px; }
  .hero-visual { min-height: 310px; }
  .lift-illustration { height: 305px; }
  .hero-card { padding: 9px 10px; }
  .label-symbol, .label-check { width: 27px; height: 27px; }
  .card-label strong { font-size: 10px; }
  .card-label small { font-size: 9px; }
  .process-grid { grid-template-columns: 1fr; }
  .step-line { margin: 11px 0 13px; }
}
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { scroll-behavior: auto !important; transition: none !important; }
}
'''

files["script.js"] = r'''const menuToggle = document.getElementById("menuToggle");
const mainNav = document.getElementById("mainNav");

if (menuToggle && mainNav) {
  menuToggle.addEventListener("click", () => {
    const isOpen = mainNav.classList.toggle("open");
    menuToggle.setAttribute("aria-expanded", String(isOpen));
    menuToggle.setAttribute("aria-label", isOpen ? "Close navigation menu" : "Open navigation menu");
  });

  mainNav.querySelectorAll("a").forEach((link) => {
    link.addEventListener("click", () => {
      mainNav.classList.remove("open");
      menuToggle.setAttribute("aria-expanded", "false");
      menuToggle.setAttribute("aria-label", "Open navigation menu");
    });
  });
}

const yearElement = document.getElementById("year");
if (yearElement) yearElement.textContent = new Date().getFullYear();

const quoteForm = document.getElementById("quoteForm");
if (quoteForm) {
  quoteForm.addEventListener("submit", (event) => {
    event.preventDefault();

    const name = document.getElementById("name").value.trim();
    const phone = document.getElementById("phone").value.trim();
    const service = document.getElementById("service").value;
    const message = document.getElementById("message").value.trim();

    if (!name || !phone || !service) {
      quoteForm.reportValidity();
      return;
    }

    const whatsappMessage = [
      "Assalam-o-Alaikum, Peshawar Elevators.",
      "",
      "I would like to make an enquiry.",
      "Name: " + name,
      "Phone: " + phone,
      "Service: " + service,
      "Details: " + (message || "Not provided"),
    ].join("\n");

    const whatsappUrl = "https://wa.me/923350949648?text=" + encodeURIComponent(whatsappMessage);
    window.open(whatsappUrl, "_blank", "noopener,noreferrer");
  });
}
'''

files["assets/logo.svg"] = r'''<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
  <rect width="100" height="100" rx="20" fill="#0b4f9c"/>
  <path d="M18 78V22h64v56" fill="none" stroke="#d8ecff" stroke-width="4" stroke-linejoin="round"/>
  <path d="M28 78V32h44v46" fill="#ffffff" fill-opacity=".12" stroke="#ffffff" stroke-width="3"/>
  <path d="M50 33v45" stroke="#ffffff" stroke-width="2"/>
  <path d="M32 28h36" stroke="#8fd0ff" stroke-width="4" stroke-linecap="round"/>
  <path d="M36 48h7M57 48h7M36 58h7M57 58h7" stroke="#8fd0ff" stroke-width="3" stroke-linecap="round"/>
  <circle cx="50" cy="13" r="4" fill="#8fd0ff"/>
</svg>
'''

files["README.md"] = r'''# Peshawar Elevators Website

A responsive, static website for Peshawar Elevators, designed for free GitHub Pages hosting.

## Files

- `index.html` — page content and sections
- `styles.css` — responsive blue-and-white design
- `script.js` — mobile navigation, current year, and WhatsApp enquiry form
- `assets/logo.svg` — simple vector logo

## Before publishing

1. Check the phone number and WhatsApp number in `index.html` and `script.js`.
2. Review the service descriptions and contact details.
3. Add real project photos later if you wish. This version uses a lightweight custom illustration, so no external image hosting is required.

## Publish from an Android phone

1. Open https://github.com and sign in or create a free account.
2. Tap **+** then **New repository**.
3. Name the repository exactly `YOUR-USERNAME.github.io` (replace `YOUR-USERNAME` with your GitHub username).
4. Set it to **Public** and create the repository.
5. Open the repository and upload the website files. Upload `index.html`, `styles.css`, `script.js`, `README.md`, and the `assets` folder containing `logo.svg`. Keep the folder structure unchanged.
6. Open **Settings → Pages**.
7. Under **Build and deployment**, choose **Deploy from a branch**.
8. Choose branch **main** and folder **/(root)**, then save.
9. Wait a few minutes. Your website should appear at `https://YOUR-USERNAME.github.io`.

If you use a repository name other than `YOUR-USERNAME.github.io`, the URL will normally be `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`. The relative file paths in this site support that setup too.

## WhatsApp form

The quotation form opens WhatsApp with a prefilled message. It does not save customer information on a server. Confirm the WhatsApp number before publishing.

## Important

GitHub Pages hosts static sites. This website does not include a database, user accounts, or server-side form storage.
'''

for rel, content in files.items():
    path = root / rel
    path.parent.mkdir(parents=True, exist_ok=True)
    path.write_text(content, encoding="utf-8")

zip_path = Path("/mnt/data/peshawar-elevators-website.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    for path in root.rglob("*"):
        if path.is_file():
            z.write(path, path.relative_to(root.parent))

print("Created website files:")
for path in sorted(root.rglob("*")):
    if path.is_file():
        print(f"- {path.relative_to(root)} ({path.stat().st_size:,} bytes)")
print(f"\nZIP archive: {zip_path} ({zip_path.stat().st_size:,} bytes)")
