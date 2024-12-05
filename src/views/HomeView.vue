<script setup lang="ts">
import TheWelcome from "../components/TheWelcome.vue";
import navigate from "../components/layout/navbar.vue";
import welcome from "../components/layout/welcome.vue";
import greet from "../components/layout/greeting.vue";
import addImage from "../components/atom/image.vue";
import production from "../components/layout/production.vue";
import reason from "../components/layout/reason.vue";
import end from "../components/layout/footer.vue";
</script>

<template>
  <!-- Main Content with Background Image -->
  <main class="margin">
    <div class="background">
      <welcome />
    </div>
    <div>
      <greet />
    </div>
    <!-- <div class="flex">
      <addImage />
    </div> -->

    <div>
      <production />
    </div>

    <div>
      <reason />
    </div>
    <div>
      <end />
    </div>
  </main>
</template>

<style scoped>
/* Main Background Styling */
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

/* --- Introduction Section --- */
.introduction {
  display: flex;
  justify-content: center; /* Memastikan konten berada di tengah secara horizontal */
  align-items: center;
  width: 100%; /* Pastikan lebar section memenuhi 100% layar */
  height: 100%;
  background-size: cover; /* Mengisi seluruh tinggi layar */
  background-color: #ffeda3; /* Memberikan background warna sesuai yang diinginkan */
  text-align: center;
}
</style>
