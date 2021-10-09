<template>
  <div class="home">
    <!--  CONTAINER -->

    <!-- card de apresentação -->
    <div id="home">
      <banner-component />
    </div>

    <!-- div image -->
    <div class="div-image">
      <img class="my-5 py-5 col-6" src="../assets/img-div.svg" alt="" />
    </div>

    <!-- CAROUSEL CONTAINER -->
    <div id="gallery" class="py-5" style="background: #182338">
      <div class="w-75 my-5 mx-auto">
        <div>
          <h1 class="my-5 mx-auto title">
            Clique em uma foto e visualize-a junto com uma breve explicação
            escrita por um astrônomo profissional.
          </h1>
        </div>
      </div>

      <carousel-component />
    </div>

    <!-- PRODUCT CONTAINER-->
    <div
      id="product"
      class="w-100 d-flex mx-auto"
      style="background: #d0dcf5"
    >
      <product-component />
    </div>

    <!-- HIGHLIGHTS CONTAINER-->
    <div
      id="highlights"
      class="highlights-container w-100 d-flex mx-auto"
      style="background: #1a2845"
    >
      <highlights-component />
    </div>

<<<<<<< Updated upstream
    <!-- FORM CONTAINER-->

    <div id="form" class="form-container py-5 my-5">
      <p class="w-50 mx-auto text-center">
        Realize agora o seu cadastro para receber mais informações sobre como
        ficar por dentro das últimas notícias do mundo intergaláctico!
      </p>
      <form-component />
    </div>
=======
    <form-component />
>>>>>>> Stashed changes
  </div>
</template>

<script>
import BannerComponent from '@/components/BannerComponent.vue';
import CarouselComponent from '@/components/CarouselComponent.vue';
import FormComponent from '@/components/FormComponent.vue';
import HighlightsComponent from '@/components/HighlightsComponent.vue';
import ProductComponent from '@/components/ProductComponent.vue';

export default {
  name: 'Home',
  data() {
    return {
      missions: {},
    };
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
  background-color: #d0dcf5;
  position: relative;
}
.title {
  width: 70%;
  font-family: "Oxygen", sans-serif;

  letter-spacing: 6px;
  font-size: clamp(1.6rem, 2.1vw, 2.3rem);
  font-weight: 400 bold;
  color: #d2e1ff;
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

@media screen and (max-width: 775px) {
  .title {
    width: 75%;
    letter-spacing: 3px;
  }

  .div-image img {
    width: 80% !important;
  }
  .form-container p {
    width: 80% !important;
  }
}

@media screen and (max-width: 320px) {
  .title {
    font-size: 22px;
    width: 95% !important;
  }
}
</style>
