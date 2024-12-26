<script setup>
import Welcome from "../components/layout/welcome.vue";
import Greet from "../components/layout/greeting.vue";
import Tentang from "../components/layout/tentangKami.vue";
import Production from "../components/layout/production.vue";
import Reason from "../components/layout/reason.vue";
import End from "../components/layout/footer.vue";
import DataP from "../components/layout/dataPenjualan.vue";
import Prioritas from "@/components/layout/prioritas.vue";
import Mitra from "@/components/layout/mitra.vue";
</script>

<template>
  <main class="disable-scroll">
    <!-- Section Welcome -->
    <div class="background">
      <Welcome />
    </div>

    <!-- Section Greeting -->
    <divdiv id="greet" class="tentang">
      <Greet />
    </divdiv>

    <!-- Section Tentang Kami -->
    <div id="tentangKami" class="tentang">
      <Tentang />
    </div>

    <div>
      <DataP />
    </div>

    <!-- Section Production -->
    <div>
      <Production />
    </div>

    <!-- Section Reason -->
    <div>
      <Reason />
    </div>

    <div>
      <Prioritas />
    </div>

    <div>
      <Mitra />
    </div>

    <!-- Section Footer -->
    <div>
      <End />
    </div>
  </main>
</template>

<style scoped>
/* Nonaktifkan scroll */
.disable-scroll {
  overflow: hidden; /* Hilangkan scroll */
  height: 100vh; /* Batasi konten dalam satu layar */
}

/* Styling untuk latar belakang */
.background {
  background-image: url("@/assets/bghomepage.png");
  background-size: cover;
  background-position: center;
  height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  text-align: center;
  color: white;
  padding: 0 20px;
}
</style>
