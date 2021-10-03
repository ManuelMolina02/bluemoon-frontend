<template>
  <div class="banner-container mx-auto">

    <div class="banner-container">
      <div class="background-image">
        <img :src="missions.url" />
      </div>

      <div class="banner-content">
        <h1 class="text-uppercase">
          {{ missions.title }}
        </h1>
        <p>
          {{ missions.explanation }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BannerComponent',

  data() {
    return {
      missions: {
        copyright: 'CARA Project',
        date: '2021-09-10',
        explanation:
          'A cada dia, uma imagem ou fotografia diferente de nosso fascinante universo é apresentada, junto com uma breve explicação escrita por um astrônomo profissional.',
        media_type: 'image',
        service_version: 'v1',
        title: 'Descubra o cosmos! ',
        url: 'https://img.wallpapersafari.com/desktop/1920/1080/76/67/HsdRS0.jpg',
      },
    };
  },
};
</script>

<style scoped>
/* image banner configs */

.background-image img {
  width: 100%;
  height: 820px;
  display: block;

  animation: zoom 25s linear infinite;
}

/* content banner configs */

.banner-content {
  position: absolute;
  top: 10rem;
  left: 3rem;
  z-index: 1000;
}

.banner-content h1 {
  font-family: "Audiowide", cursive;
  color: var(--white);
  width: 40%;
  font-size: 118px;
  font-weight: 400;
  margin-left: 8rem;
  animation: fade-slide-in 4s;
}

.banner-content p {

  margin-top: 180px;
  margin-left: 8rem;
  width: 35%;
  font-size: 36px;
  animation: fade-slide-in 4s;
}

@keyframes zoom {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(1.3);
  }

  100% {
    transform: scale(1);
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
