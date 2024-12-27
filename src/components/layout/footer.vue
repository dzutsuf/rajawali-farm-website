<script>
import "font-awesome/css/font-awesome.min.css";

export default {
  mounted() {
    const footer = document.querySelector(".footer");
    const observer = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) {
          footer.classList.add("animate-footer");
        }
      },
      { threshold: 0.1 }
    );
    observer.observe(footer);
  },
};
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
          <div class="icon">
            <a
              href="https://www.instagram.com/rajawalifarm/"
              class="instagram-icon"
              target="_blank"
              rel="noopener noreferrer"
            >
              <i class="fab fa-instagram"></i>
            </a>
          </div>
        </div>
      </div>
    </div>
    <div class="div2">
      <h1 class="dh2">Informasi</h1>
      <div class="nophone">
        <div class="icon2"><i class="fa fa-phone"></i></div>
        <h1 class="number">+62 0822-1442-6665</h1>
      </div>
      <div class="nophone">
        <div class="icon2"><i class="fa fa-envelope"></i></div>
        <h1 class="number">ATU110714@gmail.com</h1>
      </div>
      <div class="nophone">
        <div class="icon2"><i class="fa fa-map-marker"></i></div>
        <h1 class="number">
          <a
            href="https://maps.app.goo.gl/VYcE6Wzz6Ej7yRvF9"
            target="_blank"
            rel="noopener noreferrer"
          >
            Kelinci road, Raharja, Kec. Tanjungsari, Kabupaten Sumedang, Jawa
            Barat 45362
          </a>
        </h1>
      </div>
    </div>
  </div>
</template>

<style>
.footer {
  background-color: #a06729;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  padding: 20px;
  opacity: 0;
  transform: translateY(100px);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.div1,
.div2 {
  margin: 20px;
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
  margin: 0;
  font-size: 6vh;
  color: white;
}

.d1p1 {
  margin-bottom: 10px;
  font-size: 1rem;
}

.instagram-icon {
  color: white;
  font-size: 3rem;
  margin-top: 10px;
  text-decoration: none;
}

.instagram-icon:hover {
  color: #d84b4b;
}

.dh2 {
  margin-top: 7px;
  font-size: 4vh;
  color: white;
}

.nophone {
  display: flex;
  align-items: center;
}

.icon2 {
  color: white;
  font-size: 2rem;
  min-width: 40px;
  text-align: center;
}

.number {
  color: white;
  font-size: large;
  margin-left: 10px;
  font-family: "Times New Roman", Times, serif;
  font-weight: 600;
}

@media screen and (max-width: 768px) {
  .footer {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .imgh1 {
    justify-content: center;
  }

  .dh1,
  .dh2 {
    font-size: 4vh;
  }

  .nophone {
    justify-content: center;
  }

  .number {
    margin-left: 0;
  }
}

/* Animasi muncul dari bawah */
.animate-footer {
  opacity: 1;
  transform: translateY(0);
}
</style>
