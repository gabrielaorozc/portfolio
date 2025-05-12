<!-- sections/Interests.vue -->
<template>
  <div class="interests-section">
    <h2 class="mb-5">Interests & Passions</h2>
    
    <div class="container mobile-container">
      <ul class="nav nav-tabs mb-4" id="interestsTab" role="tablist">
        <li class="nav-item" v-for="(tab, index) in tabs" :key="index">
          <button 
            class="nav-link" 
            :class="{ active: activeTab === index }"
            @click="activeTab = index"
            type="button"
          >
            <i :class="tab.icon"></i>
            {{ tab.title }}
          </button>
        </li>
      </ul>

      <div class="tab-content" id="interestsTabContent">
        <div 
          v-for="(tab, index) in tabs" 
          :key="index"
          class="tab-pane fade"
          :class="{ 'show active': activeTab === index }"
        >
          <div class="card">
            <div class="card-body">
              <template v-if="index === 0">
                <h3>Software Engineering</h3>
                <p>My journey in software engineering began in the early 2000s with a passion for customizing MySpace profiles through HTML code. This early exposure to frontend development sparked my interest in creating and modifying web interfaces, and I quickly realized my love for seeing immediate visual results from code changes.</p>
                <p>After completing my Bachelor's in Computer Science, I focused on frontend development, where I truly thrive. One of my most rewarding experiences was at VenueNext, where I led the complete revamp of their POS product to implement new UX designs. This project was particularly fulfilling as I got to work with modern React, create reusable components, and refactor legacy code - all while learning different coding styles and best practices.</p>
                <p>An exciting chapter in my career was teaching game development to children using Scratch, a block-based coding language with JavaScript backend. This experience not only allowed me to share my passion for programming with young minds but also helped me discover my own interest in game development. As a lifelong gamer, I aspire to transition into game development in the future, combining my technical expertise with my love for gaming.</p>
                <p>What I love most about frontend development is the perfect blend of technical challenge and creative expression. Every day brings new opportunities to create beautiful, functional web experiences while staying current with the latest technologies and trends in web development.</p>
              </template>

              <template v-if="index === 1">
                <h3>Strength Training</h3>
                <p>My strength training journey began in 2015, and while I took some time off to focus on raising my children, I've recently reignited my passion for fitness alongside my husband. As we grow older and our children become more active, staying fit and healthy has become even more important - we need to keep up with their endless energy without any physical limitations!</p>
                <p>What started as a way to stay in shape has evolved into an incredible strength-building journey. As someone who has always been petite, the gym has been transformative for me. I've gained approximately 30 pounds of muscle mass, which is a significant achievement given my starting point. The strength I've developed has been particularly rewarding, allowing me to hit personal records that I never thought possible for someone of my size and stature.</p>
                <p>This journey has become a shared passion with my husband, who is not just my partner but my best friend. Our gym time has become our special time together, a space where we continue to grow and strengthen not just our bodies, but our relationship as well. This shared commitment has brought remarkable positive changes to our marriage, and our children are witnessing firsthand what a strong, communicative partnership looks like.</p>
                <p>Everything I do, including this fitness journey, is ultimately for my children's well-being. It's incredibly fulfilling to navigate life's challenges and triumphs together with my lifelong best friend, showing our children the importance of health, dedication, and growing together as a family.</p>
              </template>

              <template v-if="index === 2">
                <h3>Culinary Arts</h3>
                <p>My love for cooking has deep roots in my Mexican heritage. Born and raised in Mexico until the age of six, I grew up in a household where homemade meals were a daily tradition. My mother's daily cooking for our family, including her fresh homemade tortillas, created my foundation for understanding the importance of home-cooked meals. Moving to the US opened my eyes to new cuisines while also making me appreciate the unique flavors of my Mexican upbringing.</p>
                <p>My culinary journey took a significant turn in high school, where I met my husband and discovered my passion for cooking through formal education. I progressed through various cooking classes, eventually reaching the highest level of culinary education available at my school. Dressed in chef's whites, I participated in school district events, learning both the art of cooking and the professional service standards of high-end restaurants. These experiences ranged from preparing full-course meals to creating exquisite baked goods.</p>
                <p>After high school, through university and into married life, my passion for cooking only grew stronger. What started as a cultural connection and educational pursuit has evolved into a daily joy. I love preparing my family's favorite meals, experimenting with new recipes, and adapting traditional dishes to our current lifestyle. Most recently, I've focused on creating high-protein, low-carb meals to support our strength training journey, showing how my culinary skills continue to evolve with our family's needs.</p>
                <p>My husband has been my biggest fan since high school, often joking that my cooking was one of the main reasons he married me! He's even suggested that I should consider opening a food truck or small restaurant in Tacoma to share my recipes with the community. While that might be a future adventure, for now, I'm happy sharing my culinary creations with my family and friends.</p>
              </template>

              <template v-if="index === 3">
                <h3>Acrylic Painting</h3>
                <p>In 2015, I decided to try my hand at painting, and to my surprise, I discovered a natural talent for it. What started as a casual experiment quickly developed into a meaningful hobby as I created various pieces, each one helping me refine my technique and artistic expression.</p>
                <p>While I haven't been able to dedicate time to painting recently, it remains a passion I hope to return to. When I do pick up the brush again, I want to channel my creativity in a new direction - creating Christian-themed artwork. This would allow me to express my gratitude to the Lord for His many blessings and share my faith through art.</p>
                <p>Here are some of my paintings - as you can probably tell, I have a particular fondness for painting lions! 🦁</p>
                <div class="painting-slideshow">
                  <div class="slideshow-container">
                    <img :src="currentPainting" :alt="paintingAlt" class="painting-image">
                    <button class="slideshow-btn prev" @click="prevPainting">
                      <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slideshow-btn next" @click="nextPainting">
                      <i class="fas fa-chevron-right"></i>
                    </button>
                  </div>
                  <div class="slideshow-dots">
                    <span 
                      v-for="(painting, index) in paintings" 
                      :key="index"
                      :class="{ active: currentIndex === index }"
                      @click="currentIndex = index"
                    ></span>
                  </div>
                </div>
              </template>

              <template v-if="index === 4">
                <h3>Gaming</h3>
                <p>I'm a proud Nintendo enthusiast! My gaming journey began in Mexico with the Nintendo NES, where I first discovered the joy of video games. Growing up, I spent countless hours playing Mario Kart on the Nintendo 64 with my older brothers, creating cherished memories that sparked my lifelong love for Nintendo.</p>
                <p>Throughout the years, I've been a dedicated Nintendo fan, owning and enjoying every major console from the GameCube to the Wii, and now the Nintendo Switch. My gaming library is filled with Nintendo classics, particularly the Legend of Zelda series, with Tears of the Kingdom currently holding the title of my favorite game.</p>
                <p>I'm also a huge fan of the Mario franchise, having played most of the iconic titles including Mario Kart, Mario Party, Super Smash Bros., and the classic Super Mario Bros. games. These games have not only provided endless entertainment but have also been a wonderful way to bond with family and friends throughout the years.</p>
                <p>What I love most about Nintendo games is their perfect blend of accessibility and depth, their family-friendly nature, and the way they bring people together. Whether it's competing in Mario Kart races, solving puzzles in Zelda, or battling it out in Smash Bros., Nintendo games have been a constant source of joy in my life. Now, I'm thrilled to share this passion with my own family - my husband and kids have joined me in the Nintendo fun! We enjoy playing Mario games and Smash Bros. together, and it's especially heartwarming to see my son develop the same love for Tears of the Kingdom that I have. Gaming has truly become a wonderful family activity that brings us all together.</p>
                
                <div class="gaming-gallery">
                  <div class="gaming-item">
                    <img src="../assets/gaming/zelda.jpg" alt="The Legend of Zelda: Tears of the Kingdom" class="gaming-image">
                    <p class="gaming-caption">My current favorite: The Legend of Zelda: Tears of the Kingdom</p>
                  </div>
                  <div class="gaming-item">
                    <img src="../assets/gaming/mario_kart.jpg" alt="Mario Kart 8 Deluxe" class="gaming-image">
                    <p class="gaming-caption">Family favorites: Mario Kart</p>
                  </div>
                  <div class="gaming-item">
                    <img src="../assets/gaming/smash_bros.jpg" alt="Super Smash Bros. Ultimate" class="gaming-image">
                    <p class="gaming-caption">Competitive fun: Super Smash Bros. Ultimate</p>
                  </div>
                </div>
              </template>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import oso from '../assets/paintings/oso.jpg'
