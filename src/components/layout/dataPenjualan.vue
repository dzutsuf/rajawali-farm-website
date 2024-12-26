<template>
  <section class="data-penjualan" ref="sectionRef">
    <div class="container">
      <h2 class="section-title">Data Penjualan Telur</h2>
      <div class="card-grid">
        <div class="card" v-for="(card, index) in cards" :key="index">
          <div class="card-inner">
            <div class="card-front">
              <div class="icon">
                <img :src="card.icon" :alt="`${card.title} Icon`" />
              </div>
              <h3 class="card-title">{{ card.title }}</h3>
            </div>
            <div class="card-back">
              <div class="icon">
                <img :src="card.icon" :alt="`${card.title} Icon`" />
              </div>
              <p class="card-text">{{ card.text }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { onMounted, ref } from "vue";
import Harian from "../footage/24-Hours.png";
import Bulanan from "../footage/calendar-month.png";
import Tahunan from "../footage/calendar-year.png";
export default {
  setup() {
    const sectionRef = ref(null);

    const cards = [
      {
        title: "Harian",
        text: "Sekitar 750 kg telur (7,5 kuintal) dihasilkan setiap hari dari sekitar 26.000 ayam.",
        icon: Harian,
      },
      {
        title: "Bulanan",
        text: "Sekitar 22,5 ton telur (22,500 kg) diproduksi setiap bulan.",
        icon: Bulanan,
      },
      {
        title: "Tahunan",
        text: "Sekitar 270 ton telur setiap tahun. Estimasi penjualan ayam sekitar 10% dari total populasi per tahun.",
        icon: Tahunan,
      },
    ];

    onMounted(() => {
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              const cards = entry.target.querySelectorAll(".card-inner");
              cards.forEach((card, index) => {
                setTimeout(() => {
                  card.classList.add("animate");
                }, index * 300);
              });
              entry.target.classList.add("animate-bg");
              entry.target
                .querySelector(".section-title")
                .classList.add("animate-title");
            }
          });
        },
        { threshold: 0.3 }
      );

      if (sectionRef.value) {
        observer.observe(sectionRef.value);
      }
    });

    return { sectionRef, cards };
  },
};
</script>

<style scoped>
.data-penjualan {
  background-image: url("@/assets/bgpenjualan.png");
  background-size: 120%;
  background-position: top center;
  transition: background-position 1s ease-out, background-size 1s ease-out;
  padding: 4rem 2rem;
  color: white;
  opacity: 0;
}

.data-penjualan.animate-bg {
  opacity: 1;
  background-size: 100%;
  background-position: center center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: 2rem;
}

.section-title {
  font-size: 4rem;
  font-weight: bold;
  color: #fff;
  flex: 1;
  text-align: left;
  transform: translateY(-20px);
  opacity: 0;
  transition: transform 1s ease-out, opacity 1s ease-out;
}

.section-title.animate-title {
  transform: translateY(0);
  opacity: 1;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  flex: 3;
}

.card {
  perspective: 1000px;
}

.card-inner {
  position: relative;
  width: 250px;
  height: 300px;
  transform-style: preserve-3d;
  transition: transform 0.6s ease-in-out;
}

.card-inner.animate {
  animation: rotateIn 1s ease-out; /* Animasi masuk */
}

.card:hover .card-inner {
  transform: rotateY(180deg); /* Animasi flip saat hover */
}

.card-front,
.card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.card-front {
  background: white;
  color: #026634;
}

.card-back {
  background: white;
  color: #026634;
  transform: rotateY(180deg);
}

.icon img {
  width: 50px;
  height: 50px;
}

.card-title {
  font-size: 1.8rem;
  font-weight: bold;
}

.card-text {
  font-size: 1.2rem;
  line-height: 1.6;
  text-align: center;
  padding: 0 1rem;
}

@keyframes rotateIn {
  from {
    transform: rotateY(90deg);
    opacity: 0;
  }
  to {
    transform: rotateY(0);
    opacity: 1;
  }
}

@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }

  .section-title {
    font-size: 2rem;
    text-align: center;
  }

  .card-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }

  .card-inner {
    height: 250px;
  }

  .card-title {
    font-size: 1.2rem;
  }

  .card-text {
    font-size: 0.9rem;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 1.5rem;
  }

  .card-inner {
    height: 200px;
  }

  .card-title {
    font-size: 1rem;
  }

  .card-text {
    font-size: 0.8rem;
  }
}
</style>
