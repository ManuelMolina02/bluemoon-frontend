<template>
  <div class="home">
    <!-- BANNER CONTAINER -->

    <!-- card de apresentação -->
    <banner-component />

    <!-- div image -->
    <div style="background-color: #0e0e0e">
      <img
        class="my-5 py-5 w-50"
        src="../assets/text-content.svg"
        alt=""
        style="background-color: #0e0e0e"
      />
    </div>

    <!-- CAROUSEL CONTAINER -->
    <div
      id="carousel-container"
      class="py-5"
      style="background: rgba(20, 20, 20, 0.5)"
    >
      <!-- chamada para visualizar pesquisas e fotos de missões -->
      <div class="w-75 my-5 mx-auto">
        <div>
          <h1 class="w-50 my-5 mx-auto title text-white">
            Click on a photo and preview it along with a brief explanation
            written by a professional astronomer.
          </h1>
        </div>
      </div>

      <carousel-component />
    </div>

    <!-- PRODUCT CONTAINER-->
    <div
      class="highlights-container w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.8)"
    >
      <product-component />

    </div>

    <!-- HIGHLIGHTS CONTAINER-->
    <div
      class="highlights-container w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.8)"
    >
      <cards-highlights-component />

    </div>

    <div
      class="highlights-container w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.6)"
    >
      <div class="highlights-images w-50 my-5">
        <img
          class="w-100"
          style="max-width: 678px"
          alt="Banner image"
          :src="missions[2].url"
        />
      </div>

      <div class="highlights-content text-white w-25 p-2 my-5 m-auto">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>

        <a class="text-white" href="#"><span>lear more</span></a>
      </div>
    </div>

    <form-component />
  </div>
</template>

<script>
import BannerComponent from '@/components/BannerComponent.vue';
import CarouselComponent from '@/components/CarouselComponent.vue';
import FormComponent from '@/components/FormComponent.vue';
import CardsHighlightsComponent from '@/components/CardsHighlightsComponent.vue';
import ProductComponent from '@/components/ProductComponent.vue';

const axios = require('axios').default;

export default {
  name: 'Home',
  data() {
    return {
      missions: {},
    };
  },

  async created() {
    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-09-23&end_date=2021-09-26&api_key=KMSpsJ0it2ktgbhjR8OdJbjr3WANnaQIohtcM424',
      )
      .then((response) => {
        this.missions = response.data;
        console.log(this.missions);
      })
      .catch((error) => {
        console.error(error);
      });
  },

  components: {
    BannerComponent,
    CarouselComponent,
    FormComponent,
    CardsHighlightsComponent,
    ProductComponent,
  },
};
</script>

<style scoped>
.title {
  font-size: 36px;
  line-height: 66px;
  letter-spacing: 0.16em;
}

/* HIGLIGHTS CONTAINER */

.highlights-content {
  display: flex;
  flex-direction: column;

  align-items: initial;
  justify-content: center;
}

.highlights-content a {
  width: 340px;
  height: 100px;
  padding: 20px 0;

  display: block;
  position: relative;
  transition: all 0.35s;

  font-size: 38px;
  letter-spacing: 3px;
  border: solid 2px white;
  border-radius: 0;

  text-decoration: none;
  text-align: center;
}

.highlights-content a span {
  position: relative;
  z-index: 2;
}

.highlights-content a:after {
  position: absolute;
  content: "";
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0;
  background: #dbdbdb;
  transition: all 0.5s;
}

.highlights-content a:hover {
  color: black !important;
}

.highlights-content a:hover:after {
  height: 100%;
}
</style>
