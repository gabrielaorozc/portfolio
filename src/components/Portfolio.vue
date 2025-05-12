<!-- Portfolio.vue -->
<template>
    <div id="page-top" class="portfolio-container">
      <!-- Navigation -->
      <nav class="navbar navbar-expand-lg navbar-dark fixed-top" id="sideNav">
        <div class="navbar-left">
          <a class="navbar-brand js-scroll-trigger" href="#page-top">
            <span class="d-none d-lg-block">
              <img class="img-fluid img-profile rounded-circle mx-auto mb-2" src="../assets/icons/profile.jpg" alt="Profile" />
            </span>
          </a>
        </div>
        <div class="navbar-mobile">
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarResponsive"
            aria-controls="navbarResponsive"
            :aria-expanded="isNavOpen"
            aria-label="Toggle navigation"
            @click="toggleNav"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" :class="{ show: isNavOpen }" id="navbarResponsive">
            <ul class="navbar-nav">
              <li v-for="section in sections" :key="section.id" class="nav-item">
                <a class="nav-link js-scroll-trigger" :href="'#' + section.id" @click="closeNav">{{ section.name }}</a>
              </li>
            </ul>
          </div>
        </div>
        <div class="navbar-right">
          <div class="faith-content">
            <p>By His mercy and through Christ, I am here. ✝</p>
          </div>
        </div>
      </nav>
  
      <!-- Page Content -->
      <div class="container-fluid p-0">
        <!-- Sections -->
        <section v-for="section in sections" :key="section.id" class="resume-section" :id="section.id">
          <div class="resume-section-content">
            <component :is="section.component" />
          </div>
        </section>
      </div>
      
      <!-- Footer -->
      <footer class="portfolio-footer">
        <p>&copy; {{ new Date().getFullYear() }} Gabriela Orozco. All rights reserved.</p>
        <p class="tech-stack">Built with Vue.js 3.4.15 and Bootstrap 5.3.3</p>
      </footer>
    </div>
  </template>
  
  <script setup>
  import About from '../sections/About.vue'
  import Experience from '../sections/Experience.vue'
  import Education from '../sections/Education.vue'
  import Skills from '../sections/Skills.vue'
  import Interests from '../sections/Interests.vue'
  import Awards from '../sections/Awards.vue'
  import { ref, onMounted, onUnmounted } from 'vue'
  import * as bootstrap from 'bootstrap'

  const isNavOpen = ref(false)
  let collapseInstance = null
  let toggleTimeout = null

  const toggleNav = () => {
    if (toggleTimeout) {
      clearTimeout(toggleTimeout)
    }
    
    toggleTimeout = setTimeout(() => { // to prevent the navbar from toggling too quickly on mobile
      isNavOpen.value = !isNavOpen.value
      if (collapseInstance) {
        if (isNavOpen.value) {
          collapseInstance.show()
        } else {
          collapseInstance.hide()
        }
      }
    }, 400) // 400ms debounce
  }

  const closeNav = () => {
    if (toggleTimeout) {
      clearTimeout(toggleTimeout)
    }
    isNavOpen.value = false
    if (collapseInstance) {
      collapseInstance.hide()
    }
  }
  
  const sections = [
    { id: 'about', name: 'About', component: About },
    { id: 'experience', name: 'Experience', component: Experience },
    { id: 'education', name: 'Education', component: Education },
    { id: 'skills', name: 'Skills', component: Skills },
    { id: 'interests', name: 'Interests', component: Interests },
    // { id: 'awards', name: 'Awards', component: Awards }
  ]

  onMounted(() => {
    const sideNav = document.body.querySelector('#sideNav');
    if (sideNav) {
      new bootstrap.ScrollSpy(document.body, {
        target: '#sideNav',
        rootMargin: '0px 0px -40%',
      });
      
      // Initialize collapse
      const collapseElement = document.getElementById('navbarResponsive')
      if (collapseElement) {
        collapseInstance = new bootstrap.Collapse(collapseElement, {
          toggle: false
        })
      }
    }
  })

  onUnmounted(() => {
    if (collapseInstance) {
      collapseInstance.dispose()
    }
    if (toggleTimeout) {
      clearTimeout(toggleTimeout)
    }
  })
  </script>
  
  <style>
  /* Import Bootstrap styles */
  @import 'bootstrap/dist/css/bootstrap.min.css';
  @import url('https://fonts.googleapis.com/css?family=Saira+Extra+Condensed:500,700');
  @import url('https://fonts.googleapis.com/css?family=Muli:400,400i,800,800i');
  @import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;700&display=swap');

  /* Import portfolio styles */
  @import '../assets/styling/portfolio.css';
  @import '../assets/styling/section.css';
  @import '../assets/styling/icons.css';

  /* Base styles */
  .portfolio-container {
    min-height: 100vh;
    width: 100%;
    position: relative;
  }
  </style>
  