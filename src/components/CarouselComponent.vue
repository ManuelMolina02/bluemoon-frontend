<template>
  <div class="carousel-container d-flex my-5 py-5">
    <b-carousel
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="3000"
    >
      <!-- CAROUSEL IMAGES -->
      <b-carousel-slide
        v-b-modal.primaryPublication
        v-for="mission in missions"
        :key="mission.title"
        :img-src="mission.url"
        class="carousel-img"
      >
      </b-carousel-slide>
    </b-carousel>

    <b-carousel
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="3100"
    >
      <!-- CAROUSEL IMAGES -->
      <b-carousel-slide
        v-b-modal.secondPublication
        v-for="mission in missions"
        :key="mission.title"
        :img-src="mission.url"
        class="carousel-img"
      >
      </b-carousel-slide>
    </b-carousel>

    <b-carousel
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="3200"
    >
      <!-- CAROUSEL IMAGES -->
      <b-carousel-slide
        v-b-modal.thirdPublication
        v-for="mission in missions"
        :key="mission.title"
        :img-src="mission.url"
        class="carousel-img"
      >
      </b-carousel-slide>
    </b-carousel>

    <!-- MODAL CONTENT -->
    <b-modal
      id="primaryPublication"
      centered
      scrollable
      ok-only
      hide-header
      button-size="lg"
      size="lg"
      title="Primary Content"
      header-class="text-white bg-dark"
      body-class="text-white bg-dark "
      footer-class="text-white bg-dark justify-content-center"
      content-class="bg-dark"
      ok-variant="outline-secondary w-50"
      ok-title="Close"
    >
      <div class="mb-4" v-for="mission in missions" :key="mission.title">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="mission.url"
          img-top
          img-alt="Card image"
          img-width="600px"
        >
          <b-card-text>
            <h3>{{ mission.title }}</h3>
            <p>{{ mission.explanation }}</p>
          </b-card-text>
        </b-card>
      </div>
    </b-modal>

    <b-modal
      id="secondPublication"
      centered
      scrollable
      ok-only
      hide-header
      button-size="lg"
      size="lg"
      title="Primary Content"
      header-class="text-white bg-dark"
      body-class="text-white bg-dark "
      footer-class="text-white bg-dark justify-content-center"
      content-class="bg-dark"
      ok-variant="outline-secondary w-50"
      ok-title="Close"
    >
      <div class="mb-4" v-for="mission in missions" :key="mission.title">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="mission.url"
          img-top
          img-alt="Card image"
          img-width="600px"
        >
          <b-card-text>
            <h3>{{ mission.title }}</h3>
            <p>{{ mission.explanation }}</p>
          </b-card-text>
        </b-card>
      </div>
    </b-modal>

    <b-modal
      id="thirdPublication"
      centered
      scrollable
      ok-only
      hide-header
      button-size="lg"
      size="lg"
      title="Primary Content"
      header-class="text-white bg-dark"
      body-class="text-white bg-dark "
      footer-class="text-white bg-dark justify-content-center"
      content-class="bg-dark"
      ok-variant="outline-secondary w-50"
      ok-title="Close"
    >
      <div class="mb-4" v-for="mission in missions" :key="mission.title">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="mission.url"
          img-top
          img-alt="Card image"
          img-width="600px"
        >
          <b-card-text>
            <h3>{{ mission.title }}</h3>
            <p>{{ mission.explanation }}</p>
          </b-card-text>
        </b-card>
      </div>
    </b-modal>
  </div>
</template>

<script>
const axios = require('axios').default;

export default {
  name: 'CarouselComponent',

  data() {
    return {
      missions: {},
    };
  },

  async created() {
    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-09-12&end_date=2021-09-16&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K',
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

.carousel-content {
  filter: grayscale(100%);
  cursor: pointer;
  transition: ease-in-out 1s;

  border-top: 2px solid rgb(112, 112, 112) !important;
  border-bottom: 2px solid rgb(112, 112, 112) !important;
}

.carousel-content:hover {
  filter: grayscale(0);
}

.card {
  border: 1px solid rgb(0 0 0 / 25%);
  border-top-left-radius: calc(1.25rem - -1px);
  border-top-right-radius: calc(1.25rem - 1px);
}

.card-img,
.card-img-top {
  border-top-left-radius: calc(1.25rem - -1px);
  border-top-right-radius: calc(1.25rem - 1px);

  width: 100%;
  height: 368px;

  background-size: cover;
}

/*border carousel*/

.carousel-content:nth-child(1) {
  border-left: 2px solid rgb(112, 112, 112) !important;
  border-right: 1px solid rgb(112, 112, 112) !important;
}

.carousel-content:nth-child(2) {
  border-left: 1px solid rgb(112, 112, 112) !important;
  border-right: 1px solid rgb(112, 112, 112) !important;
}

.carousel-content:nth-child(3) {
  border-left: 1px solid rgb(112, 112, 112) !important;
  border-right: 2px solid rgb(112, 112, 112) !important;
}

.carousel-img {
  width: calc(100vw / 3);
  height: 46vh;
  transition: linear 2s;
  object-fit: cover !important;
}
</style>
