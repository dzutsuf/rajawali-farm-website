<template>
  <section ref="sectionRef" class="farm-section">
    <div class="image-grid">
      <div class="image-item top-left stagger">
        <img src="@/assets/footage1.png" alt="Eggs in a basket" />
      </div>
      <div class="image-item bottom-left stagger">
        <img src="@/assets/footage2.png" alt="Animal feeds" />
      </div>
      <div class="image-item right stagger">
        <img src="@/assets/footage3.png" alt="Chickens in a farm" />
      </div>
    </div>
    <div class="text-content">
      <h2 class="tentang stagger">Apa itu Rajawali Farm?</h2>
      <p class="stagger">
        Rajawali Farm merupakan badan usaha mandiri yang bergerak di sektor
        agrobisnis dengan fokus pada produksi ayam dan telur berkualitas yang
        berdiri di tahun 2017.
      </p>
      <h2 class="misi stagger">Misi</h2>
      <p class="stagger">
        Memperluas jaringan distribusi dan kontribusi positif pada masyarakat
        dengan menyediakan produk berkualitas yang mendukung gaya hidup sehat.
      </p>
    </div>
  </section>
</template>

<script>
import { onMounted, ref } from "vue";

export default {
  setup() {
    const sectionRef = ref(null);

    onMounted(() => {
      const observer = new IntersectionObserver(
        ([entry]) => {
          if (entry.isIntersecting) {
            const children = entry.target.querySelectorAll(".stagger");
            children.forEach((child, index) => {
              setTimeout(() => {
                child.classList.add("animate");
              }, index * 200);
            });
          }
        },
        { threshold: 0.3 }
      );

      if (sectionRef.value) {
        observer.observe(sectionRef.value);
      }
    });

    return { sectionRef };
  },
};
</script>

<style scoped>
.farm-section {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2rem;
  background-color: #fff;
}

.image-grid {
  display: grid;
  grid-template-columns: 1.5fr 2fr;
  grid-template-rows: 1fr 1fr;
  gap: 1rem;
  max-width: 800px;
  align-items: center;
}

.image-item {
  overflow: hidden;
  position: relative;
}

.image-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transform: scale(0.5);
  transition: transform 0.6s cubic-bezier(0.68, -0.55, 0.27, 1.55),
    opacity 0.6s ease;
}

.image-item.animate img {
  opacity: 1;
  transform: scale(1);
}

.image-item.top-left {
  grid-column: 1 / 2;
  grid-row: 1 / 2;
  border-top-left-radius: 50%;
  border-bottom-left-radius: 30%;
  height: 250px;
}

.image-item.bottom-left {
  grid-column: 1 / 2;
  grid-row: 2 / 3;
  border-bottom-left-radius: 50%;
  border-bottom-right-radius: 50%;
  height: 200px;
  width: 200px;
  object-fit: cover;
  object-position: center;
  margin-left: 4.8rem;
}

.image-item.right {
  grid-column: 2 / 3;
  grid-row: 1 / 3;
  border-top-right-radius: 50%;
  border-bottom-right-radius: 50%;
}

.text-content {
  flex: 1;
  margin-left: 6rem;
  color: #2c3e50;
}

.text-content h2 {
  font-size: 3rem;
  color: #026634;
  margin-bottom: 1rem;
  text-align: center;
}

.misi {
  margin-top: 3rem;
}

.text-content p {
  font-size: 1.5rem;
  line-height: 1.6;
  text-align: center;
  color: #34495e;
}

.stagger {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}

.stagger.animate {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 768px) {
  .farm-section {
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-top: 2rem;
    gap: 0;
    margin-bottom: 2rem;
  }

  .image-grid {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(2, auto);
    gap: 0;
    margin-bottom: 15px;
  }

  .image-item.top-left,
  .image-item.bottom-left,
  .image-item.right {
    width: 100%;
    height: auto;
    margin: 0;
  }

  .image-item img {
    border-radius: 20%;
  }

  .text-content {
    margin-left: 0;
    margin-top: 0;
  }

  .text-content h2 {
    font-size: 2rem;
  }

  .text-content p {
    font-size: 1rem;
    line-height: 1.5;
  }
}

@media (max-width: 480px) {
  .farm-section {
    padding: 1rem;
    text-align: center;
    align-items: center;
    gap: 0;
    margin-bottom: 2rem;
  }

  .image-grid {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(2, 1fr);
    gap: 0;
    margin-bottom: 15px;
  }

  .image-item.top-left,
  .image-item.bottom-left,
  .image-item.right {
    height: 150px;
  }

  .text-content {
    margin-top: 0;
    text-align: center;
  }

  .text-content h2 {
    font-size: 1.8rem;
  }

  .text-content p {
    font-size: 0.9rem;
    line-height: 1.4;
  }
}
</style>
