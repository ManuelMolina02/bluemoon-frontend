<template>
  <div class="highlights-container w-100 d-flex my-5 mx-auto">
    <div class="highlights-images w-50">
      <img
        class="w-100"
        style="max-width: 678px"
        alt="Banner image"
        :src="missions.url"
      />

      <div>
        <img
          class="w-100"
          style="max-width: 678px"
          alt="Banner image"
          :src="missions.url"
        />
      </div>
    </div>

    <div
      class="highlights-content text-white p-2 my-5 m-auto"
      style="width: 35%"
    >
      <h1 style="color: #007fe4">Missões em Marte</h1>
      <p>
        Siga cada passo dos robôs Perseverance e Curiosity na jornada de
        exploração no planeta vermelho.
      </p>

      <a class="text-white" href="#"><span>saiba mais</span></a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HighlightsComponent',
  data() {
    return {
      missions: {
        copyright: 'CARA Project',
        date: '2021-09-10',
        explanation:
          'Follow every step of the Perseverance and Curiosity robots as they explore the red planet',
        hdurl: 'https://apod.nasa.gov/apod/image/2109/67P_210907.jpg',
        media_type: 'image',
        service_version: 'v1',
        title: 'Missions Mars',
        url: 'https://apod.nasa.gov/apod/image/2108/PIA24767.jpg',
      },
    };
  },
};
</script>

<style scoped>
/* HIGLIGHTS CONTAINER */
.highlights-container {
  max-width: 75% !important;
  align-items: center;
}

.highlights-content {
  display: flex;
  flex-direction: column;

  align-items: initial;
  justify-content: center;
}

.highlights-content a {
  width: 340px;
  height: 100px;
  padding: 14px 0;

  display: block;
  position: relative;
  transition: all 0.35s;

  font-size: 2.6rem;
  letter-spacing: 5px;
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
  transition: all 0.7s;
}

.highlights-content a:hover {
  color: #007fe4 !important;
  font-weight: bold;
  border: solid 2px white;
}

.highlights-content a:hover:after {
  height: 100%;
}

.highlights-images > img {
  position: relative;
  border-radius: 16px;

  opacity: 0.5;
  top: 146px;
  left: -88px;
}

.highlights-images div img {
  position: relative;
  border-radius: 16px;
  top: -176px;
  left: -20px;
  transition-duration: 1s;
  transition-delay: 0.2s;

  box-shadow: rgba(19, 19, 19, 0.4) -5px -5px,
    rgba(19, 19, 19, 0.267) -10px -10px, rgba(19, 19, 19, 0.267) -15px -15px,
    rgba(31, 31, 31, 0.062) -20px -20px, rgba(31, 31, 31, 0.062) -25px -25px;
}

.highlights-images div img:hover {
  top: -160px;
  left: -12px;
}

@media screen and (max-width: 1400px) {
  .highlights-content,
  .highlights-images {
    width: 75% !important;
  }

  .highlights-content a {
    width: 323px;
    height: 85px;
    font-size: 2rem;
  }
}

@media screen and (max-width: 1200px) {
  .highlights-container {
    display: flex !important;
    flex-direction: column-reverse;
    align-items: center;
  }

  .highlights-images > img {
    top: 15%;
    left: -11%;
  }
  .highlights-images div img:hover {
    top: -160px;
    left: -25px;
  }
}

@media screen and (max-width: 700px) {
  .highlights-content,
  .highlights-images {
    width: 90% !important;
    margin-left: 4rem;
  }
}
</style>
