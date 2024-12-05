<script setup></script>

<template>
  <div class="welcome-text">
    <img
      class="logo animate-logo"
      src="@/assets/logorajawalifarm.png"
      alt="logorajawalifarm"
    />
    <h1 class="animate-text">RAJAWALI FARM</h1>
    <p class="animate-text">Rajanya Telur dan Ayam</p>
    <div class="button1 animate-buttons">
      <a href="#explore" class="cta-button">Tentang Kami</a>
      <a href="#explore" class="cta-button">Blog</a>
    </div>
  </div>
</template>

<style>
/* Keyframes for Animations */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideInUp {
  from {
    transform: translateY(50px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

/* Animations for Elements */
.animate-logo {
  animation: fadeIn 1.5s ease-in-out;
}

.animate-text {
  animation: slideInUp 1.2s ease-in-out;
  animation-delay: 0.5s;
  animation-fill-mode: both;
}

.animate-buttons {
  animation: slideInUp 1.2s ease-in-out;
  animation-delay: 1s;
  animation-fill-mode: both;
}

/* Logo Styling */
.logo {
  width: 50%;
  height: auto;
  margin-bottom: 10px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

/* Welcome Text Section */
.welcome-text {
  margin-top: 7vh;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.welcome-text h1 {
  font-size: 4rem;
  font-weight: bold;
  margin-bottom: 15px;
}

.welcome-text p {
  font-size: 2rem;
  margin-bottom: 25px;
}

.button1 {
  display: flex;
  gap: 20px;
  justify-content: center;
}

/* CTA Button Styling */
.cta-button {
  background-color: transparent;
  padding: 14px 40px;
  font-size: 1.3rem;
  color: white;
  text-decoration: none;
  border-radius: 25px;
  border: 2px solid white;
  transition: background-color 0.3s, border-color 0.3s;
}

.cta-button:hover {
  background-color: #e64a19;
}
</style>
