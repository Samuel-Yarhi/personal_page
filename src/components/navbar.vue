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
  justify-content: space-around;
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
}

.navLink:hover {
  border-bottom: 2px solid #374e37;
}

.active {
  border-bottom: 2px solid #374e37;
}
</style>
