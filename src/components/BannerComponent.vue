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
      <h1 class="text-uppercase">Descubra o<br />cosmos!</h1>
      <p class="col-7">
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
  padding-top: 80px;

  font-family: "Audiowide", cursive;
  font-size: clamp(4rem, 8vw, 8rem);
  font-weight: 400;
  color: var(--white);

  animation: fade-slide-in 4s;
}

.banner-content p {
  margin-top: calc(24vh - 20px);

  font-size: clamp(1.6rem, 3vw, 2.4rem);
  animation: fade-slide-in 4s;
}

@media screen and (max-width: 900px) {

}
</style>
