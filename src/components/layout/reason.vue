<script></script>

<template>
  <div class="reason-container">
    <h1 class="h1p">Kenapa Anda harus Memilih Kami?</h1>
    <ul class="icon-list">
      <li>
        <img src="@/assets/kualitas.png" alt="kualitas" class="img" />
        <h1 class="h1li">Kualitas Terbaik</h1>
        <p>
          Produk ayam dan telur kami diproduksi dengan standar tinggi untuk
          memastikan kesegaran dan rasa terbaik.
        </p>
      </li>
      <li>
        <img src="@/assets/tangan.png" alt="tangan" class="img" />
        <h1 class="h1li">Tangan Ahli</h1>
        <p>
          Dikelola oleh tim dengan pengalaman dan keahlian dalam memelihara
          serta memproduksi hasil ternak berkualitas.
        </p>
      </li>
      <li>
        <img src="@/assets/harga.png" alt="harga" class="img" />
        <h1 class="h1li">Harga Kompetitif</h1>
        <p>
          Produk berkualitas dengan harga yang tetap terjangkau untuk konsumen.
        </p>
      </li>
      <li>
        <img src="@/assets/pengiriman.png" alt="pengiriman" class="img" />
        <h1 class="h1li">Pengiriman Aman</h1>
        <p>
          Produk diantar dengan cepat menggunakan pengemasan yang menjaga
          kualitas dan kesegaran.
        </p>
      </li>
      <li>
        <img src="@/assets/transparansi.png" alt="transparansi" class="img" />
        <h1 class="h1li">Transparansi Proses</h1>
        <p>
          Kami terbuka mengenai cara produk dihasilkan, sehingga Anda tahu bahwa
          Anda mendapatkan yang terbaik.
        </p>
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
  display: flex; /* Membuat elemen list berjajar horizontal */
  justify-content: center; /* Memusatkan elemen list secara horizontal */
  gap: 60px; /* Jarak antar elemen list */
  list-style: none; /* Hilangkan tanda bullet pada list */
  padding: 0; /* Hilangkan padding bawaan ul */
  margin-bottom: 200px; /* Hilangkan margin bawaan ul */
}

.icon-list li {
  display: flex; /* Membuat tata letak vertikal dalam setiap li */
  flex-direction: column;
  align-items: center; /* Pusatkan isi dalam li */
  text-align: justify;
  max-width: 250px;
  width: 200px; /* Ukuran lebar gambar tetap */
  height: 107px; /* Batasi lebar setiap elemen list */
}

.icon-list li img {
  width: 200px; /* Ukuran lebar gambar tetap */
  height: 200px; /* Tinggi gambar tetap */
  object-fit: contain; /* Pastikan gambar tidak terdistorsi */
  margin: 0; /* Hilangkan margin bawaan pada gambar */
  padding: 0; /* Hilangkan padding jika ada */
}

.h1li {
  font-size: 1.5rem;
  margin: 0; /* Hilangkan margin atas dan bawah */
  padding: 0;
}

.icon-list li p {
  margin: 0; /* Hilangkan margin pada paragraf */
  padding: 10px 0; /* Jarak konsisten antara heading dan teks */
  font-size: 0.9rem; /* Sesuaikan ukuran teks */
  line-height: 1.5; /* Jarak antar baris yang nyaman */
}
</style>
