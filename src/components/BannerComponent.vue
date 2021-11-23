<template>
  <div id="banner">
    <div class="logo">
      <!-- moon orbiting -->
      <img
        class="moon-image"
        src="../assets/frame.svg"
        style="width: 46px; opacity: 0.91"
        alt="image-logo"
      />

      <!-- text logo -->
      <img
        class="mx-2 bluemoon-text"
        src="../assets/bluemoon.svg"
        style="width: 232px; opacity: 0.91"
        alt="text-logo"
      />
    </div>

    <div class="banner-container">
      <div class="background-image">
        <img
          :src="dataBanner.image"
          alt="banner-background"
        />
      </div>
    </div>

    <div class="banner-content" alt="conteúdo banner home">
      <h1>DESCUBRA O <br />COSMOS!</h1>
      <p class="text-white">
        {{dataBanner.description}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Banner',

  data() {
    return {
      dataBanner: {},
    };
  },

  created() {
    this.dataBanner = {
      description: 'A cada dia, uma imagem ou fotografia diferente de nosso fascinante universo é apresentada, junto com uma breve explicação escrita por um astrônomo profissional.',
      image: 'https://img.wallpapersafari.com/tablet/2560/1700/29/66/MKlOHz.jpg',
    };
  },
};
</script>

<style scoped>
/* LOGO CONFIGS */
.logo {
  position: absolute;
  z-index: 3;
  display: flex;
  justify-content: center;
  width: 100%;
  align-items: center;
  margin: 1.8rem;
}
.moon-image {
  margin-right: 0.4rem;
  animation: spin 2.6s linear infinite;
}

/* BANNER IMAGE */
.banner-container {
  overflow: hidden;
  max-height: 940px;
}

.background-image img {
  width: 100%;
  height: 1240px;
  object-fit: cover;
  filter: contrast(1.02) brightness(0.95);

  position: relative;
  top: -4vh;

  animation: zoom 25s linear infinite;
}

/* BANNER CONTENT */
.banner-content {
  filter: drop-shadow(18px 10px 0.8rem #000);

  margin: 8rem 4.2rem;
  height: 80%;
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  text-align: start;
  flex-direction: column;
  justify-content: space-between;
}

.banner-content h1 {
  font-family: "Audiowide", cursive;
  font-size: clamp(4rem, 8vw, 8rem);
  font-weight: 400;
  color: #ede3e4;
}

.banner-content p {
  width: 50%;
  font-family: "Raleway", sans-serif;
  letter-spacing: 1.6px;
  font-size: clamp(1.8rem, 2.1vw, 2.3rem);
  color: var(--dark-blue);
  text-align: initial;
}

@media screen and (max-width: 1440px) {
  .banner-content p {
    width: 65%;
  }
}
@media screen and (max-width: 875px) {
    .logo {
    margin-top: 2.4rem;
    justify-content: initial !important;
  }
  .banner-content {
    margin: 8rem 1rem;
  }
  .banner-content h1 {
    width: 100%;
    text-align: center !important;
  }
  .banner-content p {
    width: 90%;
    font-size: 26px;
  }
  .background-image img {
    width: 100%;
    height: 112vh;

    animation: none;
  }
}

@media screen and (max-width: 540px) {
  .banner-content {
    left: 40px !important;
  }

  .banner-content h1 {
    font-size: 46px;
  }
  .banner-content p {
    font-size: 22px;
  }

    .logo{
    margin: 2.4rem .8rem;
  }

  .bluemoon-text{
    width: 182px !important;
  }
}
@media screen and (max-width: 320px) {
  .banner-content h1 {
    font-size: 32px;
  }
  .banner-content p {
    width: 95%;
    font-size: 22px;
  }
}
</style>
