<template>
  <div
    class="product-container w-100 d-flex my-5 mx-auto"
  >
    <div class="product-images w-50 my-5">
      <img
        class="w-100"
        style="max-width: 568px"
        alt="Banner image"
        :src="missions.url"
      />
    </div>

    <div class="product-content text-white p-2 my-5 m-auto" style="width: 35%">
      <div class="product-item mb-5">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>
      </div>

      <div class="product-item mb-5">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>
      </div>

      <div class="product-item mb-5">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>
      </div>

      <div class="product-item mb-5">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>
      </div>

      <div class="product-item mb-5">
        <h1>Mars Missons</h1>
        <p>
          Follow every step of the Perseverance and Curiosity robots as they
          explore the red planet
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductComponent',
  data() {
    return {
      missions: {
        copyright: 'CARA Project',
        date: '2021-09-10',
        explanation:
          'Follow every step of the Perseverance and Curiosity robots as they explore the red planet',
        hdurl:
          'https://apod.nasa.gov/apod/image/2109/GalaxySkyMirror_Egon_960.jpg',
        media_type: 'image',
        service_version: 'v1',
        title: 'Missions Mars',
        url: 'https://apod.nasa.gov/apod/image/2109/AuroraIceland_Necchi_1280.jpg',
      },
    };
  },
};
</script>

<style scoped>
/* HIGLIGHTS CONTAINER */
.product-container {
  max-width: 75% !important;
}

.product-content {
  display: flex;
  flex-direction: column;

  align-items: initial;
  justify-content: center;
}

.product-images > img {
  position: sticky;
  border-radius: 8px;
  transition-delay: 2s;

  top: 32px;
}
</style>
