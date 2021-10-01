<template>
  <div>
    <b-card
      id="banner-container"
      :img-src="banner.urlBigImage"
      :title="banner.title"
      class="banner-container mx-auto"
      text-variant="white"
      img-alt="Banner Image"
      overlay
    >
      <b-card-text>
        {{ banner.description }}
      </b-card-text>

    </b-card>

  </div>
</template>

<script>
export default {
  name: 'BannerContainer',

  data() {
    return {
      banner: {
        title: 'Astronomy Picture of the Day',
        description:
          'Discover the cosmos! Each day a different image or photograph of our fascinating universe is featured',
        urlBigImage:
          'https://img.wallpapersafari.com/desktop/1440/900/76/67/HsdRS0.jpg',
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* BANNER CONTAINER */
.banner-container {
  /*
  filter: grayscale(0.2) contrast(180%) saturate(1) hue-rotate(184deg);
  */

  max-width: 1678px;
  border: none !important;

  font-family: "Quantico", sans-serif;
}

/* image area */
.card-img,
.card-img-top,
.card-img-bottom {
  width: 100%;
  height: 816px;
}

.banner-container h4 {
  width: 55%;
  padding-left: 80px;
  font-size: 88px !important;
  letter-spacing: 10px;
  font-weight: bold;
  text-align: initial !important;
}

.banner-container p {
  width: 35%;
  padding-left: 80px;

  margin-top: 160px !important;
  font-size: 40px;
  text-align: initial !important;
}

</style>
