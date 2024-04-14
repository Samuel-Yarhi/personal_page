<template>
  <Navbar />
  <h1 class="projectsTitle">Projects</h1>

  <h4 class="subheading">Click on each project title to show its details!</h4>

  <div id="app">
    <div class="faqs">
      <FAQ
        v-for="(faq, i) in faqs"
        :faq="faq"
        :index="i"
        :key="i"
        :open="faq.open"
        @toggleOpen="toggleOpen"
      />
    </div>
  </div>
</template>

<script>
import Navbar from '../components/navbar.vue'
import FAQ from '../components/FAQ.vue'

export default {
  name: 'Projects',
  components: {
    // Import the Navbar component
    Navbar,
    FAQ
  },
  data() {
    return {
      faqs: [
        {
          question: 'Tindog',
          answer:
            'Developed the front end of a dating website for dogs using HTML, CSS, and Bootstrap. The app is fully responsive and has a clean and modern design.',
          link: 'https://samuel-yarhi.github.io/TinDog/',
          open: false
        },
        {
          question: 'Drumkit Webapp',
          answer:
            'Developed a full-stack web application simulating a DrumKit using the jQuery library to handle the DOM tree for detecting mouse and keyboard actions. Implemented JavaScript methods and classes to play .mp3 files with conditional statements.',
          link: 'https://samuel-yarhi.github.io/DrumKit/',
          open: false
        },
        {
          question: 'Personal website',
          answer:
            'You are browsing it right now! This website was developed using Vue.js, Vite, and Typescript. I also used the Vue Router library to handle the navigation between pages. It is actually an SPA! This architecture allows the website to be faster, making it easy to access and browse through. I also used my knowledge in UX to provide a smooth experience for the user.',
          open: false
        },
        {
          question: 'UX Design Prototype: Japanese restaurant delivery app',
          answer:
            'Elaborated the design and prototype in low fidelity and high fidelity of a mobile app using Figma. The app is focused on delivering Japanese food to customers. The prototype includes the user flow, wireframes, and a clickable prototype for user testing. The app was designed following the principles of UX Design and Material Design guidelines.',
          link2:
            'https://www.figma.com/proto/561TiTIm2h5TUWk4coYT53/Portfolio-Wireframes?type=design&node-id=2-2&t=07B5HBhUlBHpPQqO-1&scaling=scale-down&page-id=0%3A1&starting-point-node-id=2%3A2&mode=design',
          link3:
            'https://www.figma.com/proto/561TiTIm2h5TUWk4coYT53/Portfolio-Wireframes?type=design&node-id=67-779&t=QJ8SlgmZs1LltuTC-1&scaling=min-zoom&page-id=67%3A485&mode=design',
          open: false
        }
      ]
    }
  },
  methods: {
    toggleOpen: function (index) {
      this.faqs = this.faqs.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open
        } else {
          faq.open = false
        }

        return faq
      })
    }
  }
}

// Get all accordion headers
var accordionHeaders = document.querySelectorAll('.accordion-header')

// Add click event listener to each accordion header
accordionHeaders.forEach(function (header) {
  header.addEventListener('click', function () {
    // Toggle active class on clicked header
    this.classList.toggle('itemActive')

    // Toggle visibility of accordion body
    var body = this.nextElementSibling
    if (body.style.display === 'block') {
      body.style.display = 'none'
    } else {
      body.style.display = 'block'
    }
  })
})
</script>

<style>
.projectsTitle {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 6rem;
  text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
  text-align: center;
  animation: slideIn 1s forwards;
  margin-top: 1rem;
  margin-bottom: 0;
}
.subheading {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 2rem;
  text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
  text-align: center;
  animation: slideIn 1s forwards;
}

/* Style for accordion header */
.accordion-header {
  background-color: #f1f1f1;
  color: #333;
  cursor: pointer;
  padding: 10px;
  border: 1px solid #ccc;
  border-bottom: none;
  border-radius: 5px 5px 0 0;
}

/* Style for accordion body */
.accordion-body {
  display: none;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 0 0 5px 5px;
}

/* Style for active accordion header */
.itemActive {
  background-color: #ff0000;
}
@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(-200px); /* Start from top */
  }
  to {
    opacity: 1;
    transform: translateY(0); /* Move down */
  }
}

.faq {
  display: block;
  width: 100%;
  max-width: 768px;
  margin: 15px auto;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  background-color: #caf3ce;
}

.faq .question {
  position: relative;
  color: #374e37;
  font-size: 20px;
  font-family: 'Inter', sans-serif;
  font-weight: bold;
  transition: all 0.4s linear;
}

.faq .question::after {
  content: '';
  position: absolute;
  top: 50%;
  right: 0px;
  transform: translateY(-50%) rotate(0deg);
  width: 30px;
  height: 30px;
  background-image: url('../assets/downBtn.png');
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  transition: all 0.2s linear;
}
.faq.open .question {
  margin-bottom: 15px;
}
.faq.open .question::after {
  transform: translateY(-50%) rotate(90deg);
}
.faq .answer {
  color: #374e37;
  font-size: 18px;
  opacity: 0;
  max-height: 0px;
  overflow-y: hidden;
  transition: all 0.4s ease-out;
  font-family: 'Inter', sans-serif;
}
.faq.open .answer {
  opacity: 1;
  max-height: 1000px;
}

@media (max-width: 836px) {
  .faq {
    max-width: 80%;
  }
}
</style>
