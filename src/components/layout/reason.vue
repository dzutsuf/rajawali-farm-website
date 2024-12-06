<script>
export default {
  data() {
    return {
      reasons: [
        {
          image: new URL("@/assets/kualitas.png", import.meta.url).href,
          title: "Kualitas Terbaik",
          description:
            "Produk ayam dan telur kami diproduksi dengan standar tinggi untuk memastikan kesegaran dan rasa terbaik.",
        },
        {
          image: new URL("@/assets/tangan.png", import.meta.url).href,
          title: "Tangan Ahli",
          description:
            "Dikelola oleh tim dengan pengalaman dan keahlian dalam memelihara serta memproduksi hasil ternak berkualitas.",
        },
        {
          image: new URL("@/assets/harga.png", import.meta.url).href,
          title: "Harga Kompetitif",
          description:
            "Produk berkualitas dengan harga yang tetap terjangkau untuk konsumen.",
        },
        {
          image: new URL("@/assets/pengiriman.png", import.meta.url).href,
          title: "Pengiriman Aman",
          description:
            "Produk diantar dengan cepat menggunakan pengemasan yang menjaga kualitas dan kesegaran.",
        },
        {
          image: new URL("@/assets/transparansi.png", import.meta.url).href,
          title: "Transparansi Proses",
          description:
            "Kami terbuka mengenai cara produk dihasilkan, sehingga Anda tahu bahwa Anda mendapatkan yang terbaik.",
        },
      ],
      activeIndex: null, // Menyimpan indeks elemen yang aktif
    };
  },
  methods: {
    toggleContent(index) {
      // Menampilkan atau menyembunyikan konten berdasarkan klik
      this.activeIndex = this.activeIndex === index ? null : index;
    },
  },
};
</script>

<template>
  <div class="reason-container">
    <h1 class="h1p">Kenapa Anda harus Memilih Kami?</h1>
    <ul class="icon-list">
      <li
        v-for="(item, index) in reasons"
        :key="index"
        :class="{ active: activeIndex === index }"
        @click="toggleContent(index)"
        @mouseenter="activeIndex = index"
        @mouseleave="activeIndex = null"
      >
        <img :src="item.image" :alt="item.title" class="img" />
        <h1 class="h1li">{{ item.title }}</h1>
        <p v-if="activeIndex === index">{{ item.description }}</p>
      </li>
    </ul>
  </div>
</template>

<style>
.h1p {
  font-size: 2.5rem;
  margin-bottom: 20px;
  text-align: center;
}

.icon-list {
  display: flex;
  justify-content: center;
  gap: 60px;
  list-style: none;
  padding: 0;
  margin-bottom: 200px;
  flex-wrap: wrap;
}

.icon-list li {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: justify;
  max-width: 250px;
  width: 200px;
  cursor: pointer;
  transition: transform 0.3s ease;
  position: relative;
}

.icon-list li img {
  width: 200px;
  height: 200px;
  object-fit: contain;
  margin: 0;
  padding: 0;
}

.h1li {
  font-size: 1.5rem;
  margin: 0;
  padding: 0;
}

.icon-list li p {
  margin: 0;
  padding: 10px 0;
  font-size: 0.9rem;
  line-height: 1.5;
  display: none;
  opacity: 0;
  transition: opacity 0.3s ease;
  position: absolute;
  bottom: -10px;
  text-align: center;
  background: #ffffff;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.icon-list li.active p,
.icon-list li:hover p {
  display: block;
  opacity: 1;
}

.icon-list li:hover {
  transform: scale(1.05);
}

@media (max-width: 768px) {
  .h1p {
    font-size: 2rem;
    margin-bottom: 15px;
  }

  .icon-list {
    gap: 30px;
  }

  .icon-list li {
    max-width: 200px;
    width: 180px;
  }

  .icon-list li img {
    width: 150px;
    height: 150px;
  }

  .h1li {
    font-size: 1.3rem;
  }

  .icon-list li p {
    font-size: 0.8rem;
  }
}

@media (max-width: 480px) {
  .h1p {
    font-size: 1.8rem;
    margin-bottom: 10px;
  }

  .icon-list li {
    max-width: 180px;
    width: 160px;
  }

  .icon-list li img {
    width: 120px;
    height: 120px;
  }

  .h1li {
    font-size: 1.1rem;
  }

  .icon-list li p {
    font-size: 0.75rem;
  }
}
</style>
