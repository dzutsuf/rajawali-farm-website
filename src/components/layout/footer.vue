<script>
import "font-awesome/css/font-awesome.min.css";
</script>

<template>
  <div class="footer">
    <div class="div1">
      <div class="imgh1">
        <img
          class="img"
          src="@/assets/logorajawalifarm.png"
          alt="logorajawalifarm"
        />
        <div class="content">
          <h1 class="dh1">Rajawali Farm</h1>
          <p class="d1p1">
            Jika Anda memiliki pertanyaan atau membutuhkan informasi lebih
            lanjut tentang Rajawali Farm, jangan ragu untuk menghubungi kami.
          </p>
          <!-- Ikon Instagram -->
          <div class="icon">
            <a
              href="https://www.instagram.com/rajawalifarm/"
              class="instagram-icon"
            >
              <i class="fab fa-instagram"></i>
              <!-- Ikon Instagram Font Awesome -->
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="div2">
      <h1 class="dh2">Informasi</h1>
      <div class="nophone">
        <div class="icon"><i class="fa fa-phone"></i></div>
        <h1 class="number">+62 857-0740-0991</h1>
      </div>
      <div class="nophone">
        <div class="icon"><i class="fa fa-envelope"></i></div>
        <h1 class="number">+62 857-0740-0991</h1>
      </div>
      <div class="nophone">
        <div class="icon"><i class="fa fa-map-marker"></i></div>
        <h1 class="number">+62 857-0740-0991</h1>
      </div>
    </div>
  </div>
</template>

<style>
.footer {
  background-color: #a06729;
  display: grid;
  grid-template-columns: 1fr 1fr; /* Membagi menjadi 2 kolom sama besar */
  gap: 20px; /* Jarak antara kolom */
}

.div1 {
  gap: 10px; /* Jarak antara gambar dan teks */
  margin-left: 50px;
  margin-top: 25px;
  margin-bottom: 25px;
}

.imgh1 {
  display: flex;
  gap: 10px;
}

.img {
  width: 99px;
  height: 94px;
}

.content {
  color: white;
}

.dh1 {
  margin: 0; /* Menghilangkan margin default pada h1 */
  font-size: 6vh;
  color: white;
}

.paragraph-container {
  margin-top: 10px; /* Memberikan sedikit jarak antara h1 dan paragraf */
}

.d1p1 {
  margin-bottom: 10px;
  font-size: 1rem;
}

/* Gaya untuk ikon Instagram */
.instagram-icon {
  color: white;
  font-size: 3rem;
  margin-top: 10px;
  text-decoration: none; /* Menghilangkan underline pada link */
}

.instagram-icon:hover {
  color: #d84b4b; /* Mengubah warna saat hover */
}

.div2 {
  gap: 10px; /* Jarak antara gambar dan teks */
  margin-left: 50px;
  margin-top: 25px;
  margin-bottom: 25px;
}

.dh2 {
  margin-top: 7px; /* Menghilangkan margin default pada h1 */
  font-size: 4vh;
  color: white;
}

.nophone {
  gap: 5px;
  display: flex;
  align-items: center;
}

.icon {
  color: white;
  font-size: 2rem;
}
.number {
  color: white;
  font-size: large;
}
</style>
