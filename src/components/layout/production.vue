<script>
import { onMounted, ref } from "vue";

export default {
  setup() {
    const sectionRefs = ref([]);

    const setRefs = (el) => {
      if (el && !sectionRefs.value.includes(el)) {
        sectionRefs.value.push(el);
      }
    };

    onMounted(() => {
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add("animate");
            }
          });
        },
        { threshold: 0.5 }
      );

      sectionRefs.value.forEach((ref) => {
        if (ref) observer.observe(ref);
      });
    });

    return { setRefs };
  },
};
</script>

<template>
  <div class="produksi">
    <h1 class="h1p">Bagaimana Kami Memproduksi Ayam dan Telur?</h1>
    <div class="content-wrapper slide-left" :ref="setRefs">
      <div class="content1">
        <img src="@/assets/produksi.png" alt="image1" class="produksi-image" />
        <p class="produksi-paragraph">
          Pakan ayam peternakan terdiri dari pelet yang mengandung karbohidrat,
          protein, vitamin, dan mineral. Selain pakan utama, suplemen seperti
          vitamin, mineral, probiotik, dan aditif pakan ditambahkan untuk
          mendukung kesehatan, pertumbuhan, dan produksi ayam. Air bersih juga
          harus tersedia setiap saat untuk mendukung pencernaan dan metabolisme
          ayam.
        </p>
      </div>
      <img src="@/assets/Ayam2.png" alt="image2" class="produksi-image" />
    </div>
    <div class="content-wrapper slide-right" :ref="setRefs">
      <img src="@/assets/produksi3.png" alt="image1" class="produksi-image2" />
      <div class="content1">
        <p class="produksi-paragraph2">
          Setelah telur dihasilkan, telur akan dipanen dengan hati-hati untuk
          menjaga kualitasnya. Telur kemudian dibersihkan, disortir berdasarkan
          ukuran dan kualitas, dan kemudian dikemas. Setelah itu, telur siap
          didistribusikan ke pasar atau konsumen melalui jaringan distribusi
          yang sudah ada, seperti pengecer atau perusahaan pengolahan makanan.
        </p>
        <img
          src="@/assets/produksi2.png"
          alt="image2"
          class="produksi-image2"
        />
      </div>
    </div>
  </div>
</template>

<style>
.produksi {
  padding-top: 50px;
  padding-bottom: 50px;
  background-color: #fbedb6;
}

.h1p {
  font-size: 2.5rem;
  margin-bottom: 20px;
  text-align: center;
}

.content-wrapper {
  display: flex;
  align-items: flex-start;
  max-width: 90%;
  margin: 0 auto;
  padding: 0 20px;
  justify-content: space-between;
  margin-bottom: 40px;
}

.content1 {
  display: flex;
}

.produksi-image {
  width: 300px;
  height: 250px;
  object-fit: cover;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
}

.produksi-image2 {
  width: 300px;
  height: 250px;
  object-fit: cover;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
}

.produksi-paragraph {
  flex: none;
  width: 700px;
  font-size: larger;
  line-height: 1.5;
  background-color: #f2c295;
  padding: 20px;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
  margin: 0;
  display: flex;
  align-items: center;
  text-align: justify;
  height: 250px;
}

.produksi-paragraph2 {
  flex: none;
  width: 700px;
  font-size: larger;
  line-height: 1.5;
  background-color: #f2c295;
  padding: 20px;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  margin: 0;
  display: flex;
  align-items: center;
  text-align: justify;
  height: 250px;
}

@media (max-width: 768px) {
  .content-wrapper {
    flex-direction: column;
    align-items: center;
    gap: 15px;
  }

  .content1 {
    flex-direction: column;
  }

  .produksi-image,
  .produksi-image2 {
    width: 80%;
    height: auto;
    border-radius: 10px;
  }

  .produksi-paragraph,
  .produksi-paragraph2 {
    width: 80%;
    border-radius: 10px;
    text-align: center;
    font-size: medium;
    padding: 15px;
    line-height: 1.4;
  }
}

@media (max-width: 480px) {
  .h1p {
    font-size: 2rem;
  }

  .content1 {
    flex-direction: column;
  }

  .produksi-image,
  .produksi-image2 {
    width: 100%;
  }

  .produksi-paragraph,
  .produksi-paragraph2 {
    width: 100%;
    font-size: small;
    padding: 10px;
    line-height: 1.3;
  }
}

@keyframes slideInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.content-wrapper {
  opacity: 0;
  transform: translateX(0);
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.slide-left.animate {
  animation: slideInLeft 0.8s ease-out forwards;
}

.slide-right.animate {
  animation: slideInRight 0.8s ease-out forwards;
}
</style>
