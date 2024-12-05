<script>
import { onMounted, ref } from "vue";

export default {
  setup() {
    const greetingRef = ref(null);

    onMounted(() => {
      const observer = new IntersectionObserver(
        ([entry]) => {
          if (entry.isIntersecting) {
            entry.target.classList.add("animate");
          }
        },
        { threshold: 0.5 }
      );

      if (greetingRef.value) {
        observer.observe(greetingRef.value);
      }
    });

    return { greetingRef };
  },
};
</script>

<template>
  <div ref="greetingRef" class="introduction">
    <div class="container">
      <div class="text-and-image">
        <!-- Text Section -->
        <div class="text-section">
          <h1>Selamat Datang di Website Rajawali Farm!</h1>
          <p>
            Kami menyediakan produk ayam dan telur berkualitas. Setiap produk
            kami melalui proses yang teliti untuk memastikan rasa dan kualitas
            terbaik. Penasaran? Yuk, cek lebih lanjut di website kami!
          </p>
        </div>
        <!-- Ayam Image Section -->
        <div class="image-section">
          <img class="ayam-image" src="@/assets/Ayam1.png" alt="Ayam Image" />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
/* --- Introduction Section --- */
.introduction {
  display: flex;
  justify-content: center; /* Memastikan konten berada di tengah secara horizontal */
  align-items: center;
  width: 100%; /* Pastikan lebar section memenuhi 100% layar */
  height: 100%;
  background-size: cover; /* Mengisi seluruh tinggi layar */
  background-color: #ffeda3; /* Memberikan background warna sesuai yang diinginkan */
  text-align: center;
}

.text-and-image {
  padding: 0 40px 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text-section {
  padding: 0 40px 0;
  color: black;
}

.text-section h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.text-section p {
  line-height: 1.6;
  font-size: 1.6rem;
  margin-bottom: 20px;
}

.image-section {
  width: 45%; /* Memastikan gambar tidak terlalu besar */
  text-align: center;
}

.ayam-image {
  height: auto;
  border-radius: 5px;
  transition: transform 0.3s ease-in-out;
}

.ayam-image:hover {
  transform: scale(1.05);
}

.h1p {
  font-size: 2.5rem;
  margin-bottom: 20px;
  text-align: center;
}

/* Responsive Design */
@media (max-width: 768px) {
  .background {
    padding: 15px;
  }

  .logo {
    width: 40%;
  }

  .welcome-text h1 {
    font-size: 2.5rem;
  }

  .welcome-text p {
    font-size: 1.2rem;
  }

  .cta-button {
    font-size: 1rem;
    padding: 10px 30px;
  }

  .text-section h1 {
    font-size: 2rem;
  }

  .text-section p {
    font-size: 1rem;
  }

  .text-and-image {
    flex-direction: column; /* Stack text and image on smaller screens */
    text-align: center;
  }

  .image-section {
    width: 80%;
    margin-top: 20px;
  }

  .ayam-image {
    width: 100%;
    max-width: 100%;
  }
}

/* --- Animations --- */
@keyframes bounceIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  60% {
    opacity: 1;
    transform: scale(1.2);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* Initial State */
.introduction {
  opacity: 0;
  transform: scale(0.5);
  transition: opacity 0.3s ease, transform 0.3s ease;
}

/* Animate State */
.introduction.animate {
  animation: bounceIn 0.8s ease-out forwards;
}
</style>
