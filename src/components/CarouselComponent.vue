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
        v-for="mission in missionsOne"
        :key="mission.title"
      >
        <img :src="mission.url" class="carousel-img" />
      </div>
    </b-carousel>

    <b-carousel
      v-b-modal.secondPublication
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="3700"
    >
      <div
        role="listitem"
        class="carousel-item"
        v-for="mission in missionsTwo"
        :key="mission.title"
      >
        <img :src="mission.url" class="carousel-img" />
      </div>
    </b-carousel>

    <b-carousel
      v-b-modal.thirdPublication
      class="carousel-content"
      style="text-shadow: 0px 0px 2px #000"
      fade
      indicators
      :interval="4000"
    >
      <div
        role="listitem"
        class="carousel-item"
        v-for="mission in missionsTree"
        :key="mission.title"
      >
        <img :src="mission.url" class="carousel-img" />
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
      <div class="mb-4" v-for="mission in missionsOne" :key="mission.missionsOne">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="mission.url"
          img-top
          img-alt="Card image"
          img-width="700px"
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
      <div class="mb-4" v-for="mission in missionsTwo" :key="mission.missionsTwo">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="mission.url"
          img-top
          img-alt="Card image"
          img-width="700px"
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
      <div class="mb-4" v-for="mission in missionsTree" :key="mission.missionsTree">
        <b-card
          class="my-3 text-white bg-dark"
          :img-src="mission.url"
          img-top
          img-alt="Card image"
          img-width="700px"
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
      missionsOne: {},
      missionsTwo: {},
      missionsTree: {},
    };
  },

  async created() {
    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-08-10&end_date=2021-08-14&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K',
      )
      .then((response) => {
        this.missionsOne = response.data;
        console.log(this.missionsOne);
      });
    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-08-17&end_date=2021-08-20&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K',
      )

      .then((response) => {
        this.missionsTwo = response.data;
        console.log(this.missionsTwo);
      })
      .catch((error) => {
        console.error(error);
      });

    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-08-26&end_date=2021-08-31&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K',
      )

      .then((response) => {
        this.missionsTree = response.data;
        console.log(this.missionsTree);
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
