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

    <!-- CAROUSEL CONTAINER -->
    <div class="carousel-container d-flex">
      <!--
        PRIMARY -> CAROUSEL CONTAINER
      -->
            <b-carousel
        class="carousel-content"
        style="text-shadow: 0px 0px 2px #000"
        no-animation
        indicators

      >
        <!-- CAROUSEL IMAGES -->
        <b-carousel-slide
          v-b-modal.primaryPublication
          :img-src="carousel[0].urlImage"
        >
          <b-modal id="primaryPublication" centered ok-only lazy>
            <p>
              {{ carousel[0].title }}

              <b-button
                v-b-popover="carousel[0].datePublication"
                title="Publication Date"
                >learn more</b-button
              >
            </p>
          </b-modal>
        </b-carousel-slide>

        <b-carousel-slide v-b-modal.secondPublication :img-src="carousel[1].urlImage">
          <b-modal id="secondPublication" centered ok-only lazy>
            <p>
              {{ carousel[1].title }}

              <b-button
                v-b-popover="carousel[1].datePublication"
                title="Publication Date"
                >learn more</b-button
              >
            </p>
          </b-modal>
        </b-carousel-slide>

        <b-carousel-slide v-b-modal.thirdPublication :img-src="carousel[2].urlImage">
          <b-modal id="thirdPublication" centered ok-only lazy>
            <p>
              {{ carousel[2].title }}

              <b-button
                v-b-popover="carousel[2].datePublication"
                title="Publication Date"
                >learn more</b-button
              >
            </p>
          </b-modal>
        </b-carousel-slide>

      </b-carousel>

      <!--
        SECOND -> CAROUSEL CONTAINER
      -->
      <b-carousel
        class="carousel-content"
        style="text-shadow: 0px 0px 2px #000"
        no-animation
        indicators
        v-b-modal.primaryModalPopover
      >
        <!-- MODAL CONTAINER -->
        <b-modal id="primaryModalPopover" centered ok-only lazy>
          <p>
            segundo modal

            <b-button v-b-popover="'oioioi!'" title="Publication Date"
              >botão com tooltip</b-button
            >
          </p>

          <p>
            <a href="#" v-b-tooltip title="Tooltip in a modal!">Link</a>
          </p>
        </b-modal>

        <!-- CAROUSEL CONTAINER -->
        <b-carousel-slide :img-src="carousel[0].urlImage"></b-carousel-slide>
        <b-carousel-slide :img-src="carousel[1].urlImage"></b-carousel-slide>
        <b-carousel-slide :img-src="carousel[2].urlImage"></b-carousel-slide>
      </b-carousel>

      <!--
        THIRD -> CAROUSEL CONTAINER
      -->
      <b-carousel
        class="carousel-content"
        style="text-shadow: 0px 0px 2px #000"
        no-animation
        indicators
        v-b-modal.thirdModalPopover
      >
        <!-- MODAL CONTAINER -->
        <b-modal id="thirdModalPopover" centered ok-only lazy>
          <p>
            terceiro modal

            <b-button v-b-popover="'oioioi!'" title="uhuuuuuuuu"
              >botão com tooltip</b-button
            >
          </p>

          <p>
            <a href="#" v-b-tooltip title="Tooltip in a modal!">Link</a>
          </p>
        </b-modal>

        <!-- CAROUSEL CONTAINER -->
        <b-carousel-slide :img-src="carousel[0].urlImage"></b-carousel-slide>
        <b-carousel-slide :img-src="carousel[1].urlImage"></b-carousel-slide>
        <b-carousel-slide :img-src="carousel[2].urlImage"></b-carousel-slide>
      </b-carousel>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
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

      carousel: [
        {
          title: 'A Fire Rainbow over West Virginia',
          explanation:
            "What's happening to this cloud? Ice crystals in a distant cirrus cloud are acting like little floating prisms. Known informally as a fire rainbow for its flame-like appearance, a circumhorizon arc appears parallel to the horizon. For a circumhorizontal arc to be visible, the Sun must be at least 58 degrees high in a sky where cirrus clouds present below -- in this case cirrus fibrates. The numerous, flat, hexagonal ice-crystals that compose the cirrus cloud must be aligned horizontally to properly refract sunlight in a collectively similar manner. Therefore, circumhorizontal arcs are somewhat unusual to see. The featured fire rainbow was photographed earlier this month near North Fork Mountain in West Virginia, USA.",
          datePublication: '2021 August 30',
          urlReference: 'https://apod.nasa.gov/apod/ap210830.html',
          urlImage:
            'https://apod.nasa.gov/apod/image/2108/FireRainbow_Harbig_960.jpg',
          urlBigImage:
            'https://apod.nasa.gov/apod/image/2108/FireRainbow_Harbig_4000.jpg',
        },

        {
          title: 'Sun Spot Hill',
          explanation:
            "Is this giant orange ball about to roll down that tree-lined hill? No, because the giant orange ball is actually the Sun. Our Solar System's central star was captured rising beyond a hill on Earth twelve days ago complete with a delightfully detailed foreground. The Sun's disk showed five sunspots, quite a lot considering that during the solar minimum in solar activity of the past few years, most days showed no spots. A close look at the hill -- Sierra del Cid in Perter, Spain -- reveals not only silhouetted pine trees, but silhouetted people -- by coincidence three brothers of the photographer. The trees and brothers were about 3.5-kilometers away during the morning of the well-planned, single-exposure image. A dark filter muted the usually brilliant Sun and brought up great detail on the lower sunspots. Within a few minutes, the Sun rose far above the hill, while within a week, the sunspots rotated around the Sun, out of view. The captured scene, however, is now frozen in time for all to enjoy.",
          datePublication: '2021 September 21',
          urlReference: 'https://apod.nasa.gov/apod/ap210921.html',
          urlImage:
            'https://apod.nasa.gov/apod/image/2109/SunSpotHill_Coy_960.jpg',
          urlBigImage:
            'https://apod.nasa.gov/apod/image/2109/SunSpotHill_Coy_2358.jpg',
        },
        {
          title: 'A Blue Moon in Exaggerated Colors',
          explanation:
            "The Moon is normally seen in subtle shades of grey or gold. But small, measurable color differences have been greatly exaggerated to make this telescopic, multicolored, moonscape captured during the Moon's full phase. The different colors are recognized to correspond to real differences in the chemical makeup of the lunar surface. Blue hues reveal titanium rich areas while orange and purple colors show regions relatively poor in titanium and iron. The familiar Sea of Tranquility, or Mare Tranquillitatis, is the blue area toward the upper right. White lines radiate across the orange-hued southern lunar highlands from 85-kilometer wide ray-crater Tycho at bottom right. The full moon that occurred earlier this month could be counted as a seasonal blue moon because it was, unusually, the third of four full moons to occur during northern summer (and hence southern winter). The featured 272-image composite demonstrates that the full Moon is always blue, but usually not blue enough in hue to ooh.",
          datePublication: '2021 August 31',
          urlReference: 'https://apod.nasa.gov/apod/ap210831.html',
          urlImage: 'https://apod.nasa.gov/apod/image/2108/Luna_Fedez_960.jpg',
          urlBigImage:
            'https://apod.nasa.gov/apod/image/2108/Luna_Fedez_1600.jpg',
        },
        {
          title: 'The Bubble and the Star Cluster',
          explanation:
            ' To the eye, this cosmic composition nicely balances the Bubble Nebula at the right with open star cluster M52. The pair would be lopsided on other scales, though. Embedded in a complex of interstellar dust and gas and blown by the winds from a single, massive O-type star, the Bubble Nebula, also known as NGC 7635, is a mere 10 light-years wide. On the other hand, M52 is a rich open cluster of around a thousand stars. The cluster is about 25 light-years across. Seen toward the northern boundary of Cassiopeia, distance estimates for the Bubble Nebula and associated cloud complex are around 11,000 light-years, while star cluster M52 lies nearly 5,000 light-years away. The wide telescopic field of view spans about 1.5 degrees on the sky or three times the apparent size of a full Moon.',
          datePublication: '2021 September 25',
          urlReference: 'https://apod.nasa.gov/apod/ap210925.html',
          urlImage:
            'https://apod.nasa.gov/apod/image/2109/241_lorand_fenyes_bubble_m52_1120.jpg',
          urlBigImage:
            'https://apod.nasa.gov/apod/image/2109/241_lorand_fenyes_bubble_m52.jpg',
        },
      ],
    };
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
