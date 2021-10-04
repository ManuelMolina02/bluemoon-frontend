<template>
  <div class="home">
    <!--  CONTAINER -->

    <!-- card de apresentação -->

    <banner-component id="section-home" />

    <!-- div image -->
    <div class="div-image">
      <img
        class="my-5 py-5 col-6"
        src="../assets/img-div.svg"
        alt=""
        style="background-color: #0e0e0e"
      />
    </div>

    <!-- CAROUSEL CONTAINER -->
    <div
      id="section-gallery"
      class="py-5"
      style="background: rgba(20, 20, 20, 0.5)"
    >
      <div class="w-75 my-5 mx-auto">
        <div>
          <h1 class="my-5 mx-auto title text-white">
            Clique em uma foto e visualize-a junto com uma breve explicação
            escrita por um astrônomo profissional.
          </h1>
        </div>
      </div>

      <carousel-component />
    </div>

    <!-- PRODUCT CONTAINER-->
    <div
      id="section-product"
      class="w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.8)"
    >
      <product-component />
    </div>

    <!-- HIGHLIGHTS CONTAINER-->
    <div
      id="section-highlights"
      class="highlights-container w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.8)"
    >
      <highlights-component />
    </div>

    <!-- FORM CONTAINER-->

    <div id="section-form" class="form-container py-5 my-5">
      <p class="w-50 mx-auto text-center">
        Realize agora o seu cadastro para receber mais informações sobre como
        ficar por dentro das últimas notícias do mundo intergaláctico!
      </p>
      <form-component />
    </div>
  </div>
</template>

<script>
import BannerComponent from '@/components/BannerComponent.vue';
import CarouselComponent from '@/components/CarouselComponent.vue';
import FormComponent from '@/components/FormComponent.vue';
import HighlightsComponent from '@/components/HighlightsComponent.vue';
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
    HighlightsComponent,
    ProductComponent,
  },
};
</script>

<style scoped>
.div-image {
  background-color: #0e0e0e;
  position: relative;
}
.title {
  width: 70%;
  font-family: "Oxygen", sans-serif;

  letter-spacing: 6px;
  font-size: 2.6rem;
  font-weight: 300;
  color: aliceblue;
  word-break: break-word;
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
