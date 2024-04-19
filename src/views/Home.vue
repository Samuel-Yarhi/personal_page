<script>
import Navbar from '../components/navbar.vue'
export default {
  methods: {
    navigateToAbout() {
      this.$router.push('/about')
      this.scrollToTop() // Scroll to top when navigating
    },
    navigateToProjects() {
      this.$router.push('/projects')
      this.scrollToTop() // Scroll to top when navigating
    },
    navigateToExperience() {
      this.$router.push('/experience')
      this.scrollToTop() // Scroll to top when navigating
    },
    navigateToContact() {
      this.$router.push('/contact')
      this.scrollToTop() // Scroll to top when navigating
    },
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' }) // Scroll to top of the page
    }
  },
  components: {
    Navbar
  }
}
</script>

<template>
  <Navbar />
  <div class="mainContainer">
    <div class="columnsContainer">
      <div>
        <img src="../../src/assets/sam.jpeg" alt="Sam" class="profileImage" />
      </div>

      <div className="rightColumn">
        <div class="heading">
          <h1>Sam’s personal page</h1>
        </div>
        <div class="welcomeText">
          <p>
            Welcome to my page!👨‍💻 My name is Sam, I’m a Full Stack Developer and a UX Designer. Here
            you will find info about myself, my work experience, personal projects and how to
            contact me.
          </p>
          <p>
            Feel free to navigate through the page using the buttons below or the navigation bar at
            the top of the page.
          </p>
        </div>

        <div class="buttonsContanier">
          <div class="buttonWrapper">
            <button class="myButton" @click="navigateToAbout">About me</button>
          </div>
          <div class="buttonWrapper">
            <button class="myButton" @click="navigateToExperience">Experience</button>
          </div>
          <div class="buttonWrapper">
            <button class="myButton" @click="navigateToProjects">Projects</button>
          </div>
          <div class="buttonWrapper">
            <button class="myButton" @click="navigateToContact">Contact me</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@import '../../src/assets/main.css';
</style>
