<template>
  <Navbar />
  <h1 class="experienceTitle">Work Experience</h1>

  <swiper
    :spaceBetween="30"
    :pagination="{
      clickable: true
    }"
    :modules="modules"
    class="mySwiper"
    :navigation="true"
  >
    <swiper-slide class="slide-container">
      <img src="../assets/justia.jpg" class="justia" />

      <p class="experienceTextAnimated">
        My first work experience was an internship at the Help Desk department of
        <a class="link" href="https://www.justia.com/" target="_blank">Justia</a> MX. Justia is a
        company that has its main headquarters at the Sillicon Valley, but they also have an office
        in Mexico. It is a company that is focused on delivering free information of the law of the
        United States, as well as offering digital marketing solutions to lawyers and law firms. I
        was still a student when I started working there. I was responsible for solving requests
        that the clients had with their websites using HTML5 and CSS3. I learned a lot about web
        development and how to work with clients.
      </p>
    </swiper-slide>
    <swiper-slide class="slide-container">
      <img src="../assets/cib.png" class="cib" />
      <p class="experienceText">
        My second job was a position as an audiovisual operator at a biological research center, in
        the events department of the institution. I was responsible for performing a wide variety of
        tasks, including the operation of an audio console for an auditorium, preparing this
        auditorium and other rooms for research expositions, setting up speakers, projectors,
        getting the laptops ready for presentations, streaming expositions through the internet
        using zoom and BlueJeans, and managing the schedule for events that the department had using
        Google Drive and Google Sheets. I did tons of stuff there, and I learned a lot about
        teamwork and communication. I also learned how to manage my time and how to be responsible
        for the tasks that were assigned to me.
      </p>
    </swiper-slide>
    <swiper-slide class="slide-container">
      <img src="../assets/Codestack_Systems.png" class="codeStack" />
      <p class="experienceText">
        My third and current job is a position as a Full Stack Developer at
        <a class="link" href="https://codestacksystems.com/" target="_blank">Codestack Systems</a>.
        This is a company that is focused on delivering software solutions to all kinds of
        businesses. I am responsible for developing mobile and web applications for clients using
        technologies like HTML5, CSS3, JavaScript, Node.js, Express.js, React Native, React,
        Angular, TypeScript, Git, Github, BitBucket, and more. I include UX Design principles in my
        work since I have completed the UX Design Certificate Program offered by Google through
        Coursera. This perspective enhances my work and makes it more user-friendly, allowing me to
        deliver top notch applications to the clients.
      </p>
    </swiper-slide>
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Pagination, Navigation } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import Navbar from '../components/navbar.vue'

export default {
  name: 'App',
  components: {
    Swiper,
    SwiperSlide,
    Navbar
  },
  setup() {
    return {
      modules: [Pagination, Navigation]
    }
  }
}
</script>

<style>
.slide-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-bottom: 3%;
}

.justia {
  height: 30%;
  width: 30%;
  margin-top: 2rem;
  opacity: 0;
  animation: slideInFromRight 1s forwards 1s;
}

.cib {
  margin-top: 2rem;
}

.link {
  color: #caf3ce;
  text-decoration: underline;
  font-weight: bold;
  font-style: italic;
  font-size: 1.6rem; /* Increase font size */
  letter-spacing: 0.05em; /* Increase letter spacing */
  transition: color 0.3s ease; /* Add transition for hover effect */
}

.link:hover {
  color: #89c997; /* Change color on hover */
}

.experienceTitle {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 6rem;
  text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
  text-align: center;
  animation: slideIn 1s forwards;
  margin-top: 1rem;
  margin-bottom: 0;
}

.experienceTextAnimated {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 1.5rem;
  text-align: justify;
  max-width: 48%;
  opacity: 0;
  animation: slideInFromRight 1s forwards 1s;
}

.experienceText {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 1.5rem;
  text-align: justify;
  max-width: 48%;
}

.swiper-pagination-bullet {
  background-color: #caf3ce;
  height: 30px;
  width: 30px;
}

.swiper-button-prev,
.swiper-button-next {
  color: #374e37;
  font-size: 2rem;
  background-color: #caf3ce;
  border: 2px solid #fff;
  border-radius: 10px;
  padding: 10px 20px;
  transition: transform 0.2s ease;
  pointer-events: auto;
  white-space: nowrap;
  text-align: center;
  cursor: pointer;
  outline: none;
  margin-top: -3rem;
}

@keyframes slideInFromRight {
  from {
    opacity: 0;
    transform: translateX(200px); /* Start from right */
  }
  to {
    opacity: 1;
    transform: translateX(0); /* Move to left */
  }
}
</style>
