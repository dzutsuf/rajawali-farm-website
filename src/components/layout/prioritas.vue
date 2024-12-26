<template>
  <div class="prioritas">
    <div class="prioritas-container">
      <img
        src="@/assets/footage5.png"
        alt="Ayam dan Telur"
        class="prioritas-image"
      />
      <p class="prioritas-text">
        "Dari farm ke meja makan Anda, kualitas adalah prioritas kami."-
        Rajawali Farm
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "PrioritasSection",
};
</script>

<style scoped>
.prioritas {
  background-color: #fff3b0;
  padding: 0px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.prioritas-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  width: 100%;
  flex-wrap: wrap;
  gap: 1rem;
}

.prioritas-image {
  max-width: 300px;
  height: auto;
  flex-shrink: 0;
}

.prioritas-text {
  font-size: 2rem;
  color: #000;
  line-height: 1.8;
  text-align: center;
  max-width: 800px;
}

@media (max-width: 768px) {
  .prioritas-container {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .prioritas-image {
    max-width: 200px;
  }

  .prioritas-text {
    font-size: 1.5rem;
    line-height: 1.6;
  }
}

@media (max-width: 480px) {
  .prioritas-image {
    max-width: 150px;
  }

  .prioritas-text {
    font-size: 1.2rem;
    line-height: 1.5;
  }
}
</style>
