<template>
  <div class="navContainer">
    <nav class="navbar">
      <router-link to="/" class="navLink" :class="{ active: $route.path === '/' }"
        >Home</router-link
      >
      <router-link to="/about" class="navLink" :class="{ active: $route.path === '/about' }"
        >About me</router-link
      >
      <router-link
        to="/experience"
        class="navLink"
        :class="{ active: $route.path === '/experience' }"
        >Experience</router-link
      >
      <router-link to="/projects" class="navLink" :class="{ active: $route.path === '/projects' }"
        >Projects</router-link
      >
      <router-link to="/contact" class="navLink" :class="{ active: $route.path === '/contact' }"
        >Contact me</router-link
      >
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Navbar'
}
</script>

<style>
.navContainer {
  background-color: #caf3ce;
  width: 100%;
  height: 50px;
}

.navbar {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  width: 100%;
}

.navLink {
  text-decoration: none;
  color: #374e37;
  font-size: 35px;
  font-family: 'Inter', sans-serif;
  margin-top: 12px;
  margin: 0 4rem;
}

.navLink:hover {
  border-bottom: 2px solid #374e37;
}

.active {
  border-bottom: 2px solid #374e37;
}

@media (max-width: 1364px) {
  .navLink {
    font-size: 25px;
    margin: 0 2rem;
  }

  .navContainer.navContainer {
    width: 104%;
    height: 50px;
  }

  .navLink {
    margin-top: 10px;
  }
}

@media (max-width: 836px) {
  .navLink {
    font-size: 15px;
    margin: 0 1rem;
  }

  .navLink {
    margin-top: 10px;
  }
}
@media (max-width: 487px) {
  .navLink {
    font-size: 12px;
    margin: 0 1rem;
  }

  .navLink {
    margin-top: 10px;
  }
}

@media (max-width: 375px) {
  .navLink {
    font-size: 10px;
    margin: 0 0.75rem;
    margin-top: 5px;
  }
}
</style>
