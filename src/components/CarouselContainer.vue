<template>
  <div class="carousel-container d-flex my-5 py-5">
    <b-carousel
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      interval="3500"
    >
      <!-- CAROUSEL IMAGES -->
      <b-carousel-slide
        v-b-modal.primaryPublication
        v-for="mission in missions"
        :key="mission.title"
        :img-src="mission.url"
        class="img-fluid d-block"
        style="max-width: 860px; max-height: 420px; object-fit: cover"
      >
      </b-carousel-slide>
    </b-carousel>

    <b-carousel
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      interval="3500"
    >
      <!-- CAROUSEL IMAGES -->
      <b-carousel-slide
        v-b-modal.secondPublication
        v-for="mission in missions"
        :key="mission.title"
        :img-src="mission.url"
        class="img-fluid d-block"
        style="max-width: 860px; max-height: 420px; object-fit: cover"
      >
      </b-carousel-slide>
    </b-carousel>

    <b-carousel
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      interval="3500"
    >
      <!-- CAROUSEL IMAGES -->
      <b-carousel-slide
        v-b-modal.thirdPublication
        v-for="mission in missions"
        :key="mission.title"
        :img-src="mission.url"
        class="img-fluid d-block"
        style="max-width: 860px; max-height: 420px; object-fit: cover"
      >
      </b-carousel-slide>
    </b-carousel>

    <!-- MODAL CONTENT -->
    <b-modal id="primaryPublication" scrollable title="Primary Content">
      <p class="my-4" v-for="mission in missions" :key="mission.title">
        {{ mission.title }}
      </p>
    </b-modal>

    <b-modal id="secondPublication" scrollable title="Second Contents">
      <p class="my-4" v-for="mission in missions" :key="mission.title">
        {{ mission.title }}
      </p>
    </b-modal>

    <b-modal id="thirdPublication" scrollable title="Third Content">
      <p class="my-4" v-for="mission in missions" :key="mission.title">
        {{ mission.title }}
      </p>
    </b-modal>
  </div>
</template>

<script>
const axios = require('axios').default;

export default {
  name: 'CarouselContainer',

  data() {
    return {
      missions: {},
    };
  },
  async created() {
    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-08-28&end_date=2021-09-28&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K',
      )
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
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* CAROUSEL CONTAINER */
.carousel-container {
  align-items: center;
}

.carousel-content {
  filter: grayscale(100%);
}

.carousel-content:hover {
  transition-delay: 0.2s;
  animation: filter-animation 3s forwards;
}

.carousel-item img {
  max-width: 100% !important;
  height: auto !important;
}

@keyframes filter-animation {
  0% {
    filter: hue-rotate(154deg) saturate(2);
  }

  100% {
    filter: hue-rotate(0) ;
  }
}
</style>
