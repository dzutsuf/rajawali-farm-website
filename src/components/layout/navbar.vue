<template>
  <header class="navbar">
    <div class="container">
      <!-- Logo -->
      <div class="logo">
        <a href="#">MyWebsite</a>
      </div>

      <!-- Menu Navigasi -->
      <nav class="nav">
        <ul :class="{ active: isMenuActive }">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>

      <!-- Hamburger Menu untuk Responsif -->
      <div class="hamburger" @click="toggleMenu">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </div>
  </header>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isMenuActive = ref(false);

const toggleMenu = () => {
  isMenuActive.value = !isMenuActive.value;
};
</script>

<style scoped>
/* Styling untuk Navbar */
.navbar {
  background-color: #333;
  padding: 10px 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  color: white;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.logo a {
  color: white;
  text-decoration: none;
  font-size: 24px;
  font-weight: bold;
}

.nav ul {
  display: flex;
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.nav li {
  margin: 0 15px;
}

.nav a {
  color: white;
  text-decoration: none;
  font-size: 18px;
  transition: color 0.3s;
}

.nav a:hover {
  color: #ff5722;
}

.hamburger {
  display: none;
  cursor: pointer;
}

.hamburger .bar {
  width: 25px;
  height: 4px;
  margin: 5px;
  background-color: white;
}

@media (max-width: 768px) {
  .nav ul {
    position: absolute;
    top: 60px;
    left: 0;
    width: 100%;
    background-color: #333;
    flex-direction: column;
    display: none;
  }

  .nav.active ul {
    display: flex;
  }

  .hamburger {
    display: block;
  }
}
</style>
