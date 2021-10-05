<template>
  <div class="banner-container">
    <div class="logo">
      <!-- moon orbiting -->
      <img
        class="moon-image"
        src="../assets/frame.svg"
        style="width: 46px; opacity: 0.91"
        alt=""
      />

      <!-- text logo -->
      <img
        class="mx-2"
        src="../assets/bluemoon.svg"
        style="width: 232px; opacity: 0.91"
        alt=""
      />
    </div>

    <div class="background-image">
      <img :src="banner.url" />
    </div>

    <div class="banner-content">
      <h1 class="my-5 py-5 text-uppercase">Descubra o<br />cosmos!</h1>
      <p class="my-5 py-4">
        {{ banner.explanation }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BannerComponent',

  data() {
    return {
      banner: {
        explanation:
          'A cada dia, uma imagem ou fotografia diferente de nosso fascinante universo é apresentada, junto com uma breve explicação escrita por um astrônomo profissional.',
        url: 'https://img.wallpapersafari.com/desktop/1920/1080/76/67/HsdRS0.jpg',
      },
    };
  },
};
</script>

<style scoped>
.banner-content {
  position: absolute;
  top: 4%;
  left: 80px;
  z-index: 1000;

  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
}

/* BACKGROUND CONFIGS */
.background-image {
  max-height: 900px;
}

.background-image img {
  width: 100%;
  height: 1060px;
  object-fit: cover;

  position: relative;
  top: -100px;

  animation: zoom 25s linear infinite;
}

/* TEXT CONFIGS */
.banner-content h1 {
  width: auto;

  font-family: "Audiowide", cursive;
  font-size: clamp(4rem, 8vw, 8rem);
  font-weight: 400;
  color: var(--white);

  animation: fade-slide-in 4s;
}

.banner-content p {
  width: 50%;
  animation: fade-slide-in 4s;
}

@media screen and (max-width: 1440px) {
  .banner-content h1 {
    margin-bottom: 4rem !important;
  }
  .banner-content p {
    width: 65%;
    padding-top: 7rem !important;
  }
}

@media screen and (max-width: 825px) {
  .banner-content h1 {
    margin-bottom: 4rem !important;
  }
  .banner-content p {
    width: 75%;
    padding-top: 10rem !important;
  }
}

@media screen and (max-width: 480px) {
  .banner-content {
  left: 40px !important;
  }
  .logo{
    justify-content: initial;
  }
  .banner-content h1 {
    font-size: 42px;
    margin-top: 6rem !important;
    margin-bottom: 8rem !important;
  }

  .banner-content p {
    width: 90%;
    font-size: 22px;
  }
}
</style>
