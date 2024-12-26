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
        <div class="text-section">
          <h1>Selamat Datang di Website Rajawali Farm!</h1>
          <p>
            Kami menyediakan produk ayam dan telur berkualitas. Setiap produk
            kami melalui proses yang teliti untuk memastikan rasa dan kualitas
            terbaik. Penasaran? Yuk, cek lebih lanjut di website kami!
          </p>
        </div>
        <div class="image-section">
          <img class="ayam-image" src="@/assets/Ayam1.png" alt="Ayam Image" />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.introduction {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background-color: #ffeda3;
  text-align: center;
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

.introduction.animate {
  opacity: 1;
  transform: translateY(0);
}

.text-and-image {
  padding: 0 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text-section {
  padding: 0 60px;
  color: black;
}

.text-section h1 {
  font-size: 2rem;
  margin-bottom: 20px;
}

.text-section p {
  line-height: 1.6;
  font-size: 1.2rem;
  margin-bottom: 20px;
}

.image-section {
  width: 15%;
  text-align: center;
}

.ayam-image {
  height: auto;
  border-radius: 5px;
  transition: transform 0.3s ease-in-out;
  width: 150px;
}

.ayam-image:hover {
  transform: scale(1.05);
}

@media (max-width: 768px) {
  .text-and-image {
    flex-direction: column;
    text-align: center;
  }

  .text-section h1 {
    font-size: 2rem;
  }

  .text-section p {
    font-size: 1rem;
  }

  .image-section {
    width: 30%;
    margin-top: 20px;
  }

  .ayam-image {
    width: 100%;
    max-width: 100%;
  }
}

@media (max-width: 480px) {
  .text-section h1 {
    font-size: 1.8rem;
  }

  .text-section p {
    font-size: 0.9rem;
  }

  .image-section {
    width: 30%;
    margin-top: 15px;
  }

  .ayam-image {
    width: 100%;
    max-width: 100%;
  }
}
</style>
