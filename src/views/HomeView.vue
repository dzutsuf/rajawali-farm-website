<script setup>
import FlyingButton from "../components/atom/FlyingButton.vue";
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
    <div class="background">
      <Welcome />
    </div>

    <div id="greet" class="tentang">
      <Greet />
    </div>

    <div id="tentangKami" class="tentang">
      <Tentang />
    </div>

    <div>
      <DataP />
    </div>

    <div>
      <Production />
    </div>

    <div>
      <Reason />
    </div>

    <div>
      <Prioritas />
    </div>

    <div>
      <Mitra />
    </div>

    <div>
      <End />
    </div>

    <FlyingButton />
  </main>
</template>

<style scoped>
.disable-scroll {
  overflow: hidden;
  height: 100vh;
}

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
