<template>
  <div class="mitra-section">
    <h2 class="title">Mitra Pemesanan</h2>
    <p class="description">
      Rajawali Farm secara berkala melayani pesanan dari berbagai mitra dengan
      komitmen pengiriman tepat waktu dan kualitas produk yang terjamin dengan
      jaringan mitra bisnis dari kalangan retail dan pasar lokal.
    </p>
    <div class="isi">
      <div class="mitra-list">
        <div class="mitra-item" v-for="(item, index) in mitra" :key="index">
          <div class="icon" :style="{ backgroundColor: item.color }"></div>
          <p class="text" v-html="item.text"></p>
        </div>
      </div>
      <div class="map">
        <img src="@/assets/footage6.png" alt="Peta Mitra Pemesanan" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mitra: [
        {
          color: "#008000",
          text: "<b>Retailer lokal di wilayah Depok, Bekasi, Jakarta, dan Cianjur.</b>",
        },
        {
          color: "#008000",
          text: "Pedagang telur grosir yang memasok ke supermarket, pasar tradisional, dan toko makanan sehat.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.mitra-section {
  text-align: center;
  padding: 4rem;
}
.title {
  font-size: 3rem;
  margin-bottom: 4rem;
}
.description {
  font-size: 1.5rem;
  margin-bottom: 2rem;
  padding-left: 40px;
  padding-right: 40px;
  font-weight: 700;
}

.isi {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 2rem;
  padding-left: 40px;
  padding-right: 40px;
}

.mitra-list {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 2rem;
  flex: 1;
}
.mitra-item {
  display: flex;
  align-items: center;
}
.icon {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  margin-right: 1rem;
}
.text {
  font-size: 1.5rem;
  text-align: left;
}
.map {
  margin-top: 2rem;
  flex: 1;
}
.map img {
  max-width: 100%;
  height: auto;
  border: 1px solid #ddd;
}

@media (max-width: 768px) {
  .mitra-section {
    padding: 2rem;
  }

  .title {
    font-size: 2rem;
  }

  .description {
    font-size: 1.2rem;
    padding-left: 20px;
    padding-right: 20px;
  }

  .isi {
    flex-direction: column;
    align-items: center;
  }

  .mitra-list {
    align-items: center;
  }

  .text {
    font-size: 1.2rem;
  }

  .map {
    margin-top: 1rem;
  }
}

@media (max-width: 480px) {
  .title {
    font-size: 1.5rem;
  }

  .description {
    font-size: 1rem;
  }

  .text {
    font-size: 1rem;
  }

  .icon {
    width: 15px;
    height: 15px;
  }

  .map {
    margin-top: 0.5rem;
  }
}
</style>
