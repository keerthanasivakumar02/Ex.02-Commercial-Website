## Ex02 Commercial Website
## NAME: KEERTHANA S
## Date:11-03-2025
## AIM
To create a commercial website using CSS Flexbox.

## ALGORITHM
# STEP 1
Create an HTML file (index.html)

# STEP 2
Create a CSS file (style.css)

# STEP 3
Include a navigation bar with links to different sections.

# STEP 4
Add structured sections for Homepage, Products / Services, About Us, Contact Details and User Account.

# STEP 5
Include social media links at the footer with copyright information.

# STEP 6
Define global styles for fonts, colors, and layout.

# STEP 7
Style the header, navigation bar, and sections.

# STEP 8
Use Flexbox for layout design.

# STEP 9
Add hover effects and transitions for interactivity.

# STEP 10
Add Images and Media.

# STEP 11
Use optimized images for a professional look.

# STEP 12
Open the HTML file in a browser to check layout and functionality.

# STEP 13
Fix styling issues and refine content placement.

# STEP 14
Deploy the website.

# STEP 15
Upload to GitHub Pages for free hosting.

## PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Codenvy</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background-color: #f0f8ff;
      color: #333;
    }

    .splash-screen {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #00b4d8;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;
      animation: fadeOut 2.5s forwards; 
    }

    .splash-screen img {
      max-width: 220px;
      animation: zoomIn 2.5s ease-in-out; 
    }

    @keyframes zoomIn {
      0% { transform: scale(0.4); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    @keyframes fadeOut {
      100% { opacity: 0; visibility: hidden; }
    }


    header {
      background-color: #0077b6;
      color: #fff;
      padding: 1rem 2rem;
      position: sticky;
      top: 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    header .logo {
      font-size: 1.8rem;
      font-weight: 700;
    }

    header nav ul {
      display: flex;
      list-style: none;
    }

    header nav ul li a {
      margin-left: 1.5rem;
      color: #fff;
      text-decoration: none;
      font-weight: 500;
    }

    header nav ul li a:hover {
      color: #ffd166;
    }

    
    .hero {
      background: linear-gradient(to right, #48cae4, #90e0ef);
      color: white;
      padding: 4rem 2rem;
      text-align: center;
    }

    .hero h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
    }

    .hero .cta-button {
      padding: 1rem 2rem;
      background-color: #023e8a;
      color: #fff;
      border: none;
      border-radius: 30px;
      font-size: 1rem;
      text-decoration: none;
      transition: background-color 0.3s;
    }

    .hero .cta-button:hover {
      background-color: #0077b6;
    }

    
    .about, .services, .section {
      padding: 3rem 2rem;
      background-color: #f0f8ff;
    }

    .about h2, .services h2, .section h2 {
      font-size: 2rem;
      margin-bottom: 1.5rem;
      color: #0077b6;
    }

    .service {
      background-color: #fff;
      padding: 1.5rem;
      margin: 1rem;
      border-radius: 15px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }


    footer {
      background-color: #0077b6;
      color: #fff;
      text-align: center;
      padding: 1rem;
    }
  </style>
</head>
<body>
  <!-- Splash Screen -->
  <div class="splash-screen">
    <img src="codenvy logo.jpg" alt="Codenvy Logo">
  </div>

  <div class="main-content">
    <header>
      <div class="logo">Codenvy</div>
      <nav>
        <ul>
          <li><a href="#home" onclick="showSection('home')">Home</a></li>
          <li><a href="#about" onclick="showSection('about')">About</a></li>
          <li><a href="#services" onclick="showSection('services')">Services</a></li>
          <li><a href="#contact" onclick="showSection('contact')">Contact</a></li>
        </ul>
      </nav>
    </header>

    <section id="home" class="hero">
      <h1>Welcome to Codenvy</h1>
      <p>Your Cloud IDE for Effortless Development!</p>
      <a href="#services" onclick="showSection('services')" class="cta-button">Get Started Free</a>
    </section>

    <section id="about" class="about hidden">
      <h2>Who We Are</h2>
      <p>At Codenvy, we revolutionize the way developers build and collaborate in the cloud. No setups, no hassle – just code from anywhere!</p>
    </section>

    <section id="services" class="services hidden">
      <h2>What We Offer</h2>
      <div class="service-container">
        <div class="service">
          <h3>Workspace Management</h3>
          <p>Create flexible workspaces tailored to your projects.</p>
        </div>
        <div class="service">
          <h3>Powerful Debugging</h3>
          <p>Debug like a pro with real-time collaboration tools.</p>
        </div>
        <div class="service">
          <h3>24/7 Support</h3>
          <p>Need help? Our team is here to guide you at every step!</p>
        </div>
      </div>
    </section>

    <section id="contact" class="section hidden">
      <h2>Let's Connect</h2>
      <p>Email: <a href="mailto:codenvy123@gmail.com">codenvy123@gmail.com</a></p>
      <p>Phone: +91 4124-65432-7865</p>
      <p>Address: KV Colony, Anna Nagar, Chennai - 602571</p>
    </section>

    <footer>
      <p>&copy; 2025 Codenvy. Level Up Your Cloud Coding Experience!</p>
    </footer>
  </div>

  <script>
    function showSection(sectionId) {
      document.querySelectorAll('section').forEach(section => {
        section.classList.add('hidden');
      });
      document.getElementById(sectionId).classList.remove('hidden');
    }

    setTimeout(() => {
      document.querySelector('.splash-screen').style.display = 'none';
      document.querySelector('.main-content').style.display = 'block';
      showSection('home');
    }, 2500);
  </script>
</body>
</html>




```
## OUTPUT
![image](https://github.com/user-attachments/assets/446c3a00-d83d-4c5f-8a5b-38ee99cd73d1)
![image](https://github.com/user-attachments/assets/5d9e8b0f-9405-4bf0-b8fb-84726db03200)





## RESULT
The program for creating commercial website using CSS Flexbox is executed successfully.
