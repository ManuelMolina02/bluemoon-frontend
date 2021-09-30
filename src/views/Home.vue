<template>
  <div class="home">
    <!-- BANNER CONTAINER -->
    <div class="banner-container">
      <div
        class="banner-image"
        style="
          filter: grayscale(0.2) contrast(180%) saturate(1) hue-rotate(184deg);
        "
      >
        <img
          class="w-100"
          style="max-width: 1678px"
          alt="Banner image"
          :src="banner.urlBigImage"
        />
      </div>

      <div class="banner-content">
        <h1 class="text-white" style="width: 40%">
          Astronomy Picture of the Day
        </h1>

        <p class="text-white" style="width: 35%">
          Discover the cosmos! Each day a different image or photograph of our
          fascinating universe is featured
        </p>
      </div>
    </div>

    <!-- CAROUSEL CONTAINER -->
    <div class="mt-5 py-5" style="background: rgba(20, 20, 20, 0.5)">
      <!-- open called images -->
      <div class="w-75 my-5 mx-auto">
        <div>
          <h1 class="w-50 my-5 mx-auto title text-white">
            Click on a photo and preview it along with a brief explanation
            written by a professional astronomer.
          </h1>
        </div>
      </div>

      <div class="carousel-container d-flex my-5 py-5">
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
            class="img-fluid d-block"
            style="max-width: 860px; max-height: 420px; object-fit: cover"
          >
          </b-carousel-slide>
        </b-carousel>

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
            class="img-fluid d-block"
            style="max-width: 860px; max-height: 420px"
          >
          </b-carousel-slide>
        </b-carousel>

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
            class="img-fluid d-block"
            style="max-width: 860px; max-height: 420px"
          >
          </b-carousel-slide>

          <b-modal
            id="primaryPublication"
            scrollable
            title="Scrollable Content"
          >
            <p class="my-4" v-for="mission in missions" :key="mission.title">
              {{ mission.title }}
            </p>
          </b-modal>
        </b-carousel>
      </div>
    </div>

    <!-- HIGHLIGHTS CONTAINER-->
    <div
      class="highlights-container w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.8)"
    >
      <div class="highlights-content text-white w-25 p-2 my-5 m-auto">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>

        <a class="text-white" href="#"><span>lear more</span></a>
      </div>

      <div class="highlights-images w-50 my-5">
        <img
          class="w-100"
          style="max-width: 678px"
          alt="Banner image"
          :src="banner.urlBigImage"
        />
      </div>
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
          :src="banner.urlBigImage"
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

    <div style="background-color: #0e0e0e">
            <img
        class="my-2 py-5 w-50"
        src="../assets/text-cont.svg"
        alt=""
        style="background-color: #0e0e0e"
      />

      <div class="pb-5">
        <!-- form card -->
        <div
          class="w-50 mx-auto text-white text-start p-5"
          style="border: solid 2px white; border-radius: 4px"
        >
          <b-form @submit="onSubmit" @reset="onReset" v-if="show" class="py-5">
            <div>
              <div class="my-3">
                <div>Value</div>
                <b-form-input
                  v-model="text"
                  placeholder="Enter your name"
                ></b-form-input>
              </div>

              <div class="my-3">
                <div>Value</div>
                <b-form-input
                  v-model="text"
                  placeholder="Enter your name"
                ></b-form-input>
              </div>

              <div class="my-3">
                <div>Value</div>
                <b-form-input
                  v-model="text"
                  placeholder="Enter your name"
                ></b-form-input>
              </div>
            </div>

            <div class="d-flex py-5" style="gap: 15px; justify-content: center">
              <b-button type="submit" variant="primary">Submit</b-button>
              <b-button type="reset" variant="danger">Reset</b-button>
            </div>
          </b-form>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
/*
const axios = require('axios').default;
*/
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

      form: {
        email: '',
        name: '',
        food: null,
        checked: [],
      },

      foods: [
        { text: 'Select One', value: null },
        'Carrots',
        'Beans',
        'Tomatoes',
        'Corn',
      ],
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = '';
      this.form.name = '';
      this.form.food = null;
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },

  /*
  async created() {
    await axios
      .get(
        'https://api.nasa.gov/planetary/apod?start_date=2021-09-23&end_date=2021-09-28&api_key=AOx0gbuEF9RXCpkQBkYq0eGDEkGCSYdhOpUT6Y4K',
      )
      .then((response) => {
        this.missions = response.data;
        console.log(this.missions);
      })
      .catch((error) => {
        console.error(error);
      });
  }, */
};
</script>

<style scoped>
/*text globals*/
.banner-content h1,
.highlights-content h1 {
  font-size: 78px;
  font-weight: bold;
  text-align: initial !important;
}

.banner-content p,
.highlights-content p {
  font-size: 38px;
  text-align: initial !important;
}

.title {
  font-size: 36px;
  line-height: 66px;
  letter-spacing: 0.16em;
}

/* BANNER CONTAINER */

.image-mask-filter {
  position: absolute;
  background-color: aqua;
  width: 100%;
  height: 80%;
  opacity: 0.2;
}

/* text content */

.banner-content {
  position: absolute;
  top: 18%;
  left: 19%;

  font-family: "Quantico", sans-serif;
}

.banner-content p {
  margin-top: 260px !important;
}

/* CAROUSEL CONTAINER */
.carousel-container {
  align-items: center;
}

.carousel-content {
  filter: grayscale(100%);
}

.carousel-content:hover {
  transition-delay: 0.2s;
  animation: filter-animation 5s infinite;
}

.carousel-item img {
  max-width: 100% !important;
  height: auto !important;
}

@keyframes filter-animation {
  0% {
    filter: hue-rotate(0);
  }

  50% {
    filter: hue-rotate(154deg) saturate(2);
  }

  100% {
    filter: hue-rotate(0);
  }
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
