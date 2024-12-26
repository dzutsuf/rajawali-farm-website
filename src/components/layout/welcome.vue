<script setup>
const goToTentangKami = () => {
  const mainElement = document.querySelector("main");
  if (mainElement) {
    mainElement.classList.remove("disable-scroll");
  }

  const tentangKamiSection = document.querySelector("#greet");
  if (tentangKamiSection) {
    tentangKamiSection.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

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
      <a href="javascript:void(0)" class="cta-button" @click="goToTentangKami">
        Tentang Kami
      </a>
    </div>
  </div>
</template>

<style scoped>
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

.logo {
  width: 50%;
  height: auto;
  margin-bottom: 10px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

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
  text-align: center;
}

.welcome-text p {
  font-size: 2rem;
  margin-bottom: 25px;
  text-align: center;
}

.button1 {
  display: flex;
  gap: 20px;
  justify-content: center;
  flex-wrap: wrap;
}

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

@media (max-width: 768px) {
  .logo {
    width: 25%;
  }

  .welcome-text {
    margin-top: 20vh;
    justify-content: center;
    text-align: center;
  }

  .welcome-text h1 {
    font-size: 2rem;
  }

  .welcome-text p {
    font-size: 1.5rem;
  }

  .cta-button {
    font-size: 1rem;
    padding: 12px 30px;
  }
}

@media (max-width: 480px) {
  .logo {
    width: 25%;
  }

  .welcome-text {
    margin-top: 30vh;
    justify-content: center;
    text-align: center;
  }

  .welcome-text h1 {
    font-size: 1.5rem;
  }

  .welcome-text p {
    font-size: 1.2rem;
  }

  .cta-button {
    font-size: 0.9rem;
    padding: 10px 20px;
  }
}
</style>
