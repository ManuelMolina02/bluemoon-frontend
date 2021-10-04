<template>
  <div class="carousel-container d-flex my-5 py-5">
    <b-carousel
            v-b-modal.primaryPublication
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="3500"
    >
      <div
        role="listitem"
        class="carousel-item"
        v-for="mission in missions"
        :key="mission.title"
      >
        <img :src="mission.url" class="carousel-img" />
      </div>
    </b-carousel>

    <b-carousel
            v-b-modal.primaryPublication
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="3700"
    >
      <div
        role="listitem"
        class="carousel-item"
        v-for="mission in missions"
        :key="mission.title"
      >
        <img :src="mission.url" class="carousel-img" />
      </div>
    </b-carousel>

    <b-carousel
      v-b-modal.primaryPublication
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="4000"
    >
      <div
        role="listitem"
        class="carousel-item"
        v-for="data in datas"
        :key="data.title"
      >
        <img :src="data.url" class="carousel-img" />
      </div>
    </b-carousel>

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
      <div class="mb-4" v-for="data in datas" :key="data.title">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="data.url"
          img-top
          img-alt="Card image"
          img-width="700px"
        >
          <b-card-text>
            <h3>{{ data.title }}</h3>
            <p>{{ data.explanation }}</p>
          </b-card-text>
        </b-card>
      </div>
    </b-modal>
  </div>
</template>

<script>
import dataFake from '../../data-fake.json';

const axios = require('axios').default;

export default {
  name: 'CarouselComponent',

  data() {
    return {
      missions: {},
      datas: dataFake,
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

.carousel-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.carousel-content {
  filter: grayscale(100%);
  cursor: pointer;
  transition: ease-in-out 1s;
  border: solid 2px #333333;

}

.carousel-content:hover {
  filter: grayscale(0);
}

.carousel-img {
  width: calc(100vw / 3) !important;
  height: 40vh;

  object-fit: cover !important;
}

.carousel-item {
  transition: linear 2s;
}

/* MODAL */
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

</style>
