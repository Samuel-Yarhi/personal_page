<template>
  <Navbar />
  <h1 class="contactTitle">Let's connect!</h1>

  <div class="gridContainer">
    <div class="contactContainer">
      <img src="../assets/linkedIn.png" alt="LinkedIn" class="image" />

      <a href="https://www.linkedin.com/in/samuel-yarhi/" target="_blank" class="imageText"
        >LinkedIn</a
      >
    </div>
    <div class="contactContainer">
      <img src="../assets/github-logo.png" alt="github" class="image" />

      <a href="https://github.com/Samuel-Yarhi" target="_blank" class="imageText">Git Hub</a>
    </div>
  </div>

  <div class="gridContainer">
    <div class="contactContainer" @click="copyToClipboard('samuel_yarhi@outlook.com')">
      <img src="../assets/email.png" alt="Email" class="image" />
      <p class="imageText">samuel_yarhi@outlook.com</p>
    </div>
    <div class="contactContainer" @click="copyToClipboard('+528442948479')">
      <img src="../assets/whatsapp.png" alt="WhatsApp" class="image" />
      <p class="imageText">+52 844 294 8479</p>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/navbar.vue'

export default {
  name: 'Contact',
  components: {
    Navbar
  },
  methods: {
    copyToClipboard(text) {
      // Create a temporary input element
      const input = document.createElement('input')
      input.style.position = 'fixed'
      input.style.opacity = 0
      input.value = text
      document.body.appendChild(input)
      // Select the text
      input.select()
      input.setSelectionRange(0, 99999) // For mobile devices
      // Copy the text
      document.execCommand('copy')
      // Remove the temporary input
      document.body.removeChild(input)
      // Optionally, display a message to the user
      alert(`${text} copied to clipboard!`)
    }
  }
}
</script>

<style>
.contactTitle {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 6rem;
  text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
  text-align: center;
  animation: slideIn 1s forwards;
  margin-top: 1rem;
  margin-bottom: 0;
}

.gridContainer {
  display: flex;
  justify-content: center;
  align-items: center;
}

.contactContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2rem;
  margin-bottom: 2rem;
  background-color: #89c997;
  max-width: fit-content;
  border-radius: 1rem;
  padding: 1%;
  margin-right: 2rem;
  opacity: 0;
  animation: fadeIn 1s forwards 1s;
}

.image {
  border-radius: 25%;
  margin-right: 1rem;
  width: 5rem;
}

.imageText {
  font-family: 'Inter', sans-serif;
  color: #374e37;
  font-size: 2rem;
  text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
  text-align: center;
  cursor: pointer;
}

.imageText:hover {
  color: #caf3ce;
}

@keyframes fadeIn {
  0% {
    opacity: 0; /* Start with no opacity */
    transform: scale(0); /* Start with small size */
    transform-origin: center; /* Set the origin to the center */
  }
  100% {
    opacity: 1;
    transform: scale(1); /* End with original size */
    transform-origin: center; /* Maintain the origin at the center */
  }
}
</style>
