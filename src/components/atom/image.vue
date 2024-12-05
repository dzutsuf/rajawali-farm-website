<script>
import { defineProps } from "vue";
const props = defineProps(["image", "paragraph"]);
</script>

<template>
  <div class="image">
    <img src="@/assets/produksi.png" alt="Ayam Image" />
  </div>
</template>

<style>
.image {
  position: relative;
  top: 0;
}
</style>
