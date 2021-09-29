<template>
  <div class="home">
    <!-- BANNER CONTAINER -->
    <div>
      <img class="w-100" alt="Banner image" :src="banner.urlBigImage" />

      <img src="../assets/image-content.svg" alt="" />
    </div>

    <div>
      <h1 class="title">{{ banner.title }}</h1>
    </div>
    <br>
    <br>

    <!-- CAROUSEL CONTAINER -->
    <div class="carousel-container d-flex">
      <!-- PRIMARY -> CAROUSEL CONTAINE -->
      <b-carousel
        class="carousel-content"
        style="text-shadow: 0px 0px 2px #000"
        no-animation
        indicators
      >
        <!-- CAROUSEL IMAGES -->
        <b-carousel-slide
          v-b-modal.primaryPublication
            v-for="mission in missions"
            :key="mission.title"
          :img-src="mission.url"
        >
        <!--
          <b-modal id="primaryPublication" centered ok-only lazy>
            <p>
              {{ mission.title }}

              <b-button
                v-b-popover="mission.date"
                title="Publication Date"
                >learn more</b-button
              >
            </p>
          </b-modal>
          -->
        </b-carousel-slide>
      </b-carousel>
    </div>
  </div>
</template>

<script>
const axios = require('axios').default;

export default {
  name: 'Home',
  data() {
    return {
      missions: {},
      banner: {
        title: 'Unwrapped: Five Decade Old Lunar Selfie',
        explanation:
          "Here is one of the most famous pictures from the Moon -- but digitally reversed. Apollo 11 landed on the moon in 1969 and soon thereafter many pictures were taken, including an iconic picture of Buzz Aldrin taken by Neil Armstrong. The original image captured not only the magnificent desolation of an unfamiliar world, but Armstrong himself reflected in Aldrin's curved visor. Enter modern digital technology. In the featured image, the spherical distortion from Aldrin's helmet has been reversed. The result is the famous picture -- but now featuring Armstrong himself from Aldrin's perspective. Even so, since Armstrong took the picture, the image is effectively a five-decade old lunar selfie. The original visor reflection is shown on the left, while Earth hangs in the lunar sky on the upper right. A foil-wrapped leg of the Eagle lander is prominently visible. Preparations to return humans to the Moon in the next few years include the Artemis program, an international collaboration led by NASA",
        datePublication: '2021 September 27',
        urlReference: 'https://apod.nasa.gov/apod/ap210927.html',
        urlImage:
          'https://apod.nasa.gov/apod/image/2109/AldrinVisorCrop_Apollo11_1080.jpg',
        urlBigImage:
          'https://apod.nasa.gov/apod/image/2109/AldrinVisor_Apollo11_4096.jpg',
      },
    };
  },
  async created() {
    await axios.get('https://api.nasa.gov/planetary/apod?start_date=2021-08-28&end_date=2021-09-28&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K')
      .then((response) => {
        this.missions = response.data;
        console.log(this.missions);
      })
      .catch((error) => {
        console.error(error);
      });
  },
};
</script>

<style scoped>
.carousel-container {
  align-items: center;
}

.carousel-content {
  filter: grayscale(100%);
}
.carousel-content:hover {
  transition-delay: 0.2s;
  filter: grayscale(0);
}

.carousel-item img {
  max-width: 100% !important;
  height: auto !important;
}

.title {
  font-family: Orbitron;
  font-size: 88px;
  line-height: 120px;
  letter-spacing: 0.1em;

  color: #ffffff;
  opacity: 0.87;
}
</style>
