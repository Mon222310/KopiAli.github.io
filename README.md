<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kopi Ali Coffee Shop</title>
  <style>
    /* Global Styles */
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #fdf6f0;
      color: #3e2723;
    }
    header {
      background-color: #6f4e37;
      color: white;
      padding: 20px;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }
    nav a:hover {
      color: #ffcc80;
    }
    .hero {
      background: url('coffee-hero.jpg') no-repeat center center/cover;
      height: 400px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 3em;
      text-shadow: 2px 2px 5px #000;
    }
    .section {
      padding: 60px 20px;
      text-align: center;
    }
    .menu-items {
      display: flex;
      justify-content: center;
      gap: 30px;
      flex-wrap: wrap;
    }
    .menu-item {
      background: #fff;
      border-radius: 8px;
      padding: 20px;
      width: 220px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .menu-item:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 12px rgba(0,0,0,0.2);
    }
    form {
      max-width: 400px;
      margin: auto;
      display: flex;
      flex-direction: column;
      gap: 15px;
    }
    input, textarea, button {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 1em;
    }
    button {
      background-color: #6f4e37;
      color: white;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #4e342e;
    }
    footer {
      background-color: #6f4e37;
      color: white;
      text-align: center;
      padding: 20px;
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Kopi Ali Coffee Shop</h1>
    <nav>
      <a href="#menu">Menu</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <div class="hero">
    Freshly Brewed Happiness
  </div>

  <section id="menu" class="section">
    <h2>Our Favorites</h2>
    <div class="menu-items">
      <div class="menu-item">
        <h3>Espresso</h3>
        <p>Strong and bold, perfect kickstart.</p>
      </div>
      <div class="menu-item">
        <h3>Cappuccino</h3>
        <p>Rich espresso with frothy milk.</p>
      </div>
      <div class="menu-item">
        <h3>Iced Latte</h3>
        <p>Cool, smooth, and refreshing.</p>
      </div>
    </div>
  </section>

  <section id="about" class="section">
    <h2>About Us</h2>
    <p>At Kopi Ali, we blend tradition and modern craft to serve coffee that warms the soul. Our beans are locally sourced and roasted with care.</p>
  </section>

  <section id="contact" class="section">
    <h2>Contact Us</h2>
    <form id="contactForm">
      <input type="text" id="name" placeholder="Your Name" required>
      <input type="email" id="email" placeholder="Your Email" required>
      <textarea id="message" rows="4" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
    <p id="formMessage"></p>
  </section>

  <footer>
    <p>&copy; 2026 Kopi Ali Coffee Shop. All rights reserved.</p>
  </footer>

  <script>
    // Smooth scroll for navigation
    document.querySelectorAll('nav a').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({
          behavior: 'smooth'
        });
      });
    });

    // Contact form validation
    const form = document.getElementById('contactForm');
    const formMessage = document.getElementById('formMessage');

    form.addEventListener('submit', function(e) {
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();

      if (name && email && message) {
        formMessage.textContent = "Thank you, " + name + "! Your message has been sent.";
        formMessage.style.color = "green";
        form.reset();
      } else {
        formMessage.textContent = "Please fill out all fields.";
        formMessage.style.color = "red";
      }
    });
  </script>
</body>
</html>
