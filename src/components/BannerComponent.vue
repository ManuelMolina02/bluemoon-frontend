<template>
  <div class="banner-container mx-auto">
    <b-card
      overlay
      :img-src="missions.url"
      text-variant="white"
      style="border: none !important;"
    >
      <b-card-text class="banner-content m-5">
          <h1 class="w-50" style="margin-top: 80px">{{missions.title}}</h1>
          <p class="w-50" style="margin-top: 260px">{{missions.explanation}}</p>
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
          'Discover the cosmos! Each day a different image or photograph of our fascinating universe is featured, along with a brief explanation written by a professional astronomer.',
        media_type: 'image',
        service_version: 'v1',
        title: 'Astronomy Picture of the Day',
        url: 'https://img.wallpapersafari.com/desktop/1920/1080/76/67/HsdRS0.jpg',
      },
    };
  },

};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.banner-container{
    max-width: 1580px;
    border: none !important;

    font-family: Quantico;
}

</style>
