<!-- sections/About.vue -->
<template>
    <div>
      <div class="header-content">
        <div class="header-content-left"> 
          <img class="img-profile rounded-circle mx-auto mb-2" src="../assets/icons/profile.jpg" alt="Profile" />
        </div>
        <div class="header-content-right">✝</div>
      </div>
      <h1 class="mb-0">
        Gabriela
        <span class="secondary-color">Orozco</span>
      </h1>
      <div class="subheading mb-5">
        Tacoma, Washington · (253) 232-2775 ·
        <a href="mailto:gaby@8bitduck.com">gaby@8bitduck.com</a>
      </div>
      
      <div class="about-content">
        <p class="mb-4">
          Hi, I'm Gaby — a creative and detail-oriented Front-End Engineer with over 5 years of 
          experience building responsive, scalable web applications. I specialize in <span class="secondary-color font-weight-bold">React.js, Vue.js, 
          and TypeScript</span>, and recently, I've been deeply involved in developing AI-powered UIs and 
          modern internal tools.
        </p>
        <p class="mb-4">
          I'm passionate about clean code, user-focused design, and bringing ideas to life 
          through elegant, accessible interfaces. Whether it's revamping a POS system to pixel-perfect 
          precision or leading UI development for AI-driven student engagement tools, I thrive on 
          collaboration, rapid iteration, and continuous learning.
        </p>
        <p class="mb-4">
          Beyond coding, I'm fluent in English and Spanish, and I love diving into new technologies 
          like Microsoft's Power Platform and SharePoint to expand my skills. I bring a strong sense 
          of ownership, a love for solving problems, and an excitement for shaping the future of digital 
          experiences.
        </p>
        <p class="mb-5">
          When I'm not building web applications, you'll find me enjoying time with my family, 
          pursuing fitness goals, or exploring the latest trends in UI/UX and AI integration.
        </p>
      </div>
      <div class="social-icons">
        <a class="social-icon" href="https://www.linkedin.com/in/gabriela-orozco/"><i class="fab fa-linkedin-in"></i></a>
        <!-- <a class="social-icon" href="https://github.com/gabrielaorozc"><i class="fab fa-github"></i></a> -->
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'About',
  }
  </script>

  <style>
  @import '../assets/styling/icons.css';

  </style>
  
  