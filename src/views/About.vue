<template>
  <Navbar />
  <h1 class="title">Who is Sam?</h1>

  <swiper
    :spaceBetween="30"
    :pagination="{
      clickable: true
    }"
    :modules="modules"
    class="mySwiper"
    :navigation="true"
  >
    <swiper-slide>
      <div class="rowContainer">
        <img src="@/assets/Samuel_Graduado.png" alt="Sam" class="gradImage" />
        <aside class="textContainer">
          <p class="text">
            I’m <strong>proudly</strong> from Mexico. I graduated in 2022 from the Computer Systems
            Engineering bachelor’s degree program at “Instituto Tecnológico de Saltillo”.
          </p>
          <p class="text">
            I am a Full Stack Developer and a UX Designer. I have a passion for creating beautiful
            and functional websites and applications. I am always looking for new challenges and
            opportunities to learn and grow.
          </p>
        </aside>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="rowContainer2">
        <img src="@/assets/Samuel_DJ2.png" alt="Sam" class="djImage1" />
        <p class="slide2text">
          My favorite hobby is to DJ. I have a taste for EDM, Techno, House, Tech-house, and related
          genres of music. I like to let my creativity flow and let loose when mixing songs. Since
          programming demands a lot of logic, problem solving and mathematics, DJing is really a
          great way to use the other hemisphere of my brain.
        </p>
        <img src="@/assets/Samuel_DJ.png" alt="Sam" class="djImage2" />
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="rowContainer3">
        <img src="@/assets/wing_chun_dummy.png" alt="wing_chun_dummy" class="dummy" />
        <aside>
          <p class="slide3text">
            I practice Wing Chun 3 times a week, Mondays, Wednesdays and Fridays. I've been
            practicing different styles of martial arts throughout my life, but Wing Chun is the one
            that has stuck with me the most. I like the philosophy behind it and the way it teaches
            you to be patient and to think before acting. It's a great way to keep my body and mind
            in shape.
          </p>
        </aside>
      </div>
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
.djImage1,
.djImage2 {
  width: 10%;
  height: 10%;
  margin-top: 2.5rem;
}

.djImage1 {
  margin-right: 6rem;
}

.djImage2 {
  margin-left: 6rem;
}

.dummy {
  width: 20%;
  height: 20%;
  margin-left: 11%;
  margin-top: 1rem;
  margin-right: 4rem;
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
  position: fixed;
}

.swiper-button-prev {
  margin-left: 6rem;
}

.swiper-button-next {
  margin-right: 6rem;
}

.rowContainer {
  display: flex;
  justify-content: center;
}

.rowContainer2 {
  display: flex;
  justify-content: center;
  margin-left: 4%;
}
.rowContainer3 {
  display: flex;
  justify-content: center;
  margin-left: 4%;
}

.textContainer {
  display: flex;
  flex-direction: column;
  opacity: 0;
  animation: slideInFromRight 1s forwards 1s;
}

html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
}

.title {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 6rem;
  text-shadow: 4px 4px 8px rgba(0, 0, 0, 0.5);
  text-align: center;
  margin-left: 5%;
  animation: slideIn 1s forwards;
  margin-top: 1rem;
  margin-bottom: 0;
}

.text {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 2rem;
  max-width: 48%;
  text-align: justify;
}

.slide2text {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 2rem;
  max-width: 31%;
  text-align: justify;
}

.slide3text {
  font-family: 'Inter', sans-serif;
  color: #caf3ce;
  font-size: 2rem;
  max-width: 48%;
  text-align: justify;
}

.gradImage {
  width: 20%;
  height: 20%;
  margin-left: 14%;
  opacity: 0;
  margin-top: 1rem;
  animation: slideInFromRight 1s forwards 1s;
  margin-right: 4rem;
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

@media (max-width: 1364px) {
  .title {
    font-size: 4rem;
  }

  .rowContainer,
  .rowContainer2 {
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .slide2text {
    font-size: 1.5rem;
    max-width: 48%;
    text-align: justify;
  }

  .rowContainer3 {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    width: 100%;
    margin-left: 25%;
  }

  .dummy {
    margin-right: 60%;
  }
  .slide3text {
    font-size: 1.5rem;
    text-align: justify;
    align-self: center;
  }

  .djImage1 {
    width: 20%;
    height: 20%;
    margin-top: 2.5rem;
    margin-right: 0;
  }

  .djImage2 {
    display: none;
  }

  .textContainer {
    align-items: center;
  }

  .text {
    font-size: 1.5rem;
  }
}

@media (max-width: 836px) {
  .swiper-button-prev {
    margin-left: 2rem;
  }

  .swiper-button-next {
    margin-right: 2rem;
  }
}

@media (max-width: 375px) {
  .gradImage {
    width: 50%;
    height: 50%;
    margin-left: 0;
    margin-right: 0;
  }

  .swiper-button-next {
    margin-right: 0px;
    width: 3%;
    height: 3%;
  }

  .swiper-button-prev {
    margin-left: -9px;
    width: 3%;
    height: 3%;
  }

  .text {
    font-size: 1.5rem;
    max-width: 65%;
  }

  .djImage1 {
    width: 40%;
    height: 40%;
    margin-top: 2.5rem;
    margin-right: 0;
  }

  .slide2text {
    font-size: 1.5rem;
    max-width: 65%;
    text-align: justify;
  }

  .slide3text {
    font-size: 1.5rem;
    max-width: 65%;
    text-align: justify;
    margin-left: -20px;
  }

  .dummy {
    width: 40%;
    height: 40%;
  }
}
</style>
