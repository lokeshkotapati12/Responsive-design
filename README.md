<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Spice Garden Restaurant | Authentic Flavors</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    :root {
      --bg: #0b1120;
      --bg-alt: #020617;
      --accent: #f97316;
      --accent-soft: rgba(249, 115, 22, 0.12);
      --text: #e5e7eb;
      --muted: #9ca3af;
      --card: #020617;
      --border: #1f2937;
      --radius: 16px;
      --shadow: 0 18px 45px rgba(0, 0, 0, 0.55);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
      background: radial-gradient(circle at top, #111827, #020617 45%);
      color: var(--text);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    /* Layout */
    .page {
      min-height: 100vh;
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 1.25rem 3rem;
    }

    /* Header / Nav */
    header {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(18px);
      background: linear-gradient(
        to bottom,
        rgba(15, 23, 42, 0.95),
        rgba(15, 23, 42, 0.8),
        transparent
      );
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.8rem 0.2rem;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .logo {
      width: 36px;
      height: 36px;
      border-radius: 12px;
      background: radial-gradient(circle at 30% 20%, #f97316, #7c2d12);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 800;
      font-size: 1rem;
      box-shadow: 0 0 0 2px rgba(15, 23, 42, 0.9);
    }

    .brand-text strong {
      font-size: 1rem;
    }

    .brand-text span {
      font-size: 0.75rem;
      color: var(--muted);
    }

    .nav-links {
      display: flex;
      gap: 0.85rem;
      font-size: 0.9rem;
    }

    .nav-links a {
      padding: 0.35rem 0.8rem;
      border-radius: 999px;
      border: 1px solid transparent;
      color: var(--muted);
      transition: all 0.18s ease;
    }

    .nav-links a:hover {
      border-color: rgba(148, 163, 184, 0.5);
      color: var(--text);
      background: rgba(15, 23, 42, 0.9);
    }

    .nav-cta {
      padding: 0.4rem 0.9rem;
      border-radius: 999px;
      border: none;
      background: var(--accent);
      color: #111827;
      font-size: 0.85rem;
      font-weight: 600;
      cursor: pointer;
      transition: transform 0.15s ease, box-shadow 0.15s ease;
      white-space: nowrap;
    }

    .nav-cta:hover {
      transform: translateY(-1px);
      box-shadow: 0 8px 22px rgba(249, 115, 22, 0.4);
    }

    /* Hamburger (mobile) */
    .hamburger {
      display: none;
      flex-direction: column;
      gap: 4px;
      cursor: pointer;
    }

    .hamburger span {
      width: 22px;
      height: 2px;
      background: #e5e7eb;
      border-radius: 999px;
    }

    .mobile-menu {
      display: none;
      flex-direction: column;
      gap: 0.4rem;
      padding: 0.6rem 0.2rem 0.9rem;
    }

    .mobile-menu a,
    .mobile-menu button {
      width: 100%;
      text-align: left;
    }

    .mobile-menu .nav-cta {
      text-align: center;
    }

    /* Hero */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.7fr) minmax(0, 1.4fr);
      gap: 1.8rem;
      align-items: center;
      padding: 2.4rem 0 2rem;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      font-size: 0.8rem;
      padding: 0.25rem 0.6rem;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.5);
      background: rgba(15, 23, 42, 0.95);
      color: var(--muted);
      margin-bottom: 0.7rem;
    }

    .hero-badge-dot {
      width: 8px;
      height: 8px;
      border-radius: 999px;
      background: #22c55e;
      box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.25);
    }

    .hero h1 {
      font-size: clamp(2.1rem, 3.2vw, 2.7rem);
      line-height: 1.18;
      margin-bottom: 0.6rem;
    }

    .gradient-text {
      background: linear-gradient(120deg, #f97316, #facc15);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero p {
      font-size: 0.98rem;
      color: #d1d5db;
      max-width: 32rem;
      margin-bottom: 1.5rem;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin-bottom: 1.3rem;
    }

    .btn {
      border-radius: 999px;
      padding: 0.6rem 1.3rem;
      border: 1px solid rgba(148, 163, 184, 0.6);
      font-size: 0.9rem;
      cursor: pointer;
      background: transparent;
      color: var(--text);
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      transition: all 0.18s ease;
    }

    .btn-primary {
      background: radial-gradient(circle at 0 0, #f97316, #7c2d12);
      border-color: transparent;
      box-shadow: var(--shadow);
      color: #111827;
      font-weight: 600;
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      box-shadow: 0 22px 45px rgba(0, 0, 0, 0.9);
    }

    .btn-outline:hover {
      background: rgba(15, 23, 42, 0.9);
    }

    .hero-meta {
      font-size: 0.8rem;
      color: var(--muted);
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
    }

    .hero-meta span {
      display: inline-flex;
      align-items: center;
      gap: 0.25rem;
    }

    .hero-image-card {
      border-radius: var(--radius);
      background: radial-gradient(circle at top, #7c2d12, #020617);
      padding: 1.1rem;
      box-shadow: var(--shadow);
      border: 1px solid rgba(148, 163, 184, 0.45);
      position: relative;
      overflow: hidden;
    }

    .hero-image-main {
      border-radius: 12px;
      height: 220px;
      background-image: linear-gradient(
          to bottom,
          rgba(15, 23, 42, 0.25),
          rgba(15, 23, 42, 0.7)
        ),
        url("https://images.pexels.com/photos/262978/pexels-photo-262978.jpeg");
      background-size: cover;
      background-position: center;
      margin-bottom: 0.8rem;
    }

    .hero-image-card p {
      font-size: 0.85rem;
      color: #fee2e2;
    }

    .hero-badge-floating {
      position: absolute;
      bottom: 1.2rem;
      right: 1.2rem;
      font-size: 0.78rem;
      padding: 0.35rem 0.7rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.9);
      border: 1px solid rgba(248, 250, 252, 0.2);
    }

    /* Sections */
    section {
      margin-top: 2.2rem;
    }

    .section-shell {
      border-radius: var(--radius);
      background: radial-gradient(circle at top left, #020617, #020617);
      border: 1px solid rgba(15, 23, 42, 0.95);
      box-shadow: var(--shadow);
      padding: 1.6rem 1.3rem 1.7rem;
    }

    .section-header {
      margin-bottom: 1rem;
    }

    .section-eyebrow {
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: var(--muted);
      margin-bottom: 0.25rem;
    }

    .section-title {
      font-size: 1.3rem;
      margin-bottom: 0.1rem;
    }

    .section-subtitle {
      font-size: 0.9rem;
      color: var(--muted);
    }

    /* About / Highlights */
    .about-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.7fr) minmax(0, 1.3fr);
      gap: 1.4rem;
      margin-top: 0.6rem;
    }

    .about-text {
      font-size: 0.95rem;
      color: #e5e7eb;
    }

    .about-text p + p {
      margin-top: 0.7rem;
    }

    .highlights {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
      gap: 0.6rem;
      margin-top: 0.9rem;
    }

    .highlight-card {
      border-radius: 12px;
      border: 1px solid var(--border);
      padding: 0.7rem 0.8rem;
      background: #020617;
      font-size: 0.85rem;
    }

    .highlight-number {
      font-size: 1.1rem;
      font-weight: 600;
      color: var(--accent);
    }

    .highlight-label {
      font-size: 0.8rem;
      color: var(--muted);
    }

    .opening-hours {
      font-size: 0.9rem;
      border-radius: 12px;
      padding: 0.8rem 0.9rem;
      background: var(--accent-soft);
      border: 1px dashed rgba(248, 250, 252, 0.35);
      color: #fed7aa;
    }

    .opening-hours strong {
      display: block;
      margin-bottom: 0.3rem;
    }

    /* Menu */
    .menu-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.7fr) minmax(0, 1.3fr);
      gap: 1.5rem;
      margin-top: 0.8rem;
    }

    .menu-category {
      margin-bottom: 1.1rem;
    }

    .menu-category h3 {
      font-size: 1rem;
      margin-bottom: 0.4rem;
    }

    .menu-items {
      display: flex;
      flex-direction: column;
      gap: 0.55rem;
    }

    .menu-item {
      display: flex;
      justify-content: space-between;
      gap: 0.7rem;
      font-size: 0.9rem;
    }

    .menu-item-main {
      flex: 1;
    }

    .menu-item-name {
      font-weight: 500;
    }

    .menu-item-desc {
      font-size: 0.8rem;
      color: var(--muted);
    }

    .menu-item-price {
      white-space: nowrap;
      font-weight: 500;
      color: #fed7aa;
    }

    .menu-note {
      font-size: 0.8rem;
      color: var(--muted);
      margin-top: 0.4rem;
    }

    .menu-side-card {
      border-radius: 12px;
      padding: 0.9rem;
      border: 1px dashed var(--border);
      background: #020617;
      font-size: 0.88rem;
      color: var(--muted);
    }

    .menu-side-card strong {
      color: #fed7aa;
    }

    /* Testimonials */
    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 0.9rem;
      margin-top: 0.8rem;
    }

    .testimonial-card {
      border-radius: 12px;
      padding: 0.9rem;
      border: 1px solid var(--border);
      background: #020617;
      font-size: 0.88rem;
    }

    .testimonial-name {
      font-weight: 500;
      margin-top: 0.5rem;
    }

    .testimonial-meta {
      font-size: 0.78rem;
      color: var(--muted);
    }

    /* Contact & Location */
    .contact-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.6fr) minmax(0, 1.4fr);
      gap: 1.4rem;
      margin-top: 0.8rem;
    }

    form {
      display: grid;
      gap: 0.7rem;
      font-size: 0.86rem;
    }

    label {
      font-size: 0.78rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.16em;
      margin-bottom: 0.18rem;
      display: block;
    }

    input,
    textarea,
    select {
      width: 100%;
      border-radius: 11px;
      border: 1px solid var(--border);
      padding: 0.55rem 0.7rem;
      background: rgba(15, 23, 42, 0.96);
      color: var(--text);
      font: inherit;
      resize: vertical;
      min-height: 40px;
    }

    textarea {
      min-height: 110px;
    }

    input:focus,
    textarea:focus,
    select:focus {
      outline: none;
      border-color: var(--accent);
      box-shadow: 0 0 0 1px rgba(249, 115, 22, 0.7);
    }

    .info-card {
      border-radius: 12px;
      padding: 0.9rem;
      border: 1px solid var(--border);
      background: #020617;
      font-size: 0.9rem;
      color: var(--muted);
      display: flex;
      flex-direction: column;
      gap: 0.7rem;
    }

    .info-row {
      display: flex;
      justify-content: space-between;
      gap: 0.7rem;
      flex-wrap: wrap;
      font-size: 0.86rem;
    }

    .info-row span:first-child {
      color: #e5e7eb;
    }

    .map-placeholder {
      border-radius: 10px;
      border: 1px dashed var(--border);
      padding: 0.6rem;
      font-size: 0.8rem;
      text-align: center;
      color: var(--muted);
    }

    .info-card a {
      color: #fed7aa;
      text-decoration: underline;
      text-decoration-style: dotted;
    }

    footer {
      margin-top: 2rem;
      padding-top: 1.2rem;
      border-top: 1px solid rgba(31, 41, 55, 0.9);
      font-size: 0.8rem;
      color: var(--muted);
      text-align: center;
    }

    footer span {
      color: #fec89a;
    }

    /* Responsive */
    @media (max-width: 880px) {
      .hero,
      .about-grid,
      .menu-grid,
      .contact-grid {
        grid-template-columns: minmax(0, 1fr);
      }

      .hero {
        padding-top: 1.6rem;
      }
    }

    @media (max-width: 720px) {
      .nav-links,
      .nav-cta {
        display: none;
      }

      .hamburger {
        display: flex;
      }

      .mobile-menu.open {
        display: flex;
      }

      .section-shell {
        padding-inline: 1.05rem;
      }

      .page {
        padding-inline: 1rem;
      }
    }

    @media (max-width: 480px) {
      .hero {
        padding-top: 1.2rem;
      }

      .hero-image-main {
        height: 190px;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="page">
      <nav class="nav">
        <div class="brand">
          <div class="logo">SG</div>
          <div class="brand-text">
            <strong>Spice Garden</strong>
            <span>Authentic Indian Restaurant</span>
          </div>
        </div>
        <div class="nav-links">
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#menu">Menu</a>
          <a href="#testimonials">Reviews</a>
          <a href="#contact">Contact</a>
          <button class="nav-cta" onclick="scrollToSection('contact')">
            Book a Table
          </button>
        </div>
        <div class="hamburger" id="hamburger">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </nav>
      <div class="mobile-menu" id="mobileMenu">
        <a href="#home" onclick="toggleMenu()">Home</a>
        <a href="#about" onclick="toggleMenu()">About</a>
        <a href="#menu" onclick="toggleMenu()">Menu</a>
        <a href="#testimonials" onclick="toggleMenu()">Reviews</a>
        <a href="#contact" onclick="toggleMenu()">Contact</a>
        <button class="nav-cta" onclick="toggleMenu(); scrollToSection('contact');">
          Book a Table
        </button>
      </div>
    </div>
  </header>

  <main class="page">
    <!-- Hero -->
    <section id="home" class="section-shell" style="margin-top: 1.4rem;">
      <div class="hero">
        <div>
          <div class="hero-badge">
            <span class="hero-badge-dot"></span>
            Open today • Dine-in • Takeaway • Delivery
          </div>
          <h1>
            Experience <span class="gradient-text">bold flavors</span> with a
            homely touch at Spice Garden.
          </h1>
          <p>
            A cozy neighborhood restaurant serving freshly prepared Indian dishes,
            tandoor specials, and comforting desserts. Perfect for family dinners,
            quick lunches, and weekend celebrations.
          </p>
          <div class="hero-actions">
            <button class="btn btn-primary" onclick="scrollToSection('contact')">
              Reserve a Table
            </button>
            <button class="btn btn-outline" onclick="scrollToSection('menu')">
              View Menu
            </button>
          </div>
          <div class="hero-meta">
            <span>⭐ 4.7/5 rating from local customers</span>
            <span>•</span>
            <span>👨‍👩‍👧 Family-friendly ambience</span>
          </div>
        </div>
        <aside class="hero-image-card">
          <div class="hero-image-main"></div>
          <p>
            “We prepare every dish with fresh ingredients, aromatic spices,
            and the same care as a home-cooked meal.”
          </p>
          <div class="hero-badge-floating">
            Today’s special: Paneer Tikka Sizzler 🌶️
          </div>
        </aside>
      </div>
    </section>

    <!-- About -->
    <section id="about">
      <div class="section-shell">
        <div class="section-header">
          <div class="section-eyebrow">Our Story</div>
          <div class="section-title">Locally loved, lovingly cooked.</div>
          <div class="section-subtitle">
            Serving the neighborhood with delicious meals since 2015.
          </div>
        </div>
        <div class="about-grid">
          <div class="about-text">
            <p>
              Spice Garden is a local family-run restaurant that brings together
              traditional recipes and modern flavors. From sizzling tikkas to
              creamy curries, every plate is made to order in our open kitchen.
            </p>
            <p>
              Whether you're stopping by for a quick lunch, planning a family
              dinner, or celebrating a special occasion, our team is here to make
              you feel at home.
            </p>
            <div class="highlights">
              <div class="highlight-card">
                <div class="highlight-number">10+</div>
                <div class="highlight-label">Signature House Specials</div>
              </div>
              <div class="highlight-card">
                <div class="highlight-number">30+</div>
                <div class="highlight-label">Fresh Dishes Daily</div>
              </div>
              <div class="highlight-card">
                <div class="highlight-number">4.7★</div>
                <div class="highlight-label">Average Customer Rating</div>
              </div>
            </div>
          </div>
          <div class="opening-hours">
            <strong>Opening Hours</strong>
            Monday – Friday: 12:00 PM – 11:00 PM<br />
            Saturday – Sunday: 11:00 AM – 11:30 PM<br /><br />
            <strong>Address</strong>
            21 Food Street, Lakeview Circle,<br />
            Your City, 500001<br /><br />
            <strong>Call us</strong>
            +91-98765 43210
          </div>
        </div>
      </div>
    </section>

    <!-- Menu -->
    <section id="menu">
      <div class="section-shell">
        <div class="section-header">
          <div class="section-eyebrow">Menu Highlights</div>
          <div class="section-title">Handpicked favorites you’ll love.</div>
          <div class="section-subtitle">
            A glimpse of our most popular dishes. Full menu available at the restaurant.
          </div>
        </div>
        <div class="menu-grid">
          <div>
            <div class="menu-category">
              <h3>Starters</h3>
              <div class="menu-items">
                <div class="menu-item">
                  <div class="menu-item-main">
                    <div class="menu-item-name">Paneer Tikka</div>
                    <div class="menu-item-desc">
                      Cottage cheese cubes marinated in spices and grilled in the tandoor.
                    </div>
                  </div>
                  <div class="menu-item-price">₹220</div>
                </div>
                <div class="menu-item">
                  <div class="menu-item-main">
                    <div class="menu-item-name">Crispy Corn</div>
                    <div class="menu-item-desc">
                      Fried sweet corn tossed with herbs, spices, and lemon.
                    </div>
                  </div>
                  <div class="menu-item-price">₹180</div>
                </div>
              </div>
            </div>

            <div class="menu-category">
              <h3>Main Course</h3>
              <div class="menu-items">
                <div class="menu-item">
                  <div class="menu-item-main">
                    <div class="menu-item-name">Butter Chicken</div>
                    <div class="menu-item-desc">
                    <div class="menu-item-price">₹320</div>
                </div>
                <div class="menu-item">
                  <div class="menu-item-main">
                    <div class="menu-item-name">Veg Dum Biryani</div>
                    <div class="menu-item-desc">
                      Long-grain basmati rice slow-cooked with fresh vegetables and spices.
                    </div>
                  </div>
                  <div class="menu-item-price">₹260</div>
                </div>
              </div>
            </div>

            <div class="menu-category">
              <h3>Breads & Desserts</h3>
              <div class="menu-items">
                <div class="menu-item">
                  <div class="menu-item-main">
                    <div class="menu-item-name">Butter Naan</div>
                    <div class="menu-item-desc">
                      Soft tandoor-baked bread brushed with butter.
                    </div>
                  </div>
                  <div class="menu-item-price">₹60</div>
                </div>
                <div class="menu-item">
                  <div class="menu-item-main">
                    <div class="menu-item-name">Gulab Jamun (2 pcs)</div>
                    <div class="menu-item-desc">
                      Warm, soft dumplings soaked in cardamom syrup.
                    </div>
                  </div>
                  <div class="menu-item-price">₹90</div>
                </div>
              </div>
            </div>

            <p class="menu-note">
              Prices are indicative and may vary slightly. Please check at the outlet for the latest menu.
            </p>
          </div>

          <aside class="menu-side-card">
            <p>
              <strong>Special Requests?</strong><br />
              We’re happy to adjust spice levels and customize meals for kids or senior
              guests. Just let our staff know your preferences.
            </p>
            <br />
            <p>
              <strong>Party Orders & Catering</strong><br />
              Hosting a house party or office lunch? We provide bulk orders and catering
              services for groups of 20+ people.
            </p>
            <br />
            <p>
              Call or WhatsApp us at <strong>+91-98765 43210</strong> to discuss your event.
            </p>
          </aside>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section id="testimonials">
      <div class="section-shell">
        <div class="section-header">
          <div class="section-eyebrow">Customer Reviews</div>
          <div class="section-title">Loved by the neighborhood.</div>
          <div class="section-subtitle">
            Here’s what some of our regular guests have to say.
          </div>
        </div>
        <div class="testimonials-grid">
          <div class="testimonial-card">
            “One of the best butter chickens I’ve had in the city. The staff is polite and
            service is quick. We keep coming back every month!”
            <div class="testimonial-name">— Rohan Mehta</div>
            <div class="testimonial-meta">Local Guide • Dine-in</div>
          </div>
          <div class="testimonial-card">
            “Perfect place for family dinners. Their veg biryani and paneer tikka are
            must-try dishes. Cozy, clean, and family-friendly.”
            <div class="testimonial-name">— Anjali Sharma</div>
            <div class="testimonial-meta">Regular Customer • Takeaway</div>
          </div>
          <div class="testimonial-card">
            “We ordered catering for a birthday party. Great quantity, delicious taste,
            and delivered on time. Highly recommended!”
            <div class="testimonial-name">— Vikram Rao</div>
            <div class="testimonial-meta">Catering Order</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <div class="section-shell">
        <div class="section-header">
          <div class="section-eyebrow">Contact & Reservations</div>
          <div class="section-title">Book a table or say hello.</div>
          <div class="section-subtitle">
            Fill the form below and we’ll confirm your reservation shortly.
          </div>
        </div>
        <div class="contact-grid">
          <!-- Simple front-end form (no backend, just demo) -->
          <form onsubmit="handleFormSubmit(event)">
            <div>
              <label for="name">Name</label>
              <input
                id="name"
                name="name"
                type="text"
                placeholder="Your full name"
                required
              />
            </div>
            <div>
              <label for="phone">Phone</label>
              <input
                id="phone"
                name="phone"
                type="tel"
                placeholder="Your phone number"
                required
              />
            </div>
            <div>
              <label for="guests">Guests</label>
              <select id="guests" name="guests" required>
                <option value="">Select number of guests</option>
                <option>1–2</option>
                <option>3–4</option>
                <option>5–8</option>
                <option>9–12</option>
                <option>More than 12</option>
              </select>
            </div>
            <div>
              <label for="date">Date & Time</label>
              <input id="date" name="date" type="datetime-local" required />
            </div>
            <div>
              <label for="message">Message (optional)</label>
              <textarea
                id="message"
                name="message"
                placeholder="Any special requests? (e.g. birthday, no onion, etc.)"
              ></textarea>
            </div>
            <button type="submit" class="btn btn-primary">
              Submit Reservation Request
            </button>
            <div
              id="formFeedback"
              style="font-size:0.8rem;color:#bbf7d0;margin-top:0.4rem;display:none;"
            >
              Thank you! Your request has been recorded (demo only).
            </div>
          </form>

          <aside class="info-card">
            <div class="info-row">
              <span>Phone</span>
              <span>+91-98765 43210</span>
            </div>
            <div class="info-row">
              <span>Email</span>
              <span>hello@spicegardenlocal.com</span>
            </div>
            <div class="info-row">
              <span>Address</span>
              <span>21 Food Street, Lakeview Circle, Your City, 500001</span>
            </div>
            <div class="map-placeholder">
              Map placeholder – you can embed a real Google Map iframe here.
            </div>
            <div>
              <strong>Follow us</strong><br />
              <a href="#">Instagram</a> • <a href="#">Facebook</a> •
              <a href="#">Zomato</a>
            </div>
          </aside>
        </div>
      </div>
    </section>

    <footer>
      © <span id="year"></span> Spice Garden Restaurant. All rights reserved.
    </footer>
  </main>

  <script>
    // Smooth scroll to sections
    function scrollToSection(id) {
      const el = document.getElementById(id);
      if (el) {
        el.scrollIntoView({ behavior: "smooth", block: "start" });
      }
    }

    // Mobile menu toggle
    const hamburger = document.getElementById("hamburger");
    const mobileMenu = document.getElementById("mobileMenu");

    function toggleMenu() {
      mobileMenu.classList.toggle("open");
    }

    hamburger.addEventListener("click", toggleMenu);

    // Reservation form demo handler
    function handleFormSubmit(event) {
      event.preventDefault();
      const feedback = document.getElementById("formFeedback");
      feedback.style.display = "block";

      // Reset form for demo
      event.target.reset();

      // Hide message after a few seconds
      setTimeout(() => {
        feedback.style.display = "none";
      }, 4000);
    }

    // Footer year
    document.getElementById("year").textContent =
      new Date().getFullYear();
  </script>
</body>
</html>
                      Tender chicken in a rich, creamy tomato gravy, mild and buttery.
                    </div>
                  </div>