import skull from '../assets/paintings/skull.jpg'
import birds from '../assets/paintings/birds.jpg'
import beach from '../assets/paintings/beach.jpg'
import elephant from '../assets/paintings/elephant.jpg'
import lions from '../assets/paintings/lions.jpg'
import lion from '../assets/paintings/lion.jpg'
import tiger from '../assets/paintings/tiger.jpg'

export default {
  name: 'Interests',
  data() {
    return {
      activeTab: 0,
      currentIndex: 0,
      paintings: [
        { src: oso, alt: 'Oso painting' },
        { src: skull, alt: 'Skull painting' },
        { src: birds, alt: 'Birds painting' },
        { src: beach, alt: 'Beach painting' },
        { src: elephant, alt: 'Elephant painting' },
        { src: lions, alt: 'Lions painting' },
        { src: lion, alt: 'Lion painting' },
        { src: tiger, alt: 'Tiger painting' }
      ],
      tabs: [
        { title: 'Coding', icon: 'fas fa-code' },
        { title: 'Fitness', icon: 'fas fa-dumbbell' },
        { title: 'Cooking', icon: 'fas fa-utensils' },
        { title: 'Art', icon: 'fas fa-palette' },
        { title: 'Gaming', icon: 'fas fa-gamepad' }
      ]
    }
  },
  computed: {
    currentPainting() {
      return this.paintings[this.currentIndex].src;
    },
    paintingAlt() {
      return this.paintings[this.currentIndex].alt;
    }
  },
  methods: {
    nextPainting() {
      this.currentIndex = (this.currentIndex + 1) % this.paintings.length;
    },
    prevPainting() {
      this.currentIndex = (this.currentIndex - 1 + this.paintings.length) % this.paintings.length;
    }
  }
}
</script>

<style>
  @import '../assets/styling/interests.css';
</style> 