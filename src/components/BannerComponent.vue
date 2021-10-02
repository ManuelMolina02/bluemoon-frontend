<template>
  <div class="banner-container mx-auto">
    <b-card
      overlay
      :img-src="missions.url"
      img-height="820px"
      text-variant="white"
      style="border: none !important"
    >
      <b-card-text class="banner-content m-5">
        <h1>{{ missions.title }}</h1>
        <p>{{ missions.explanation }}</p>
      </b-card-text>
    </b-card>
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
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.banner-container {
  border: none !important;
}

.banner-content h1 {
  font-family: "Tourney", cursive;
  width: 35%;

  font-size: 108px;
  margin-top: 20px;
  margin-left: 8rem;
}

.banner-content p {
  margin-top: 220px;
  margin-left: 8rem;
  width: 35%;
}
</style>
