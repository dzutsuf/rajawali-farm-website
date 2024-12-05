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

    <!-- Section 1 -->
    <div class="content-wrapper slide-left" :ref="setRefs">
      <img src="@/assets/produksi.png" alt="image1" class="produksi-image" />
      <p class="produksi-paragraph">
        Pakan ayam peternakan terdiri dari pelet yang mengandung karbohidrat,
        protein, vitamin, dan mineral. Selain pakan utama, suplemen seperti
        vitamin, mineral, probiotik, dan aditif pakan ditambahkan untuk
        mendukung kesehatan, pertumbuhan, dan produksi ayam. Air bersih juga
        harus tersedia setiap saat untuk mendukung pencernaan dan metabolisme
        ayam.
      </p>
      <img src="@/assets/Ayam2.png" alt="image2" class="produksi-image" />
    </div>

    <!-- Section 2 -->
    <div class="content-wrapper slide-right" :ref="setRefs">
      <img src="@/assets/produksi3.png" alt="image1" class="produksi-image2" />
      <p class="produksi-paragraph2">
        Setelah telur dihasilkan, telur akan dipanen dengan hati-hati untuk
        menjaga kualitasnya. Telur kemudian dibersihkan, disortir berdasarkan
        ukuran dan kualitas, dan kemudian dikemas. Setelah itu, telur siap
        didistribusikan ke pasar atau konsumen melalui jaringan distribusi yang
        sudah ada, seperti pengecer atau perusahaan pengolahan makanan.
      </p>
      <img src="@/assets/produksi2.png" alt="image2" class="produksi-image2" />
    </div>
  </div>
</template>

<style>
.produksi {
  padding-top: 25px;
  padding-bottom: 25px;
}

.h1p {
  font-size: 2.5rem;
  margin-bottom: 20px;
  text-align: center;
}

.content-wrapper {
  display: flex; /* Default tata letak sejajar horizontal */
  align-items: flex-start;
  gap: 0; /* Hilangkan gap agar terlihat menyatu */
  max-width: 90%;
  margin: 0 auto;
  padding: 0 20px;
}

.produksi-image {
  width: 300px; /* Default lebar gambar */
  height: auto; /* Menjaga proporsi gambar */
  border-top-left-radius: 10px; /* Radius atas kiri */
  border-bottom-left-radius: 10px; /* Radius bawah kiri */
}

.produksi-image2 {
  width: 300px; /* Default lebar gambar */
  height: auto; /* Menjaga proporsi gambar */
}

.produksi-paragraph {
  flex: 1;
  font-size: 1rem;
  line-height: 1.5;
  background-color: #f2c295; /* Warna background */
  padding: 20px; /* Tambahkan padding untuk teks */
  border-top-right-radius: 10px; /* Radius atas kanan */
  border-bottom-right-radius: 10px; /* Radius bawah kanan */
  margin: 0; /* Hilangkan margin agar menyatu dengan gambar */
  display: flex; /* Membuat teks memenuhi area */
  align-items: center; /* Memusatkan teks secara vertikal */
  text-align: justify;
  height: 180px;
}

.produksi-paragraph2 {
  flex: 1;
  font-size: 1rem;
  line-height: 1.5;
  background-color: #f2c295; /* Warna background */
  padding: 20px; /* Tambahkan padding untuk teks */
  border-top-left-radius: 10px; /* Radius atas kanan */
  border-bottom-left-radius: 10px; /* Radius bawah kanan */
  margin: 0; /* Hilangkan margin agar menyatu dengan gambar */
  display: flex; /* Membuat teks memenuhi area */
  align-items: center; /* Memusatkan teks secara vertikal */
  text-align: justify;
  height: 180px;
}

/* Responsif untuk layar kecil */
@media (max-width: 768px) {
  .content-wrapper {
    flex-direction: column; /* Tata letak vertikal */
    align-items: center;
    gap: 15px; /* Jarak antar elemen */
  }

  .produksi-image {
    width: 80%; /* Gambar lebih proporsional */
    border-radius: 10px; /* Radius penuh di layar kecil */
  }

  .produksi-paragraph {
    border-radius: 10px; /* Radius penuh di layar kecil */
    text-align: center; /* Teks rata tengah */
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

/* Initial State */
.content-wrapper {
  opacity: 0;
  transform: translateX(0); /* Default transform */
  transition: opacity 0.3s ease, transform 0.3s ease;
}

/* Slide Left */
.slide-left.animate {
  animation: slideInLeft 0.8s ease-out forwards;
}

/* Slide Right */
.slide-right.animate {
  animation: slideInRight 0.8s ease-out forwards;
}
</style>
