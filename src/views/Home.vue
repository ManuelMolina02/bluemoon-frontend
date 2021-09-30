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

    <!-- open called images -->
    <div class="w-75 my-5 mx-auto">
      <div>
        <h1 class="w-50 my-5 mx-auto title text-white">
          Click on a photo and preview it along with a brief explanation written
          by a professional astronomer.
        </h1>
      </div>
    </div>

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
        class="carousel-content my-5"
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

        <b-modal id="primaryPublication" scrollable title="Scrollable Content">
          <p class="my-4" v-for="mission in missions" :key="mission.title">
            {{ mission.title }}
          </p>
        </b-modal>
      </b-carousel>
    </div>

    <div>
      <img class="my-5 py-5 w-50" src="../assets/text-content.svg" alt="">
    </div>

    <!-- HIGHLIGHTS CONTAINER-->
    <div
      class="highlights-container w-100 d-flex mx-auto"
      style="background: rgba(20, 20, 20, 0.8)"
    >
      <div class="highlights-content text-white w-25 my-5 mx-auto">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>

          <a href="#" class="btn btn-highlights text-white">lear more</a>

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
      missions: [
        {
          copyright: 'Mike Cohea',
          date: '2021-09-23',
          explanation:
            "Famed in festival, story, and song the best known full moon is the Harvest Moon. For northern hemisphere dwellers that's a traditional name of the full moon nearest the September equinox. Seen from Saunderstown, Rhode Island, planet Earth, this Harvest Moon left a broad streak of warm hues as it rose through a twilight sky over the Newport Bridge. On September 20 its trail was captured in a single 22 minute exposure using a dense filter and a digital camera. Only two days later the September equinox marked a change of season and the beginning of autumn in the north. In fact, recognizing a season as the time between solstice and equinox, this Harvest Moon was the fourth full moon of the season, coming just before the astronomical end of northern summer.",
          hdurl:
            'https://apod.nasa.gov/apod/image/2109/Cohea_APOD_HarvestMoon.jpg',
          media_type: 'image',
          service_version: 'v1',
          title: 'Harvest Moon Trail',
          url: 'https://apod.nasa.gov/apod/image/2109/Cohea_APOD_HarvestMoon1067.jpg',
        },
        {
          copyright: 'Pierre Martin',
          date: '2021-09-24',
          explanation:
            "This year an outburst of Perseid meteors surprised skywatchers. The reliable meteor shower's peak was predicted for the night of August 12/13. But persistent visual observers in North America were deluged with a startling Perseid shower outburst a day later, with reports of multiple meteors per minute and sometimes per second in the early hours of August 14. The shower radiant is high in a dark night sky in this composite image. It painstakingly registers the trails of 282 Perseids captured during the stunning outburst activity between 0650 UT (02:50am EDT) and 0900 UT (05:00am EDT) on August 14 from Westmeath Lookout, Ontario. Of course the annual Perseid meteor shower is associated with planet Earth's passage through dusty debris from periodic comet 109P/Swift-Tuttle. The 2021 outburst could have been caused by an unanticipated encounter with the Perseid Filament, a denser ribbon of dust inside the broader debris zone.",
          hdurl:
            'https://apod.nasa.gov/apod/image/2109/IMG_9365-Aug1314-2021-282-meteors.jpg',
          media_type: 'image',
          service_version: 'v1',
          title: 'Perseid Outburst at Westmeath Lookout',
          url: 'https://apod.nasa.gov/apod/image/2109/IMG_9365-Aug1314-2021-282-meteors1024.jpg',
        },
        {
          copyright: 'Lorand Fenyes',
          date: '2021-09-25',
          explanation:
            'To the eye, this cosmic composition nicely balances the Bubble Nebula at the right with open star cluster M52. The pair would be lopsided on other scales, though. Embedded in a complex of interstellar dust and gas and blown by the winds from a single, massive O-type star, the Bubble Nebula, also known as NGC 7635, is a mere 10 light-years wide.  On the other hand, M52 is a rich open cluster of around a thousand stars. The cluster is about 25 light-years across. Seen toward the northern boundary of Cassiopeia, distance estimates for the Bubble Nebula and associated cloud complex are around 11,000 light-years, while star cluster M52 lies nearly 5,000 light-years away. The wide telescopic field of view spans about 1.5 degrees on the sky or three times the apparent size of a full Moon.',
          hdurl:
            'https://apod.nasa.gov/apod/image/2109/241_lorand_fenyes_bubble_m52.jpg',
          media_type: 'image',
          service_version: 'v1',
          title: 'The Bubble and the Star Cluster',
          url: 'https://apod.nasa.gov/apod/image/2109/241_lorand_fenyes_bubble_m52_1120.jpg',
        },
        {
          copyright: 'Peter TuthillSydney U.Cornell U.',
          date: '2021-09-26',
          explanation:
            'How did a round star create this square nebula? No one is quite sure. The round star, known as MWC 922 and possibly part of a multiple star system, appears at the center of the Red Square Nebula.  The featured image combines infrared exposures from the Hale Telescope on Mt. Palomar in California, and the Keck-2 Telescope on Mauna Kea in Hawaii.  A leading progenitor hypothesis for the square nebula is that the central star or stars somehow expelled cones of gas during a late developmental stage. For MWC 922, these cones happen to incorporate nearly right angles and be visible from the sides.  Supporting evidence for the cone hypothesis includes radial spokes in the image that might run along the cone walls. Researchers speculate that the cones viewed from another angle would appear similar to the gigantic rings of supernova 1987A, possibly indicating that a star in MWC 922 might one day itself explode in a similar supernova.',
          hdurl:
            'https://apod.nasa.gov/apod/image/2109/RedSquare_Tuthill_960.jpg',
          media_type: 'image',
          service_version: 'v1',
          title: 'The Red Square Nebula',
          url: 'https://apod.nasa.gov/apod/image/2109/RedSquare_Tuthill_960.jpg',
        },
        {
          date: '2021-09-27',
          explanation:
            "Here is one of the most famous pictures from the Moon -- but digitally reversed. Apollo 11 landed on the moon in 1969 and soon thereafter many pictures were taken, including an iconic picture of Buzz Aldrin taken by Neil Armstrong. The original image captured not only the magnificent desolation of an unfamiliar world, but Armstrong himself reflected in Aldrin's curved visor.  Enter modern digital technology. In the featured image, the spherical distortion from Aldrin's helmet has been reversed.  The result is the famous picture -- but now featuring Armstrong himself from Aldrin's perspective. Even so, since Armstrong took the picture, the image is effectively a five-decade old lunar selfie.  The original visor reflection is shown on the left, while Earth hangs in the lunar sky on the upper right. A foil-wrapped leg of the Eagle lander is prominently visible.  Preparations to return humans to the Moon in the next few years include the Artemis program, an international collaboration led by NASA.",
          hdurl:
            'https://apod.nasa.gov/apod/image/2109/AldrinVisor_Apollo11_4096.jpg',
          media_type: 'image',
          service_version: 'v1',
          title: 'Unwrapped: Five Decade Old Lunar Selfie',
          url: 'https://apod.nasa.gov/apod/image/2109/AldrinVisorCrop_Apollo11_1080.jpg',
        },
      ],
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

    align-items: center;
    justify-content: center;

}

.btn-highlights{
 width: 400px !important;
 height: 80px !important;

 font-size: 34px;
 text-align: center;

 border-radius: 0 !important;
 border: solid 2px white;
 transition: .5s ease;
}

.btn-highlights:hover{
  background-color: white;
  color: black !important;
  transition-delay: .2s;
}

</style>
