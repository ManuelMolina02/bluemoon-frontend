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
      <p class="col-6">
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
/* image banner configs */

/*limitar alty*/
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

/* content banner configs */

.banner-content {
  position: absolute;
  top: 8rem;
  left: 3rem;
  z-index: 1000;
}

.banner-content h1 {
  width: auto;
  margin-left: 4rem;

  font-family: "Audiowide", cursive;
  font-size: 8rem;
  font-weight: 400;
  color: var(--white);

  animation: fade-slide-in 4s;
}

.banner-content p {
  margin-top: 12rem;
  margin-left: 4rem;
  font-size: 2.6rem;
  animation: fade-slide-in 4s;
}

@media screen and (max-width: 1400px) {
  .banner-content {
    top: 7rem;
  }

  .banner-content p {
    margin-top: 13rem;
    width: 65%;
  }
}

@keyframes zoom {
  0% {
    transform: scale(1) rotate(0);
  }

  50% {
    transform: scale(1.3) rotate(4deg);
  }

  100% {
    transform: scale(1) rotate(0);
  }
}

@keyframes fade-slide-in {
  from {
    opacity: 0;
    transform: translateX(-300px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
</style>
